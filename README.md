# surge-rules

个人 Surge 规则集，按 App 分目录组织。

## 目录结构

```
rule/Surge/<App名>/<App名>.list
```

每个 App 一个独立规则文件，格式：

```
# NAME: <App名>
# AUTHOR: Rulify
# REPO: https://github.com/gaoda212/surge-rules
# UPDATED: <时间>
# DOMAIN: <精确域名条数>
# DOMAIN-SUFFIX: <后缀条数>
# TOTAL: <总数>
```

## 引用方式

在 Surge Profile 的 `[Rule]` 段：

```ini
RULE-SET,<规则集raw地址>,<策略名>
```

例：

```ini
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/微信/微信.list,DIRECT
```

> ⚠️ 本仓库为 **Private**，raw 链接需带 token 才能访问。
> 若要让 Surge 直接引用，需改为 public。

## 覆盖范围

Apple 全家桶、Telegram、WhatsApp、Instagram、Reddit、Spotify、TikTok、YouTube、
X、ChatGPT、微信、抖音、Bilibili、高德地图、中国农业银行、比亚迪 等 46 个 App。
