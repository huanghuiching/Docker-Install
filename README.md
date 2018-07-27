# Docker-Install
## Linux CentOS version
#### Docker Official Installation: https://docs.docker.com/install/linux/docker-ce/centos/#install-using-the-convenience-script

#### 步驟1. 從get.docker.com網址處爬取安裝程式並執行
> curl -fsSL https://get.docker.com/ | sh

#### 步驟2. 如果你希望非 root 身分也可以操作 docker 的話，請在 docker group 新增使用者，該使用者將在 docker 容器內擁有 root 權限。(新增使用者必須再次登出登入後才會產生效果)
> sudo groupadd docker

> sudo usermod -aG docker your-user

#### 步驟3. 測試權限是否更改正確(就是run一個docker喊hello-world的測試)
> docker run hello-world

##### 測試失敗錯誤訊息：
> WARNING: Error loading config file: /home/user/.docker/config.json - stat /home/user/.docker/config.json: permission denied

##### 解法1. 刪除家目錄裡面的docker目錄(下次使用的時候會再重新生成，但是docker裡面的設定都會不見)
> rm -r ~/.docker/ 

##### 解法2. 用以下的語法去修改 
> sudo chown "$USER":"$USER" /home/"$USER"/.docker -R

> sudo chmod g+rwx "/home/$USER/.docker" -R

#### 步驟4. 啟用程式

##### 設定自動啟用(若要取消此功能請執行disable那行程式)
##### 如果沒有systemctl功能的系統可用 $ sudo chkconfig docker on 完成設定
> sudo systemctl enable docker

> sudo systemctl disable docker



##### 手動啟用(大部分linux系統支援systemctl語法，如果不成功，請嘗試改用service)
> sudo systemctl start docker

> sudo service docker start
