# surge-rules

个人 Surge 规则集，按 App 分目录。

## 规则集

| App | 文件 | 规则数 |
|---|---|---|
| Bilibili | `rule/Surge/Bilibili/Bilibili.list` | 15 |
| WeChat | `rule/Surge/WeChat/WeChat.list` | 19 |
| Douyin | `rule/Surge/Douyin/Douyin.list` | 29 |

## 引用方式

在 Surge Profile 的 `[Rule]` 段：

```ini
RULE-SET,<规则集地址>,<策略名>
```

实测可用地址：

```ini
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/Bilibili/Bilibili.list,香港节点
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/WeChat/WeChat.list,DIRECT
RULE-SET,https://raw.githubusercontent.com/gaoda212/surge-rules/main/rule/Surge/Douyin/Douyin.list,DIRECT
```

> 策略名按你自己的策略组填（DIRECT / Proxy / 各节点组等）。

## 文件格式

```
# NAME: <App名>
# AUTHOR: Rulify
# REPO: https://github.com/gaoda212/surge-rules
# UPDATED: <时间>
# DOMAIN: <精确域名条数>
# DOMAIN-SUFFIX: <后缀条数>
# TOTAL: <总数>
```

## 注意

`rule/Surge/` 下的文件由规则同步功能自动生成，会覆盖式更新。
不要在此目录手动修改，以免被下次同步覆盖。
