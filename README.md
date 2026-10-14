# Surge 规则集

个人 Surge 分流规则集。

## 目录结构

```
rules/      自建分流规则集
```

## 规则集说明

`rules/custom.list` —— 自建分流规则，按用途分区：

- **必走代理的服务**：AI 服务、代码托管
- **走 R2S 回程**：国内流媒体、订阅拉取
- **特殊直连**：延迟测试域名
- **自定义拦截**：按需添加

## 引用方式

在 Surge Profile 的 `[Rule]` 段：

```ini
RULE-SET,<规则集地址>,<策略名>
```

## 策略组

| 策略名 | 含义 |
|---|---|
| `Proxy` | 选择型，默认 🇺🇸MEGABOX-PRO |
| `SNTP` | 智能选择 |
| `🇨🇳Home_R2S` | Tailscale 回程走 R2S |
| `DIRECT` | 直连 |
| `REJECT` / `REJECT-DROP` | 拦截 |
