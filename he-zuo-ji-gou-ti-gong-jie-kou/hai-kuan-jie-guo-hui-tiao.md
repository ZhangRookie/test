---
description: 用户在合作机构完成还款后需调用本接口通知平台。 包括扣款成功、扣款失败、扣款失败原因、扣款类型（还款扣款，展期扣款）
---

# 还款结果回调

## 请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| repayesult | string | 是 | 还款结果状态 |
| updatedAt | string | 是 | 状态变更时间\(10位时间戳\) |
| failReason | string | 否 | 还款失败原因描述 |

## 请求示例

```text
"orderNo":"245132241561415",
"repayResult":"401",
"updatedAt": "1500762721",
"failReason": "账户余额不足，无法完成扣款操作。"
```

## 响应示例

```text
{
    status: 1,
    message: "success",
    data: null
}
```

