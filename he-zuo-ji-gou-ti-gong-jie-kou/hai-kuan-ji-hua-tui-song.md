---
description: 平台放款成功、展期、逾期、还款成功后向合作机构推送还款计划，用户根据还款计划详情查询借款详情与还款详情展示
---

# 还款计划推送

## 请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

> 整体请求参数结构说明
>
> | 参数 | 类型 | 是否必选 | 描述 |
> | :--- | :--- | :--- | :--- |
> | orderNo | string | 是 | 订单唯一编号 |
> | totalAmount | integer | 是 | 还款总额; 单位: 分 |
> | totalSvcFee | integer | 是 | 总服务费; 单位: 分 |
> | receivedAmount | integer | 是 | 到账金额; 单位: 分 |
> | alreadyPaid | integer | 是 | 已还金额; 单位: 分 |
> | totalPeriod | integer | 是 | 总期数 |
> | finishPeriod | integer | 是 | 已还期数 |
> | repaymentPlan | array | 是 | 具体还款计划数组 |
>
> repaymentPlan 内元素结构说明
>
> | 参数 | 类型 | 是否必选 | 描述 |
> | :--- | :--- | :--- | :--- |
> | periodNo | string | 是 | 还款期号 |
> | principle | integer | 是 | 本期还款本金; 单位: 分 |
> | interest | integer | 是 | 本期还款利息; 单位: 分 |
> | serviceFee | integer | 是 | 本期服务费用; 单位: 分 |
> | billStatus | integer | 是 | 本期账单状态; -1: 未出账; 0: 待还款; 1: 已还款 |
> | totalAmount | integer | 是 | 本期还款总额; 单位: 分 |
> | alreadyPaid | integer | 是 | 本期已还金额; 单位: 分 |
> | loanTime | integer | 是 | 实际起息时间\(10位时间戳\) |
> | dueTime | integer | 是 | 最迟还款时间（10位时间戳，精确到秒超过该时间就算逾期） |
> | canPayTime | integer | 是 | 可以还款时间\(10位时间戳\) |
> | finishPayTime | integer | 是 | 实际完成还款时间\(10位时间戳\) |
> | overdueDay | integer | 是 | 逾期天数 |
> | overdueFee | integer | 是 | 逾期费用; 单位: 分 |
> | periodFeeDesc | string | 是 | 本期费用描述 |
> | payType | integer | 是 | 还款支付方式; 如: 0.未还款 1. 主动还款 2.系统扣款 3. 支付宝转账 4. 银行转账或其它方式 |

## 请求示例

```text
        "order_sn":"245132241561415",    
        "total_amount": 465000,  
        "total_svc_fee": 15000,   
        "received_amount": 465000,   
        "already_paid": 155000,    
        "total_period": 3,
        "finish_period": 1,
        "repayment_plan":[
            {
                "period_no": "1",
                "principle": 150000,
                "interest": 1000,
                "service_fee":4000,
                "bill_status": 1, 
                "total_amount": 153400,
                "already_paid": 150000,
                "loan_time": 1500387486, 
                "due_time": 1500787486,
                "can_pay_time": 1500762721,
                "finish_pay_time": 1503354721,
                "overdue_day": 2,
                "overdue_fee": 3400,
                "period_fee_desc": "三月还款费用明细", 
                "pay_type": 1
            },{
                "period_no": "2",
                "principle": 150000,
                "interest": 1000,
                "service_fee":4000,
                "bill_status": 0, 
                "total_amount": 150000,
                "already_paid": 0,
                "loan_time": 1500387486, 
                "due_time": 1500787486,
                "can_pay_time": 1500762721,
                "finish_pay_time": 0,
                "overdue_day": 0,
                "overdue_fee": 0,
                "period_fee_desc": "四月还款费用明细",  
                "pay_type": 0 
            },{
                "period_no": "3",
                "principle": 150000,
                "interest": 1000,
                "service_fee":4000,
                "bill_status": -1, 
                "total_amount": 150000,
                "already_paid": 0,
                "loan_time": 1500387486, 
                "due_time": 1500787486,
                "can_pay_time": 1500762721,
                "finish_pay_time": 0,
                "overdue_day": 0,
                "overdue_fee": 0,
                "period_fee_desc": "五月还款费用明细", 
                "pay_type": 0
            }
        ]
    }
```

## 响应示例

```text
{
    status: 1,
    message: "success",
    response: null
}
```
