---
description: 本接口主要目的是过滤机构黑名单用户以及一些基础风控规则的预拦截
---

# 用户过滤接口

机构在导流的过程中将首先根据平台所需的用户客群条件进行筛客，符合筛客条件的人群将会调用此接口进行准入判断

## 1.请求路径

/userAccept

## 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :---: | :--- | :--- |
| userName | String | 是 | 用户姓名 |
| userPhone | String | 是 | 用户手机号（掩后3位） |
| userIdCard | String | 是 | 用户身份证号码（掩后4位） |

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| result | integer | 是 | 借款权限 |
| amount | integer | 是 | 可贷额度 |
| minAmount | integer | 否 | 最小可贷额度 |
| terms | array\[integer\] | 是 | 可贷期限 |
| remark | tring | 否 | 其他原因拒绝借款时，此字段说明 |
| canLoanTime | string | 否 | 告知用户在什么时候才可以借款，精确到天 |



## 4.请求示例 <a id="&#x8BF7;&#x6C42;&#x793A;&#x4F8B;"></a>

```text
"user_name": "刘先森",
"user_phone": "13245678***",
"user_idcard": "61012119000109****"
```

## 5.准入响应示例 <a id="&#x51C6;&#x5165;&#x54CD;&#x5E94;&#x793A;&#x4F8B;"></a>

```text
{
    status: 1,
    message: "success",
    response: {
        "result": 200,
        "amount": 100000,
        "min_amount": 100000,
        "terms": [7]
    }
}
```

## 6.在贷拒绝准入响应示例 <a id="&#x5728;&#x8D37;&#x62D2;&#x7EDD;&#x51C6;&#x5165;&#x54CD;&#x5E94;&#x793A;&#x4F8B;"></a>



```text
{
    status: 1,
    message: "success",
    data: {
        "result": 401,
        "canLoanime": "2018-10-01"
    }
}
```

## 7.其他原因拒绝准入响应示例 <a id="&#x5176;&#x4ED6;&#x539F;&#x56E0;&#x62D2;&#x7EDD;&#x51C6;&#x5165;&#x54CD;&#x5E94;&#x793A;&#x4F8B;"></a>

```text
{
    status: 1,
    message: "success",
    data: {
        "result": 505,
        "can_loan_time": "2017-12-01",
        "remark": "您之前的借款订单未通过审核，2017年12月01日可再次申请。"
    }
}
```

## 8.借款权限列表 <a id="&#x501F;&#x6B3E;&#x6743;&#x9650;&#x5217;&#x8868;"></a>

| result | 说明 |
| :--- | :--- |
| 200 | 可以借款 |
| 301 | 用户年龄过大或过小 |
| 401 | 用户在机构有未完成的借款 |
| 402 | 用户在机构有不良借款记录 |
| 403 | 该用户是征信系统黑名单用户 |
| 505 | 其他原因，禁止用户借款。需在备注说说明原因 |



