# Surge Rules

个人 Surge 分流 / 隐私封锁规则集，仅保留两个 App。

| App | 规则数 | 文件 |
|---|---|---|
| WPS | 39 | [rule/Surge/WPS/WPS.list](rule/Surge/WPS/WPS.list) |
| TencentMeeting | 16 | [rule/Surge/TencentMeeting/TencentMeeting.list](rule/Surge/TencentMeeting/TencentMeeting.list) |

## 订阅地址

```
https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/WPS/WPS.list
https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/TencentMeeting/TencentMeeting.list
```

## 使用注意

两个文件均含 `REJECT` 与 `DIRECT`，**必须放在 `ChinaMax` 等国内规则集之前**引用：

- WPS：含 2 条 `IP-CIDR` 封锁内置 HTTPDNS 绕过（`120.92.33.171`、`159.138.83.72`），
  以及业务域 `wpscdn.com` / `kdocs.cn` / `wpsdns.com` 等 `DIRECT`，防止被 ChinaMax 误杀。
- TencentMeeting：含 `IP-CIDR,162.14.0.0/16,DIRECT,no-resolve`（媒体转发 14000 端口），
  以及业务域 `meeting.tencent.com` / `meeting.qq.com` 等 `DIRECT`。
