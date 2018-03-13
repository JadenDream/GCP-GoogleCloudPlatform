## GCP 匯入憑證

### 登入F5，https://f5.live.bvcasino.info:8443 <br>
 ![F5匯入憑證](pic/screenshot_25.jpg "F5匯入憑證")
### MAIN, SSL Orchestrator, Certitificates and keys <br>
 ![F5匯入憑證](pic/screenshot_26.jpg "F5匯入憑證")

### 匯入Traffic Certificate Management憑證 選import 
 ![F5匯入憑證](pic/screenshot_26_1.jpg "F5匯入憑證")
### import type：選PKCS 12 (IIS) 
 ![F5匯入憑證](pic/screenshot_26_2.jpg "F5匯入憑證")
### 選擇憑證的檔案，檔案選 .pme<br> 
 ![F5匯入憑證](pic/screenshot_27.jpg "F5匯入憑證")
### name可自行定義，輸入密碼，按import <br>
 ![F5匯入憑證](pic/screenshot_28.jpg "F5匯入憑證")
### 匯入憑證完畢畫面<br>

 ![F5匯入憑證](pic/screenshot_29.jpg "F5匯入憑證")
### 繼續匯入憑證，選certificate, 檔案選 .crt<br>
 ![F5匯入憑證](pic/screenshot_30.jpg "F5匯入憑證")
### 匯入憑證完畢畫面<br>
 ![F5匯入憑證](pic/screenshot_31.jpg "F5匯入憑證")

### F5的domain需使用https，因此需匯入Device Certificate Management 憑證，選擇device certificate，選擇impoart<br>
 ![F5匯入憑證](pic/screenshot_32.jpg "F5匯入憑證")
### import type：選PKCS 12 (IIS) <br>
 ![F5匯入憑證](pic/screenshot_33.jpg "F5匯入憑證")
### 匯入憑證完畢畫面<br>
 ![F5匯入憑證](pic/screenshot_34.jpg "F5匯入憑證")