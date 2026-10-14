# Profile 备份说明

本目录存放 Surge Profile 的**脱敏备份**，用途：
- 版本管理：profile 改动留痕，可回溯、可 diff
- 灾难恢复：设备丢失/重装后可快速恢复配置骨架
- 参考查阅：查看当前分流策略与规则源

## ⚠️ 重要：文件已脱敏

仓库里的 profile **不是可直接使用的完整版**。以下字段已被替换为 `<REDACTED>`：

| 字段 | 原值 | 恢复方式 |
|---|---|---|
| `http-api` | `<密码>@0.0.0.0:6171` | 从本机 Surge 设置中查看，或重设 |
| `external-controller-access` | `<密码>@0.0.0.0:6170` | 同上 |
| `policy-path` 里的 `token` / `sign` / `nonce` | 订阅服务商签发 | 从订阅服务商页面重新获取 |

**为什么脱敏**：即使仓库是 private，把凭据写进 git 历史也有风险 ——
一旦仓库转公开、被 fork、或账号泄露，历史里的凭据会永久可查。凭据应始终留在设备本地。

## 文件对应关系

| 文件 | 来源 | 导出方式 |
|---|---|---|
| `Simple_Mac.conf` | Mac（192.168.5.55）`~/Library/Application Support/Surge/Profiles/` | 直接复制 |
| `Simple_ios.conf` | iOS 本机 | `surge-cli dump profile` 的 `originalProfile` 段 |

## 恢复步骤

1. 复制文件到设备的 Surge Profiles 目录
2. 把所有 `<REDACTED>` 填回真实值
3. 在 Surge 中切换到该 profile
4. 验证：`surge-cli status` 确认策略组和规则加载正常

## 更新备份

profile 变更后重新导出并覆盖本目录文件即可（记得脱敏）。
