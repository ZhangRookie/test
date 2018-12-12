---
description: 合作机构对用户借款申请进行审核之后，将具体可申请金额和审批结果通过本接口推送给平台
---

# 审批结果回调

### 1.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderSn | string | 是 | 订单唯一编号 |
| approveStatus | string | 是 | 审批状态 |
| approveAmount | string | 是 | 审批后的可借金额单位（分） |
| approveTerm | string | 是 | 审批后的可借周期 |
| termType | string | 是 | 1:按天; 2：按月; 3：按年 |
| approveRemark | string | 是 | 审批状态备注 |
| canLoanTime | string | 是 | 可以再次申请借款的时间，此时间之前将不在请求用户过滤接口。值如：2017-03-29 08:00:00 |
| updatedAt | string | 是 | 订单状态变更时间\(10位时间戳\) |

### 2.请求示例

```text
 "orderSn": "245132241561415",
    "approveStatus": "200",
    "approveAmount": "150000",
    "approveTerm": "3",
    "termType": "2",
    "approveRemark": "ok",
    "canLoanTime": "2017-12-29 08:00:00",
    "updatedAt":"1500387486"
```

### 3.响应示例



```text
{
    status: 1,
    message: "success",
    response: null
}
```

### 4.审批状态列表 <a id="&#x5BA1;&#x6279;&#x72B6;&#x6001;&#x5217;&#x8868;"></a>

| approve\_status | 状态值 |
| :--- | :--- |
| 200 | 审批通过 |
| 403 | 审批拒绝 |

