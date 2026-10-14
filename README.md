# Surge 规则集

个人 Surge 分流规则与配置备份。

## 目录结构

```
rules/      自建分流规则集（.list / .conf）
profiles/   Surge Profile 备份（Mac / iOS）
docs/       说明文档
scripts/    相关脚本
```

## 规则集用法

在 Surge Profile 的 `[Rule]` 段引用：

```ini
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rules/<文件名>.list,<策略名>
```

> 注意：本仓库是 **Private**，raw 链接需要带 token 才能访问。
> 若要公开引用，需把仓库改为 public，或用带 token 的代理地址。

## 当前 Profile 使用的规则源（供参考）

| 规则集 | 用途 | 来源 |
|---|---|---|
| `adrules.list` | 广告拦截 | https://adrules.top/adrules.list |
| `Apple-AI.list` | Apple AI 服务走代理 | RocM301/Apple-Rule |
| `Apple.lsr` | Apple 域名 | rule.kelee.one |
| `BiliBili.lsr` | B站走 R2S 回程 | rule.kelee.one |
| `ChinaMax.lsr` | 国内域名 REJECT | rule.kelee.one |
| `LAN` | 局域网直连 | 内置 |

## 策略组约定

| 策略名 | 含义 |
|---|---|
| `Proxy` | 选择型，默认 🇺🇸MEGABOX-PRO |
| `SNTP` | 智能选择（排除 🇺🇸 节点） |
| `🇨🇳Home_R2S` | Tailscale 回程走 R2S |
| `DIRECT` | 直连 |
| `REJECT` / `REJECT-DROP` | 拦截 |
