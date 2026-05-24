# Burp-XSS-Demo

使用 Burp Suite 对 DVWA 靶场进行反射型 XSS 测试的实战记录。

## 环境信息
- 攻击机：Kali Linux 2026.2
- 靶机：Ubuntu 22.04 (localhost)
- Web 服务：Apache + PHP + MySQL
- 工具：Burp Suite Community v2026.2.3
- 靶场：DVWA v1.10 (Security Level: Low)

## 项目内容
- `screenshots/`：测试过程的截图（Repeater Render 页面 + HTTP history 200 状态码）
- `requests/`：从 Burp 导出的 HTTP 请求文本
- `payloads/`：成功测试过的 Payload 列表

## 操作步骤
1. 配置 Burp 代理（127.0.0.1:8080）并导入 CA 证书。
2. 登录 DVWA，将安全等级设为 Low。
3. 进入 XSS (Reflected) 页面，提交 `<script>alert(1)</script>`。
4. 在 Burp 的 HTTP history 中捕获请求，发送到 Repeater。
5. 点击 `Send`，在 `Render` 标签下观察页面。

## 结果
成功触发 XSS，页面执行了脚本，证明漏洞存在。
