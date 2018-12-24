---
description: 用户在产品详情页，完成基础信息认证，并且通过用户过滤接口的用户，机构将向平台推送用户基础信息
---

# 推送用户基本信息

## 1.请求路径

/pushUserBaseInfo

## 2.请求参数

### 2.1. 参数总览 <a id="&#x53C2;&#x6570;&#x603B;&#x89C8;"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderInfo | object | 是 | 订单基础信息 |
| userInfo | object | 是 | 用户基础信息 |
| userVerify | object | 是 | 用户认证信息 |

### 2.2. 参数明细 <a id="&#x53C2;&#x6570;&#x660E;&#x7EC6;"></a>

#### 2.2.1. orderInfo订单基础信息

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |
| loanMount | string | 是 | 借款金额\(单位:分\) |

#### 2.2.2. userInfo 用户信息详情 <a id="user_info"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| userName | string | 是 | 用户身份证姓名 |
| userPhone | string | 是 | 用户明文手机号 |
| userIdCard | string | 是 | 用户明文身份证 |

#### 2.2.3. userVerify 认证信息详情 <a id="user_verify"></a>

**1-1\) operatorVerify 运营商原始数据**

```text
{
	"data": {
		"identity_code": "513301199123123123",
		"created_time": "2018-09-26 16:08:06",
		"channel_src": "中国移动",
		"user_mobile": "18301231234",
		"task_data": {
			"bill_info": [{
				"bill_discount": null,
				"bill_fee": "5810",
				"usage_detail": [],
				"bill_record": [{
					"fee_name": "固定费用",
					"fee_amount": "5800",
					"fee_category": null,
					"user_number": "18303019887"
				}],
				"bill_cycle": "2018-09",
				"paid_amount": null,
				"unpaid_amount": null,
				"breach_amount": null,
				"bill_total": "5810"
			}],
			"family_info": [],
			"sms_info": [{
				"total_msg_cost": "10",
				"total_msg_count": "70",
				"sms_record": [{
					"msg_cost": "0",
					"msg_channel": "短信",
					"msg_fee": null,
					"msg_biz_name": null,
					"msg_start_time": "2018-09-01 10:30:45",
					"msg_discount": null,
					"msg_remark": null,
					"msg_type": "接收",
					"msg_address": "未知",
					"msg_other_num": "10086"
				}],
				"msg_cycle": "2018-09"
			}],
			"account_info": {
				"mobile_status": "正常",
				"prom_available": null,
				"credit_score": null,
				"credit_point": "1063",
				"balance_unavailable": null,
				"account_balance": "832",
				"balance_available": null,
				"sim_card": null,
				"land_level": null,
				"prepay_unavailable": null,
				"net_age": "73",
				"real_info": "已登记",
				"prepay_available": null,
				"prom_unavailable": null,
				"credit_effective_time": null,
				"credit_level": "3",
				"net_time": "2012-08-21",
				"puk_code": null,
				"current_fee": "5810",
				"roam_state": null
			},
			"point_info": {
				"point_record": [],
				"point_detail": []
			},
			"base_info": {
				"user_sex": "未知",
				"cert_addr": "未知",
				"user_email": "未知",
				"user_name": "姚**",
				"post_code": null,
				"cert_num": "未知",
				"user_number": "18312312345",
				"user_contact_no": "未知"
			},
			"payment_info": [{
				"pay_date": "2018-09-01",
				"pay_channel": "其他",
				"pay_fee": "4990",
				"pay_type": "现金充值"
			}],
			"package_info": {
				"brand_name": "全球通",
				"pay_type": null,
				"package_detail": []
			},
			"call_info": [{
				"total_call_count": "54",
				"total_call_time": "4343",
				"total_fee": "0",
				"call_cycle": "2018-09",
				"call_record": [{
					"call_cost": "0",
					"call_land_type": "国内长途",
					"call_long_distance": null,
					"call_type_name": "被叫",
					"call_time": "50",
					"call_roam_cost": null,
					"call_other_number": "18812312312",
					"call_start_time": "2018-09-01 00:46:19",
					"call_discount": null,
					"call_address": "上海市.上海市"
				}]
			}]
		},
		"user_name": "1831234123",
		"real_name": "姚**",
		"channel_code": "100000",
		"channel_type": "YYS",
		
		"lost_data": null
	}
}
```

**1-2\) operatorReportVerify 运营商报告数据**

**与合作机构商定**

**2\)idCardInfo 身份证认证**

| 参数 | 类型 | 是否必选 | 描述 | 父节点字段 |
| :--- | :--- | :--- | :--- | :--- |
| idCardInfo | object | 是 | 身份证信息 | idCardInfo |

| 参数 | 类型 | 是否必选 | 描述 | 父节点字段 |
| :--- | :--- | :--- | :--- | :--- |
| faceRecognitionPicture | string | 是 | 活体识别头像URL | idCardInfo |
| idNumberPicture | string | 否 | 手持身份证头像URL | idCardInfo |
| idNumberZPicture | string | 是 | 身份证正面照片URL | idCardInfo |
| idNumberFPicture | string | 是 | 身份证反面照片URL | idCardInfo |
| ocrName | string | 是 | OCR识别身份证姓名 | idCardInfo |
| ocrRace | string | 是 | OCR识别身份证民族 | idCardInfo |
| ocrSex | string | 是 | OCR识别身份证性别 | idCardInfo |
| ocrBirthday | string | 是 | OCR识别身份证出生日期 | idCardInfo |
| ocrIdNumber | string | 是 | OCR识别身份证号 | idCardInfo |
| ocrAddress | string | 是 | OCR识别身份证地址 | idCardInfo |
| ocrIssuedBy | string | 是 | OCR识别身份证发证机关 | idCardInfo |
| ocrStartTime | string | 是 | OCR识别身份证有效期开始时间 | idCardInfo |
| ocrEndTime | string | 是 | OCR识别身份证有效期结束时间 | idCardInfo |

