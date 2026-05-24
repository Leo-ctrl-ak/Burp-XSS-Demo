# 渗透测试报告：DVWA 反射型 XSS (Low)

## 测试者
[Leo]

## 测试时间
2026-05-24

## 目标
http://localhost/DVWA/vulnerabilities/xss_r/

## 测试过程
1. 验证 DVWA 安全等级为 Low。
2. 在输入框提交 Payload：`<script>alert(1)</script>`。
3. 使用 Burp Suite 抓包，发送到 Repeater。
4. 在 Repeater 中发送请求，响应状态码为 200。
5. 在 `Render` 标签下，页面执行了脚本。

## 结论
DVWA 在 Low 安全等级下存在反射型 XSS 漏洞。