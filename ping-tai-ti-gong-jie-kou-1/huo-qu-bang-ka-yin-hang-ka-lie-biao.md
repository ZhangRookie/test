---
description: 此接口用户获取平台所支持的银行列表
---

# 获取支持卡银行卡列表

### 1.请求路径

/getValidBankList

### 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| cardType | string | 是 | 银行卡类型 1 信用卡 2 借记卡\(目前只支持借记卡\) |

### 3.返回参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| bankName | string | 是 | 银行简称 |
| bankCode | string | 是 | 银行代码 |

### 4. 请求示例

```text
{
    ua:"YBQB_PARTNER_XL",
    args: { 
        "cardType": "2", 
    },
    sign:"{签名规则参考 接口请求签名章节}",
    timeStamp:"1500693926"
}
```

### 5. 响应示例

```text
{
    status: 1,
    message: "success",
    data: [
        {
            "bankName": "工商银行",
            "bankCode": "ICBC"
        },
        {
            "bankName": "中国银行",
            "bankCode": "BOC"
        }
    ]
}
```

### 6. 银行Code映射关系

| 银行名称 | 银行编号 |
| :--- | :--- |
| 工商银行 | ICBC |
| 中国建设银行 | CCB |
| 中国银行 | BOC |
| 交通银行 | BCOM |
| 兴业银行 | CIB |
| 中信银行 | ECITIC |
| 平安银行 | PINGAN |
| 上海银行 | SHB |
| 浦发银行 | SPDB |



