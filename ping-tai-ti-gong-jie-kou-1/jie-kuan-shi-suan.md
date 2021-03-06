---
description: 展示功能：在客户端用户选择借款金额和借款期限时，显示相应的到账金额、每期应还总额、服务费、费用描述等信息。
---

# 借款试算

## 1.请求路径

```text
/trialCalculation
```

##  2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| loanAmount | integer | 是 | 审批金额 单位（分\) |
| loanTerm | integer | 是 | 审批期限 |
| termType | integer | 是 | 1:按天; 2：按月; 3：按年 |

3.响应参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| serviceFee | object or integer | 是 | 服务费，单位: 分，例如：{"min": 10000, "max": 13000} or 10000 |
| serviceFeeDesc | string | 是 | 服务费说明，例如：包含30%风控服务费， 40%信息认证费 |
| interestFee | object or integer | 是 | 利息 |
| receiveAmount | object or integer | 是 | 到账金额 |
| repayAmount | object or integer | 是 | 应还总额 |
| repayPlan | array | 是 | 预计还款计划, 数组内每个元素数据结构如下表。 |

说明:   
　以上凡为 object or integer 类型的参数, 均可以支持两种数据格式。  
　　格式一: integer 类型固定值, 如: 15000  
　　格式二: object 类型浮动值, 如: {"min": 10000, "max": 13000}  


### 2.1 repayPlan 预计还款计划说明

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| periodNo | integer | 是 | 期号 |
| repayAmount | integer | 是 | 本期应还金额，单位: 分，例如：{"min": 100000, "max": 130000} or 100000 |
| repayAmountDesc | string | 是 | 本期应还金额描述 |

## 3. 请求示例

```text
{
    ua:"YBQB_PARTNER_XL",
    args: { 
       "loanAmount":150000,
       "loanTerm":3,
       "termType":3   
      },
    sign:"{签名规则参考 接口请求签名章节}",
    timeStamp:"1500693926"
}
```

## 4.响应示例

```text
{
    "status": 1,
    "message": "success",
    "response": {
        "serviceFee" : 6000,
        "serviceFeeDesc" : "包含30%风控服务费， 40%信息认证费",
        "interestFee" : {"min": 900, "max": 1500},
        "receiveAmount" : 150000,
        "repayAmount" : {"min": 156900, "max": 157500},
        "repayPlan" : [ 
            {
              "repayAmount": {"min": 52300, "max": 52500},
              "repayAmountDesc": "本金500元，利息3~5元，服务费20元",
              "periodNo": 1
            }
        ]
    }
}
```

