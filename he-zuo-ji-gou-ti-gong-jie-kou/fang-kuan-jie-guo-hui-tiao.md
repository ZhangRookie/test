---
description: 平台对用户借款进行放款之后，将放款结果通知给合作机构
---

# 放款结果回调

## 请求参数 {#请求参数}

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| lendingStatus | integer | 是 | 放款状态 |
| failReason | string | 是 | 放款失败的说明信息 |
| updatedAt | string | 是 | 订单状态变更时间\(10位时间戳\) |

## 请求示例

```text
"orderNo":"245132241561415",
"lendingStatus":"200",
"failReason": "ok"
"updatedAt":"1500387486",
```

## 响应示例 {#响应示例}

```text
{
    status: 1,
    message: "success",
    data: null
}
```

## 放款状态列表

| lending\_status | 状态值 |
| :--- | :--- |
| 200 | 放款成功 |
| 401 | 放款失败 |

