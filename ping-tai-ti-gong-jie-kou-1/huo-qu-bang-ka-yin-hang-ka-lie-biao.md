---
description: 此接口用户获取平台所支持的银行列表
---

# 获取支持卡银行卡列表

### 1.请求路径

/getValidBankList

### 2.请求参数

> 此接口无请求参数

### 3. 请求示例



### 4. 响应示例

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

### 5. 银行Code映射关系

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



