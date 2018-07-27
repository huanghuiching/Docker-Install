# Docker-Install
## Linux CentOS version
## 下載說明請參考網頁 https://docs.docker.com/install/linux/docker-ce/centos/#install-using-the-convenience-script

步驟1. 從get.docker.com網址處爬取安裝程式並執行
> curl -fsSL https://get.docker.com/ | sh

步驟2. 如果你希望非 root 身分也可以操作 docker 的話，請在 docker group 新增使用者，該使用者將在 docker 容器內擁有 root 權限。(新增使用者必須再次登出登入後才會產生效果)
> sudo groupadd docker
> sudo usermod -aG docker your-user
