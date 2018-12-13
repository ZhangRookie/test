---
description: 此接口为基于页面跳转的还款流程提供支持
---

# 订单还款展期H5

## 1.机构还款跳转地址

任意支持GET参数的可直接请求的web地址即可。 示例如：http://ybqb.zetafin.cn/index-ug

## 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 借款订单唯一编号 |
| sign | string | 是 | 签名:订单号 |
| returnUrl | String | 否 | 机构还款完成后的回跳平台地址 |

## 3.返回参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| repayUrl | String | 是 | 用户还款\(展期\)链接 |

## 4.响应示例

```text
{
    status: 1,
    message: "success",
    data: {
        "repayUrl": "http://ybqb.zetafin.cn/index-ug?orderNo=170808000016&sign=ef6852278c1445930290c127b0454965",
    }
}
```

