# Surge Rules

个人 Surge 分流 / 隐私封锁规则集。

| 规则集 | 规则数 | 文件 |
|---|---|---|
| AdTracker | 13 | [rule/Surge/AdTracker/AdTracker.list](rule/Surge/AdTracker/AdTracker.list) |
| WPS | 39 | [rule/Surge/WPS/WPS.list](rule/Surge/WPS/WPS.list) |
| TencentMeeting | 16 | [rule/Surge/TencentMeeting/TencentMeeting.list](rule/Surge/TencentMeeting/TencentMeeting.list) |

## 订阅地址

```
https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/AdTracker/AdTracker.list
https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/WPS/WPS.list
https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/TencentMeeting/TencentMeeting.list
```

## 引用方式

```ini
[Rule]
# 广告/追踪封锁，全 REJECT，无业务域，放前面
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/AdTracker/AdTracker.list,REJECT
```

## 使用注意

- **AdTracker**：全为 `REJECT`，不含 `DIRECT`，无业务域，放在规则列表前部即可（建议在 `adrules` 之前）。
  来源是 Surge 漏网流量的统计结果 —— 2675 条漏网记录中 **82.8% 是一次性随机域名**
  （如 `efuqpkalqw.com`），这类域名规则拦不住，本文件只收录稳定可复现的域名。
- **WPS / TencentMeeting** 均含 `REJECT` 与 `DIRECT`，**必须放在 `ChinaMax` 等国内规则集之前**引用：
  - WPS：含 2 条 `IP-CIDR` 封锁内置 HTTPDNS 绕过（`120.92.33.171`、`159.138.83.72`），
    以及业务域 `wpscdn.com` / `kdocs.cn` / `wpsdns.com` 等 `DIRECT`，防止被 ChinaMax 误杀。
  - TencentMeeting：含 `IP-CIDR,162.14.0.0/16,DIRECT,no-resolve`（媒体转发 14000 端口），
    以及业务域 `meeting.tencent.com` / `meeting.qq.com` 等 `DIRECT`。

## 备注

Surge 的 `DOMAIN-SUFFIX` 只匹配完整标签：`xxx-datadoghq.com` 与 `datadoghq.com` 是**不同域**，
必须单独列（见 AdTracker 中的 `browser-intake-us5-datadoghq.com`）。
