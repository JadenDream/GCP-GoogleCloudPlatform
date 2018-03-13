
### sc架構：客端-lb-f5-vs-pool-node-web01~04

### 要使用F5 需設定node→pool→virtual servers

# 一、登入F5
### https://f5.live.bvcasino.info:8443
![local traffic](pic/set/screenshot_89.jpg "local traffic")
# 建立node 
### local traffic 選 nodes -> 右上create 
![local traffic](pic/set/screenshot_90.jpg "local traffic")

### 建立WEB01~04，設定完按finish，下圖以WEB01為例 
![local traffic](pic/set/screenshot_91.jpg "local traffic")

### nodes設定完成畫面 
![local traffic](pic/set/screenshot_92.jpg "local traffic")


# 二、建立pool 
### 建立 web使用的pool -> 右上create 
![local traffic](pic/set/screenshot_93.jpg "local traffic")
### 輸入name、health monitors、load balancing method
![local traffic](pic/set/screenshot_94.jpg "local traffic")
### New Member選擇 node list 即會出現剛才新增的node選項，輸入address、port、add加入後，按finished
![local traffic](pic/set/screenshot_95.jpg "local traffic")
### pool設定完成畫面，status為綠色
![local traffic](pic/set/screenshot_96.jpg "local traffic")


# 三、建立virtual servers (需建立http與https二種)
## 1.建立 http使用的virtual servers -> 右上create 
![local traffic](pic/set/screenshot_97.jpg "local traffic")
### 輸入name(vs_web_80)、source address(任何人皆可連線)、destination address/mark 則要輸入此台f5的內網ip
![local traffic](pic/set/screenshot_99.jpg "local traffic")
### source address translation(SAT) 要選擇 automap
![local traffic](pic/set/screenshot_100.jpg "local traffic")
### default pool 要選擇 pool_web，按finished
![local traffic](pic/set/screenshot_101.jpg "local traffic")


## 2.建立 https使用的virtual server 
### 因HTTPS需要ssl profile(clinet) 需要到profiles先設定
![local traffic](pic/set/screenshot_103.jpg "local traffic")
![local traffic](pic/set/screenshot_104.jpg "local traffic")
![local traffic](pic/set/screenshot_105.jpg "local traffic")
![local traffic](pic/set/screenshot_106.jpg "local traffic")
### 建立 http使用的virtual servers -> 右上create 
![local traffic](pic/set/screenshot_97.jpg "local traffic")
### 輸入name(vs_web_443)、source address(任何人皆可連線)、destination address/mark 則要輸入此台f5的內網ip
![local traffic](pic/set/screenshot_102.jpg "local traffic")
### 選bravocasinossl 
![local traffic](pic/set/screenshot_107.jpg "local traffic")
### source address translation(SAT) 要選擇 automap
![local traffic](pic/set/screenshot_100.jpg "local traffic")
### default pool 要選擇 pool_web
![local traffic](pic/set/screenshot_101.jpg "local traffic")
### virtual server 設定完畢畫面
![local traffic](pic/set/screenshot_108.jpg "local traffic")
### 全部設定完畢畫面
![local traffic](pic/set/screenshot_111.jpg "local traffic")



# 四、建立gcp vm、lb
### 建立VM、建立個體群組
![local traffic](pic/lb/screenshot_00.jpg "local traffic")
### 新增負載平衡，啟動設定
![local traffic](pic/lb/screenshot_01.jpg "local traffic")
### 後端設定
![local traffic](pic/lb/screenshot_02.jpg "local traffic")
### 建立後端服務，並設定健康狀態
![local traffic](pic/lb/screenshot_02-1.jpg "local traffic")
###主機與路徑規格 會自動帶入
![local traffic](pic/lb/screenshot_03.jpg "local traffic")
### 前端設定 HTTP
![local traffic](pic/lb/screenshot_04.jpg "local traffic")

### 過一陣子後，檢查健康狀態為 0/ 1  因後端連不到LB

### 所以需要另外處理，這裡使用irules來客製化才會讓後端連到LB，因irules裡程式會使用到 http標頭，因此需到gcp的f5的健康狀態設定http標頭
###![local traffic](pic/screenshot_199.jpg "local traffic")


### 到f5網頁上面設定irules -> 右上create 
![local traffic](pic/screenshot_200.jpg "local traffic")
![local traffic](pic/screenshot_201.jpg "local traffic")
```
when HTTP_REQUEST {
    set httpHost [string tolower [HTTP::host]]
    if { $httpHost equals "gcplbcheck" } {
        HTTP::respond 200
        return
    }
}
```

### 到GCP新增防火牆規則   
```
130.211.0.0/22
35.191.0.0/16
```

![local traffic](pic/set/screenshot_109.jpg "local traffic")

### 設定完畢 檢查健康狀態正確要為 1/ 1 
![local traffic](pic/lb/screenshot_05.jpg "local traffic")




# 五、調整cloud DNS
![local traffic](pic/lb/screenshot_06.jpg "local traffic")



# 六、測試F5 是否設定成功

### 需先在各WEB全部加入一個站台
![local traffic](pic/screenshot_101.jpg "local traffic")
### 測試lb http 成功導到web設備
![local traffic](pic/screenshot_102.jpg "local traffic")
### 因lb是需要給所有玩家連線的  所只會吃80 port, 因此443連不上，此為正常
![local traffic](pic/screenshot_103.jpg "local traffic")


