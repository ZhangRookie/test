---
description: 用户在完成平台产品所需的所有补充认证项，机构将向平台推送订单和所需的补充信息
---

# 推送用户补充信息

## 请求参数 <a id="&#x8BF7;&#x6C42;&#x53C2;&#x6570;"></a>

### 3.1. 参数总览 <a id="&#x53C2;&#x6570;&#x603B;&#x89C8;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderInfo | object | 是 | 用户订单信息 |
| userAdditional | object | 是 | 用户补充信息 |

### 3.2. 参数明细 <a id="&#x53C2;&#x6570;&#x660E;&#x7EC6;"></a>

#### 3.2.1. orderInfo 用户订单信息 <a id="order_info"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| loan\_amount | string | 是 | 借款金额\(单位:分\) |
| userPhone | string | 是 | 用户明文手机号 |

####  3.2.2 userAdditional 补充信息详情 <a id="user_additional"></a>

**1\) deviceInfo 设备信息**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 是 | 设备标识 7d50dcb97e654de6890ae8000bb4558a |
| idfa | String | 否 | iOS设备专用（同时受App Store影响可能缺失）IDFA标识 BAFA623B-A87F-4F69-85C8-52F76F1464BF |
| idfv | String | 否 | identifierForVendor |
| device\_info | String | 是 | 设备名称 iPhone 6 Plus |
| osType | String | 是 | 设备类型 iOS |
| osVersion | String | 是 | 系统版本号 9.300000 |
| lastLoginTime | String | 是 | 最后登录时间 1476692044 |
| gpsLongitude | String | 否 | 经度 121.5103238932292 |
| gpsLatitude | String | 否 | 纬度 31.30658718532986 |
| gpsAddress | String | 否 | 具体地址 上海市杨浦区政学路靠近金芭蕾舞蹈\(五角场店\) |
| ip | String | 是 | 登录设备IP地址 127.0.0.1 |
| memory | String | 是 | 内存容量 |
| storage | String | 是 | 总内部存储 |
| unuseStorage | String | 是 | 可使用内部存储 |
| wifi | String | 否 | 是否使用 wifi |
| wifiName | String | 否 | wifi 名称 |
| bettary | String | 是 | 电量 |
| carrier | String | 否 | 运营商 |
| teleNum | String | 否 | 运营商编码 |
| appMarket | String | 是 | 渠道 |
| isRoot | String | 是 | 是否 ROOT 或越狱 |
| dns | String | 否 | DNS |
| isSimulator | String | 是 | 是否为模拟器 |
| picCount | String | 否 | 图片数量 |
| androidId | String | 否 | android\_id |
| udid | String | 否 | 设备的唯一设备识别符 |
| uuid | String | 否 | 设备标识符UUID |
| imsi | String | 否 | 国际移动用户识别码 |
| mac | String | 否 | MAC地址 |
| sdcard | String | 否 | 内存卡容量 |
| unuseSdcard | String | 否 | 已经使用容量 |
| imei | String | 否 | imei |

**2\) addressBook 通讯录信息**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| phoneList | array | 是 | 通讯录列表 name\_phone |

**3\) contactInfo 紧急联系人信息**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| name | String | 是 | 第一联系人姓名 |
| mobile | String | 是 | 第一联系人手机号 |
| relation | String | 是 | 第一联系人与用户关系 |
| nameSpare | String | 是 | 第二联系人姓名 |
| mobileSpare | String | 是 | 第二联系人手机号 |
| relationSpare | String | 是 | 第二联系人与用户关系 |

**4\) workOfficeInfo 职业-上班族**

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| companyName | string | 是 | 公司名称 |
| areas | string | 是 | 公司地区：省,市,区 \(英文逗号区隔\) |
| address | string | 是 | 公司地址 |
| telNo | string | 是 | 公司电话 |

