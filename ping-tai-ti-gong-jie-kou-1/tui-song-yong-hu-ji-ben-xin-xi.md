---
description: 用户在产品详情页，完成基础信息认证，并且通过用户过滤接口的用户，机构将向平台推送用户基础信息
---

# 推送用户基本信息

## 1.请求路径

/pushUserBaseInfo

## 2.请求参数

### 2.1. 参数总览 {#参数总览}

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderInfo | object | 是 | 订单基础信息 |
| userInfo | object | 是 | 用户基础信息 |
| userVerify | object | 是 | 用户认证信息 |

### 2.2. 参数明细 {#参数明细}

#### 2.2.1. orderInfo订单基础信息

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| loanmount | string | 是 | 借款金额\(单位:分\) |

#### 2.2.2. userInfo 用户信息详情 {#user_info}

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| user\_name | string | 是 | 用户身份证姓名 |
| userPhone | string | 是 | 用户明文手机号 |
| userIdCard | string | 是 | 用户明文身份证 |

#### 2.2.3. userVerify 认证信息详情 {#user_verify}

**1-1\) operatorVerify 运营商原始数据**

**1-2\) operatorReportVerify 运营商报告数据**

\*\*\*\*

**2\)idCardInfo 身份证认证**

| 参数 | 类型 | 是否必选 | 描述 | 父节点字段 |
| :--- | :--- | :--- | :--- | :--- |
| idCardInfo | object | 是 | 身份证信息 | idCardInfo |

| 参数 | 类型 | 是否必选 | 描述 | 父节点字段 |
| :--- | :--- | :--- | :--- | :--- |
| faceRecognitionPicture | string | 否 | 活体识别头像URL | idCardInfo |
| idNumberPicture | string | 否 | 手持身份证头像URL | idCardInfo |
| idNumberZPicture | string | 否 | 身份证正面照片URL | idCardInfo |
| idNumberFPicture | string | 否 | 身份证反面照片URL | idCardInfo |
| ocrName | string | 否 | OCR识别身份证姓名 | idCardInfo |
| ocrRace | string | 否 | OCR识别身份证民族 | idCardInfo |
| ocrSex | string | 否 | OCR识别身份证性别 | idCardInfo |
| ocrBirthday | string | 否 | OCR识别身份证出生日期 | idCardInfo |
| ocrIdNumber | string | 否 | OCR识别身份证号 | idCardInfo |
| ocrAddress | string | 否 | OCR识别身份证地址 | idCardInfo |
| ocrIssuedBy | string | 否 | OCR识别身份证发证机关 | idCardInfo |
| ocrStartTime | string | 否 | OCR识别身份证有效期开始时间 | idCardInfo |
| ocrEndTime | string | 否 | OCR识别身份证有效期结束时间 | idCardInfo |

