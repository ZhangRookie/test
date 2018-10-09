---
description: 此接口用户获取平台所支持的银行列表
---

# 获取绑卡银行卡列表

## 1.请求路径

/getValidBankList

## 2.请求参数 {#请求参数}

> 此接口无请求参数

## 3. 请求示例 {#请求示例}



## 4. 响应示例 {#响应示例}

```text
{
    status: 1,
    message: "success",
    response: [
        {
            "bank_name": "工商银行",
            "bank_code": "ICBC"
        },
        {
            "bank_name": "中国银行",
            "bank_code": "BOC"
        }
    ]
}
```

## 5. 银行Code映射关系 {#银行code映射关系}

| 银行名称 | 银行编号 |
| :--- | :--- |
| 工商银行 | ICBC |
| 农业银行 | ABC |
| 中国银行 | BOC |
| 建设银行 | CCB |
| 交通银行 | BCOM |

