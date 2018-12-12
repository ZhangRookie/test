---
description: >-
  如果合作机构有任何人为或其它行为导致订单状态与还款计划变更（如人工修改还款时间，还款金额，订单延期操作，）
  均需向平台推送最新的还款计划，推送接口详情【平台提供接口->还款计划推送】注意！注意！注意！
  没有成功放款的订单若拉取还款计划status不等于1，还款计划详情数据也无需返回。
---

# 拉取还款计划



## 1. 接口背景 <a id="&#x63A5;&#x53E3;&#x80CC;&#x666F;"></a>

1. 正常放款成功的订单，还款计划以合作机构的推送为准
2. 订单状态不一或其它异常情况时，用户手动拉取用户最新还款计划会调用本接口
3. 还款计划是订单放款成功的标识，生成还款计划意味着用户银行卡已经到账了。不管是推送还是拉取还款计划成功响应都是代表放款成功了。

## 2.请求路径

 /getRepayplan

## 3.请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |

## 4.响应参数

整体响应结果结构说明  


| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderSn | string | 是 | 订单唯一编号 |
| totalAmount | integer | 是 | 还款总额; 单位: 分 |
| totalSvcFee | integer | 是 | 总服务费; 单位: 分 |
| receivedAmount | integer | 是 | 到账金额; 单位: 分 |
| alreadyPaid | integer | 是 | 已还金额; 单位: 分 |
| totalPeriod | integer | 是 | 总期数 |
| finishPeriod | integer | 是 | 已还期数 |
| repaymentPlan | array | 是 | 具体还款计划数组 |

repaymentPlan 内元素结构说明

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| periodNo | string | 是 | 还款期号 |
| principle | integer | 是 | 本期还款本金; 单位: 分 |
| interest | integer | 是 | 本期还款利息; 单位: 分 |
| serviceFee | integer | 是 | 本期服务费用; 单位: 分 |
| billStatus | integer | 是 | 本期账单状态; -1: 未出账; 0: 未还款; 1: 已还款 |
| totalAmount | integer | 是 | 本期还款总额; 单位: 分 |
| alreadyPaid | integer | 是 | 本期已还金额; 单位: 分 |
| loanTime | integer | 是 | 实际起息时间 |
| dueTime | integer | 是 | 最迟还款时间（精确到秒超过该时间就算逾期） |
| canPayTime | integer | 是 | 可以还款时间 |
| finishPayTime | integer | 是 | 实际完成还款时间 |
| overdueDay | integer | 是 | 逾期天数 |
| overdueFee | integer | 是 | 逾期费用; 单位: 分 |
| periodFeeDesc | string | 是 | 本期费用描述 |
| payType | integer | 是 | 还款支付方式; 如: 0.未还款 1. 主动还款 2.系统扣款 3. 支付宝转账 4. 银行转账或其它方式 |

## 5.请求示例 <a id="&#x8BF7;&#x6C42;&#x793A;&#x4F8B;"></a>

```text
"orderSn":"246964109149933"
```

响应示例



```text
 {
        "orderSn":"245132241561415",    
        "totalAmount": 465000,  
        "totalSvcFee": 15000,   
        "receivedAmount": 465000,   
        "alreadyPaid": 155000,    
        "totalPeriod": 3,
        "finishPeriod": 1,
        "repaymentPlan":[
            {
                "periodNo": "1",
                "principle": 150000,
                "interest": 1000,
                "serviceFee":4000,
                "billStatus": 1, 
                "totalAmount": 153400,
                "alreadyPaid": 150000,
                "loanTime": 1500387486, 
                "dueTime": 1500787486,
                "canPayTime": 1500762721,
                "finishPayTime": 1503354721,
                "overdueDay": 2,
                "overdueFee": 3400,
                "periodFeeDesc": "三月还款费用明细", 
                "payType": 1
            },{
                "periodNo": "2",
                "principle": 150000,
                "interest": 1000,
                "serviceFee":4000,
                "billStatus": 0, 
                "totalAmount": 150000,
                "alreadyPaid": 0,
                "loanTime": 1500387486, 
                "dueTime": 1500787486,
                "canPayTime": 1500762721,
                "finishPayTime": 0,
                "overdueDay": 0,
                "overdueFee": 0,
                "periodFeeDesc": "四月还款费用明细",  
                "payType": 0 
            },{
                "periodNo": "3",
                "principle": 150000,
                "interest": 1000,
                "serviceFee":4000,
                "billStatus": -1, 
                "totalAmount": 150000,
                "alreadyPaid": 0,
                "loanTime": 1500387486, 
                "dueTime": 1500787486,
                "canPayTime": 1500762721,
                "finishPayTime": 0,
                "overdueDay": 0,
                "overdueFee": 0,
                "periodFeeDesc": "五月还款费用明细", 
                "payType": 0
            }
        ]
    }
```

