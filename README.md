# surge-rules

个人 Surge 规则集。

## 目录结构

```
rule/Surge/<App名>/<App名>.list
```

保留的规则集：

| App | 文件 | 规则数 |
|---|---|---|
| Bilibili | `rule/Surge/Bilibili/Bilibili.list` | 见文件头 |
| 微信 | `rule/Surge/微信/微信.list` | 见文件头 |
| 抖音 | `rule/Surge/抖音/抖音.list` | 见文件头 |

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

## 注意

`rule/Surge/` 下的文件由**规则同步功能自动生成**，会覆盖式更新。
不要在此目录手动修改，以免被下次同步覆盖。
