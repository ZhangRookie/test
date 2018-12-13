---
description: 合作机构需与一本钱包平台索取唯一：ua 与 key
---

# 签名规则

### 1.签名生成规则：

1. 利用ua与key拼装生成signKey `$signKey = "{$ua}{$key}{$ua}"`
2. 将请求数据转换成json字符串 `$args = json_encode($requestArgs)`
3. 结合signKey、call、args 生成签名：`$sign = md5("{$signKey}{$call}{$signKey}{$args}{$signKey}")`

