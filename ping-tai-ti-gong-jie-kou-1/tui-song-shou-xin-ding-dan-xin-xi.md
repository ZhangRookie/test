---
description: 机构发送用户确认借款数据
---

# 确认借款接口

### 1.请求路径

/confirmLoanOrder

### 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 机构订单唯一编号\(平台第三方订单号\) |

### 3. 响应参数

> 此接口无特殊响应参数要求，按响应示例返回即可。

### 4.请求示例

```text
{
    ua:"YBQB_PARTNER_XL",
    args: { 
       "orderNo": "1712200000001"
    },
    sign:"{签名规则参考 接口请求签名章节}",
    timeStamp:"1500693926"
}

```

### 5.响应示例

```text
{
  status: 1,
  message: "success",
  data:null
}
```

### 6.异常示例

1. status 为非1时，均为异常情况，message 返回失败原因
2. 推送失败或status异常时不再进行重推，自动将订单完结。

