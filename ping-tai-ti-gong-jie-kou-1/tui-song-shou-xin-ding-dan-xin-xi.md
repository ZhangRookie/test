---
description: 用户在产品详情页，并且获得了授信额度，平台将向机构推送订单信息
---

# 确认借款接口

## 1.请求路径

/pushCreditOrder

## 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 机构订单唯一编号\(平台第三方订单号\) |
| loanAmount | string | 是 | 借款金额\(单位:分\) |

## 3. 响应参数 <a id="&#x54CD;&#x5E94;&#x53C2;&#x6570;"></a>

> 此接口无特殊响应参数要求，按响应示例返回即可。

## 4.请求示例

```text
"orderNo": "1712200000001",
"userName": "宋先生",
"userMobile":"13812345678",
"userIdCard":"123212199001011234",
"loan_amount": "100000",
"loanTerm": 1
```

## 5.响应示例

```text
{
  status: 1,
  message: "success",
  data: {
      "code":200,
      "msg":"success"
  }
}
```

## 6.异常示例 <a id="&#x5F02;&#x5E38;&#x793A;&#x4F8B;"></a>

1. status 为非1时，均为异常情况，message 返回失败原因
2. 推送失败或status异常时不再进行重推，自动将订单完结。

