---
description: 此接口用户获取平台所支持的银行列表
---

# 获取支持卡银行卡列表

## 1.请求路径

/getValidBankList

## 2.请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

> 此接口无请求参数

## 3. 请求示例 <a id="&#x8BF7;&#x6C42;&#x793A;&#x4F8B;"></a>



## 4. 响应示例 <a id="&#x54CD;&#x5E94;&#x793A;&#x4F8B;"></a>

```text
{
    status: 1,
    message: "success",
    response: [
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

## 5. 银行Code映射关系 <a id="&#x94F6;&#x884C;code&#x6620;&#x5C04;&#x5173;&#x7CFB;"></a>

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



