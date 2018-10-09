---
description: 推单完成后用户进行绑定银行卡操作，将具体的绑卡结果通过本接口推送给合作机构
---

# 绑卡结果回调

## 请求参数 {#请求参数}

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 否 | 订单唯一编号 |
| bindStatus | string | 是 | 绑卡结果状态; 参考订单绑卡接口 状态码 |
| bankCode | string | 是 | 绑卡银行编码 |
| bankName | string | 是 | 绑卡银行名称 |
| userName | string | 是 | 用户姓名 |
| userIdCard | string | 是 | 用户身份证号 |
| echoData | string | 是 | 回显数据字段, 此字段的数据来源于机构绑卡接口\(或H5\)的请求参数中，原样回传即可 |
| cardNumber | string | 是 | 银行卡号 |
| cardPhone | string | 是 | 银行预留手机号 |
| userPhone | string | 是 | 用户准入时的明文手机号 |

## 请求示例

```text
"order_sn":"245132241561415",
"bind_status":"200",
"bank_code":"ICBC",
"bank_name":"工商银行",
"user_name":"张三",
"user_idcard":"610121190001011122",
"echo_data": "{pid: 123456}",
"card_number":"6222022005001212723",
"card_phone":"13245678901",
"user_phone":"13312345678"
```

## 响应示例

```text
{
    status: 1,
    message: "success",
    data: null
}
```



