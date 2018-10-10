---
description: 用户认证完成后，将具体的认证结果通过本接口推送给合作机构
---

# 认证结果回调

## 请求参数 {#请求参数}

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| authStatus | string | 是 | 认证结果状态; 200 认证成功，401认证失败需要重新认证 |
| authType | string | 是 | 认证类型 1 芝麻认证，2 运营商认证, 3 信用卡认证，4 公积金认证，5 社保认证，6 人行征信认证 7 信用卡账单认证 8 用款确认 |
| successTime | int | 是 | 有效期时间戳\(10位\) |
| userName | string | 是 | 用户姓名 |
| userPhone | string | 是 | 用户手机号 |
| userIdCard | string | 是 | 用户身份证号码 |

## 请求示例

```text
"authStatus":"200",
"authType":"1",
"successTime": 1500693926,
"userName": "张三",
"userPhone": "15026875663"
"userIdCard": "654123456789123345"
```

## 响应示例 {#响应示例}

```text
{
    status: 1,
    message: "success",
    data: null
}
```

## 枚举列表 {#枚举列表}

| auth\_status | 认证结果状态 |
| :--- | :--- |
| 200 | 认证成功 |
| 401 | 认证失败需要重新认证 |

