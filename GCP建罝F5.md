## GCP建置F5

### 登入GCP後，選擇Cloud Launcher <br>
 ![Cloud Launcher](pic/f5_1.jpg "Cloud Launcher!")
 
### 搜尋f5，選擇F5 BIG-IP ADC Best-BYOL<br>
 ![Best-BYOL](pic/f5_2.jpg "Best-BYOL")
### 下方內容有說明F5各等級的差異 <br>
 ![各版本的差別](pic/f5_3.jpg "各版本的差別")
### 按COMPUTE ENGINE上啟動 <br>
 ![COMPUTE ENGINE](pic/f5_4.jpg "COMPUTE ENGINE")
### 輸入NAME、ZONE，資源依需求調整，按部署  <br>
 ![輸入NAME、ZONE](pic/f5_5.jpg "輸入NAME、ZONE")
### 正在部署   <br>
 ![正在部署](pic/f5_6.jpg "正在部署")
### 部署完成<br>
 ![部署完成](pic/f5_7.jpg "部署完成")
 ![提示](pic/f5_8.jpg "提示")

### 塑建議回到VM執行個體，查看F5的IP與是否啟動成功<br>
 ![部署完成](pic/f5_7_1.jpg "部署完成")

### 接著到VPC網路，外部IP位址，將上述的IP 類型從臨時改成「靜態」，否則重開機之後外部IP會換過。<br>

### 開啟xshell連線F5 IP，視各個環境狀況選擇以下方式登入  <br>
### 1.使用admin 登入 。<br>
 ![admin 登入](pic/f5_9.jpg "admin 登入")
### 2.如果GCP有使用中繼資料 admin登入改密碼需使用public key(admin)  與 私人key 進行登入。<br>
![admin 登入](pic/f5_9_0.jpg "admin 登入")
![admin 登入](pic/f5_9_1.jpg "admin 登入")
### 要更改管理員密碼，輸入modify auth password admin  <br>
### 輸入密碼 <br>
### 再次確認密碼 <br>
### 確保系統保留更改密碼，請輸入save sys config <br>
 ![更改管理員密碼](pic/f5_10.jpg "更改管理員密碼")
### 開啟網頁輸入https://104.198.93.133:8443 使用admin與管理員新密碼登入<br>
 ![Cloud Launcher](pic/f5_11.jpg "Cloud Launcher!")
### 成功登入F5的畫面，按activate　 <br>
 ![成功登入F5](pic/f5_12.jpg "成功登入F5")
### 輸入License，選 NEXT　 <br>
 ![License](pic/f5_13.jpg "License")
### 選 accetp　 <br>
 ![License](pic/f5_14.jpg "License")
### 進行中　 <br>
 ![License](pic/f5_15.jpg "License")
### 完畢，選CONTINUE　 <br>
 ![License](pic/f5_16.jpg "License")
### 調整F5時區，System->Platform 改成台北時區。 <br>
 ![License](pic/f5_18.jpg "License")
### GCP建置完會自動建好防火牆規則，22PORT不需要，8443PORT僅留維護線路IP。 <br>
 ![License](pic/f5_17.jpg "License")

