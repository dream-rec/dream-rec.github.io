### 懒人配置
```
www.visa.com:80#lazy
cis.visa.com:8080#lazy
africa.visa.com:8880#lazy
www.visa.com.sg:2052#lazy
www.visaeurope.at:2082#lazy
www.visa.com.mt:2086#lazy
qa.visamiddleeast.com:2095#lazy
usa.visa.com:443#lazy
myanmar.visa.com:8443#lazy
www.visa.com.tw:2053#lazy
www.visaeurope.ch:2083#lazy
www.visa.com.br:2087#lazy
www.visasoutheasteurope.com:2096#lazy
```
### 反向代理（9）
```
proxyip:
ts.hpc.tw
workers.cloudflare.cyou
cdn.xn--b6gac.eu.org
cdn-all.xn--b6gac.eu.org
bestproxy.onecf.eu.org

```

### 一、Cloudfare官网 
官方链接: https://dash.cloudfare.com/
###  二、UUID在线生成网站 
地址: https://uutool.cn/uuid/ 
### 三、反代cf域名 
```
edgetunnel.anycast.eu.org 
cdn-all.xn--b6gac.eu.org 
cdn.xn--b6gac.eu.org 
cdn-b100.xn--b6gac.eu.org cdn.anycast.eu.org 
cdn-all.xijingping.link 
```
### 四、ip地址查询 
官方链接: https://ipdata.co/ 
官方链接: https://ip.gs/ 
### 五、fofa官网 
官方链接: https://fofa.info/ 
### 六、筛选语句: 
server=="cloudflare" && port=="443" && country=="US" && city=="Los Angeles"
### 七、配合测速脚本
**CloudflareST
IPDB#便捷获取**

### 示例CF官网域名和各端口
**// http_ip**
```
let IP1 = 'www.visa.com'
let IP2 = 'cis.visa.com'
let IP3 = 'africa.visa.com'
let IP4 = 'www.visa.com.sg'
let IP5 = 'www.visaeurope.a'
let IP6 = 'www.visa.com.mt'
let IP7 = 'qa.visamiddleeast.com'
```

**// https_ip**
```
let IP8 = 'usa.visa.com'
let IP9 = 'myanmar.visa.com'
let IP10 = 'www.visa.com.tw'
let IP11 = 'www.visaeurope.ch'
let IP12 = 'www.visa.com.br'
let IP13 = 'www.visasoutheasteurope.com'
```

**// http_port，notls**
```
let PT1 = '80'
let PT2 = '8080'
let PT3 = '8880'
let PT4 = '2052'
let PT5 = '2082'
let PT6 = '2086'
let PT7 = '2095'
```

**// https_port，tls**
```
let PT8 = '443'
let PT9 = '8443'
let PT10 = '2053'
let PT11 = '2083'
let PT12 = '2087'
let PT13 = '2096'
```

### 精选CF,PROXY-IP

- Best cf = bestcf.onecf.eu.org
- Best proxy = bestproxy.onecf.eu.org
- Best 9proxy = my-telegram-is-herocore.onecf.eu.org