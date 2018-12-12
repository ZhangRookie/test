# 还款计划查询接口

## 1. 接口背景 <a id="&#x63A5;&#x53E3;&#x80CC;&#x666F;"></a>

1. 正常放款成功的订单，还款计划以合作机构的推送为准
2. 订单状态不一或其它异常情况时，用户手动拉取用户最新还款计划会调用本接口
3. 还款计划是订单放款成功的标识，生成还款计划意味着用户银行卡已经到账了。不管是推送还是拉取还款计划成功响应都是代表放款成功了。

## 2.请求路径

 /getRepayments

## 3.请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |

## 4.响应参数

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

