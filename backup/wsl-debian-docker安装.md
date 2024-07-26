```
sudo -i       
sudo cp /etc/apt/sources.list /etc/apt/sources.list_bak     #备份源
```
 
```
#中国科技大学
sudo sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list
#163网易云
sudo sed -i 's/deb.debian.org/mirrors.163.com/g' /etc/apt/sources.list
#阿里云
sudo sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list
```

```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

```
#配置gpg密钥
sudo mkdir -m 0755 -p /etc/apt/keyrings

sudo curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
 
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://mirrors.ustc.edu.cn/docker-ce/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo service docker start
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://4ymyo4p4.mirror.aliyuncs.com",
                                   "https://docker.m.daocloud.io",
        "https://dockerproxy.com",
        "https://docker.mirrors.ustc.edu.cn",
        "https://docker.nju.edu.cn"]
}
EOF
```

```
sudo service docker restart
sudo docker run hello-world
sudo docker ps
docker pull portainer/portainer-ce
docker volume create portainer_data 
docker run -d --name portainer -p 9000:9000 --restart=always \-v /var/run/docker.sock:/var/run/docker.sock \-v portainer_data:/data  portainer/portainer-ce
```