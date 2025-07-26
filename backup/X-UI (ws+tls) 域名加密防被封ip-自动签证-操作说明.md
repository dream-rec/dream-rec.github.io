# 使用 x-ui 搭建 Trojan(可替换其他类型) WS TLS 节点

**发布时间**: May 27, 2025

## 🌐 日志：使用 x-ui 搭建 Trojan TLS 节点（含域名证书配置）

**面板工具**：[https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh]
**目标域名**：`us.example.com`

---

## 🧩 第一步：更新系统、安装证书工具

```bash
sudo apt update
sudo apt install certbot python3-certbot-nginx -y
```

> 说明：`certbot` 用于签发 Let's Encrypt 证书，`python3-certbot-nginx` 插件让它能自动配置 Nginx。

---

## 🌐 第二步：为域名申请 HTTPS 证书

```bash
sudo certbot --nginx -d us.example.com
```

> **重要提醒**：
> - 请确保你的域名已经解析到当前 VPS 公网 IP，DNS添加A记录指向公网IPV4地址。
> - 请确保服务器的 80 和 443 端口已开放。部分 VPS 提供商要求不仅在系统内部（如通过 ufw 或 firewalld）放行端口，还需在云平台的 VPC 网络安全组 或 防火墙策略 中手动添加相应的入站规则，否则外部访问可能被阻断。
> - 如果申请成功，证书和密钥默认保存在：  
>   `/etc/letsencrypt/live/us.example.com/fullchain.pem`  
>   `/etc/letsencrypt/live/us.example.com/privkey.pem`

---

## ⚙️ 第三步：安装 Trojan 多协议面板 x-ui

```bash
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

安装完成后，运行：

```bash
x-ui
```

默认管理面板地址：`http://你的服务器IP:54321`，首次进入需设置用户名和密码。

---

## 🔐 第四步：添加 Trojan 节点配置（WebSocket + TLS）

打开浏览器，访问 x-ui 管理面板，添加一个新的入站配置，建议选择 **Trojan 类型**。

### 基本设置：

- **入站类型**：Trojan（支持 TLS）
- **端口**：建议使用 `443`、`8443` 或其他自定义端口，CF支持的HTTPS端口
- **SNI（Server Name Indication）**：填写你的域名，例如 `us.example.com`
- **密码（Password）**：用户连接所需的认证密码，自行设置，务必保密
- **请求头**：添加HOST类型，值对应域名us.example.com，下侧域名同理

### 证书配置：

**证书文件路径**：
```
/etc/letsencrypt/live/us.example.com/fullchain.pem
```

**私钥文件路径**：
```
/etc/letsencrypt/live/us.example.com/privkey.pem
```

### 其他可选项：

- ✅ 启用 TLS（必须勾选）
- ✅ 可选启用：
  - WebSocket（更强的混淆性）
  - Reality（无需证书的新协议，适合对抗 DPI）
  - gRPC（某些设备表现更佳）


## 📦 第五步：客户端连接

导出配置（二维码或 JSON），导入到：

- **Windows**: V2RayN / NGUI
- **iOS**: Shadowrocket / Kitsunebi
- **Android**: v2rayNG / Clash Meta

确保客户端使用域名连接，启用 TLS，验证 SNI 字段一致。

---

## 🔁 第六步：证书自动续期

certbot 默认自动续期，你可以手动测试：

```bash
sudo certbot renew --dry-run
```

---

## ✅ 总结

| 工具 | 作用 |
|------|------|
| `certbot` | 免费 HTTPS 证书 |
| `x-ui` | 可视化管理 Trojan / VLESS 等协议 |
| `nginx` | 用于证书申请，不参与代理功能 |
| `Let's Encrypt` | 提供 90 天有效期免费证书 |

