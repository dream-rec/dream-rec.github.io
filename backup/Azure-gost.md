### 1. git clone下载
`git clone https://github.com/dream-rec/haoel.github.io.git`
### 2. 进入子文件夹，运行脚本
```
cd haoel.github.io/scripts
ls
./install.ubuntu.18.04.sh
```
### 3. 执行1-4，8，9退出
### 4. 开放vps-443和80端口
### 5. 运行gost
```
sudo docker ps -a
sudo docker start container-id
```
### 6. 检查SSL证书是否存在
```
sudo docker inspect container-id | grep log
sudo cat log-path
#如果出现no such file证明无SSL证书，需要重新生成
```
### 7. 测试代理是否连接成功
`curl -v "https://www.google.com" --proxy "https://DOMAIN" --proxy-user 'USER:PASS'`

---

### config.yaml样例
```
port: 7890
socks-port: 7891
redir-port: 7892
mixed-port: 7893
ipv6: true
allow-lan: true
mode: Rule
log-level: silent
external-controller: "127.0.0.1:55769"
secret: ""
tun:
  enable: true
  stack: system
  dns-hijack:
    - tcp://8.8.8.8:53
    - udp://8.8.8.8:53
dns:
  enable: true
  ipv6: true
  listen: 0.0.0.0:53
  default-nameserver:
    - 114.114.114.114
  enhanced-mode: fake-ip
  fake-ip-range: 198.18.0.1/16
  nameserver:
    - 114.114.114.114
    - 223.5.5.5
  fallback:
    - 114.114.114.114

proxies:
  - name: "azure"
    type: http
    server: yourdomain
    port: 443
    username: name
    password: "pwd"
    tls: true
    skip-cert-verify: true

proxy-groups:
  - name: "Proxy"
    type: select
    proxies:
      - azure

rules:
  - DOMAIN-SUFFIX,local,DIRECT
  - IP-CIDR,127.0.0.0/8,DIRECT
  - IP-CIDR,172.16.0.0/12,DIRECT
  - IP-CIDR,192.168.0.0/16,DIRECT
  - IP-CIDR,10.0.0.0/8,DIRECT

  - DOMAIN-SUFFIX,deepl.com,DIRECT

  - GEOIP,CN,DIRECT
  - MATCH,Proxy

```

