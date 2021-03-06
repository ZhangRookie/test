---
description: 用户在完成平台产品所需的所有补充认证项，机构将向平台推送订单和所需的补充信息
---

# 推送用户补充信息

## 1.请求路径

/pushUserAdditionalInfo

## 2.请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

### 2.1. 参数总览 <a id="&#x53C2;&#x6570;&#x603B;&#x89C8;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderInfo | object | 是 | 用户订单信息 |
| userAdditional | object | 是 | 用户补充信息 |

### 2.2. 参数明细 <a id="&#x53C2;&#x6570;&#x660E;&#x7EC6;"></a>

#### 2.2.1. orderInfo 用户订单信息 <a id="order_info"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| loan\_amount | string | 是 | 借款金额\(单位:分\) |
| userPhone | string | 是 | 用户明文手机号 |

####  2.2.2 userAdditional 补充信息详情 <a id="user_additional"></a>

**1\) addressBook 通讯录信息**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| phoneList | array | 否 | 通讯录列表 name\_phone |

**2\) contactInfo 紧急联系人信息**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| name | String | 是 | 第一联系人姓名 |
| mobile | String | 是 | 第一联系人手机号 |
| relation | String | 是 | 第一联系人与用户关系 |
| nameSpare | String | 是 | 第二联系人姓名 |
| mobileSpare | String | 是 | 第二联系人手机号 |
| relationSpare | String | 是 | 第二联系人与用户关系 |

**3\) workOfficeInfo 职业-上班族**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| companyName | string | 是 | 公司名称 |
| areas | string | 是 | 公司地区：省,市,区 \(英文逗号区隔\) |
| address | string | 是 | 公司地址 |
| livingAddress | String | 是 | 现居住地址 |

### 2.3.紧急联系人关系映射列表

| relation | relationSpare | 描述 |
| :--- | :--- | :--- |
|  PARENT | PARENT | 父母 |
| COUPLE | COUPLE | 配偶 |
| SIBLING | SIBLING | 兄弟姐妹 |
| CHILD | CHILD | 子女 |
| CLASSMATE | CLASSMATE | 同学 |
| FRIEND | FRIEND | 朋友 |
| COLLEAGUE | COLLEAGUE | 同事 |



