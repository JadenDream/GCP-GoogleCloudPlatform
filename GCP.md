# 建立GCP雲端機器
##### <p>1. [連結到Google Cloud Platform](https://cloud.google.com/?utm_source=google&utm_medium=cpc&utm_campaign=japac-TW-all-en-dr-bkws-all-super-trial-e-dr-1002234&utm_content=text-ad-none-none-DEV_c-CRE_205812821243-ADGP_BKWS%20%7C%20EXA%20~%20T1%20-%20General_M:1_TW_EN_cloud-googlecloud-KWID_43700018487811535-kwd-35920686936&userloc_9040380&utm_term=KW_googlecloud&gclid=CNnCzIrBg9UCFVgFKgod99wNLQ&dclid=COnE9orBg9UCFcUulgodL5kHxg "Google Cloud Platform")</p>
##### <p>2. 登入Google `ex. charles.wang@gosmio.biz`</p>
##### <p>3. 點擊畫面右上角`控制台`<br /> ![DashBoard](images/gcp_dashboard.jpg "控制台")</p>
***
##### <p>4. 選取或建立新機構（專案）<br /> ![Projects](images/gcp_projects.jpg "建立專案")</p>
***
##### <p>5. 選取gosmio.biz/`Bet666`專案 <br /> ![Select](images/gcp_project_select.jpg "選取專案") <p>即可看到「資訊主頁」畫面。<br /> ![Console](images/gcp_main_page.jpg "資訊主頁")</p></p>
***
##### <p>6. 點選`資訊主頁`畫面左上方的工具列 <br /> ![List](images/gcp_func_list.jpg "工具列清單")<p>畫面左側會出現工具列清單。</p></p>
***
##### <p>7. 點選工具列清單→Compute Engine→`VM執行個體` <br /> ![VM](images/gcp_vm_compute.jpg "VM執行個體") <p>點選`建立執行個體`。</p></p>
***
##### <p>8. 輸入名稱`（名稱必須為小寫字母、數字或連字號，且結尾須為小寫字母或數字）`、選擇區域與機器類型<br />![Select Name and Area](images/gcp_vm_create01.jpg "Step01-1") <p>點選`變更`，選擇作業系統與開機磁碟類型 <br /> ![Select Operating System and Disk Type](images/gcp_vm_create01_os.jpg "Step01-2") <br />點選`選取`</p></p>
***
##### <p>9. 依需求變更`身分及API存取權`與`防火牆` <br /> ![Select Identity and Firewall](images/gcp_vm_create02_firewall.jpg "Step02")</p>
***
##### <p>10. 設定`管理、磁碟、網路、SSH金鑰` <br /> ![Settign Manage, Disk, Network and SSH](images/gcp_vm_create03_mgr.jpg "Step03") <p> 10.1. 設定`管理`頁籤內容 <br /> ![Manage Page](images/gcp_vm_create03_manage.jpg "Step03-1.") <br /> 10.2. 設定`磁碟`頁籤內容（點選`＋新增項目`建立第二磁碟） <br /> ![Setting Disk](images/gcp_vm_create03_disk.jpg "Step03-2") <br /> 10.3. 設定`網路`頁籤內容（在`網路介面`下點選編輯）<br /> ![Setting Network](images/gcp_vm_create03_network.jpg "Step03-3-1") <br /> ![Setting Detail of Network](images/gcp_vm_create03_network_setting.jpg "Step03-3-2") <br /> 10.4. 設定`SSH金鑰` <br /> ![Setting SSH](images/gcp_vm_create03_ssh.jpg "Step04") </p></p>
***
##### <p>11. 再次確認步驟8至步驟10的內容是否正確，確認無誤後，點選`建立` <br /> ![Created](images/gcp_vm_done.jpg "Done!")</p>
# <p>完成`GCP雲端機器`建立</p>