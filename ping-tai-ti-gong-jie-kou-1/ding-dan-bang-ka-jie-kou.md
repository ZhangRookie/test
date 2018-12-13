# 订单绑卡接口

### 1.请求路径

/applyBindCard

### 2.请求参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 借款订单唯一编号 |
| bankCode | string | 是 | 绑卡银行编码 |
| userName | string | 是 | 用户姓名 |
| userIdCard | string | 是 | 用户身份证号 |
| cardNumber | string | 是 | 银行卡号\(只支持借记卡\) |
| cardPhone | string | 是 | 银行预留手机号 |
| userPhone | string | 是 | 用户准入时的明文手机号 |
| echoData | string | 是 | 回显数据字段, 此字段仅要求在绑卡结果回调接口中回传即可 |
| verifyCode | string | 否 | 绑卡验证码，当已发送验证码之后再次请求提交 |

### 3. 响应参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| bindStatus | string | 是 | 绑卡结果状态 |
| remark | string | 否 | 绑卡状态描述 |

### 4.请求示例

```text
"orderNo":"246964109149933",    
"bankCode":"ICBC",        
"userName":"张三",        
"userIdCard":"610121190001011122",
"cardNumber":"6222022005001212723",       
"cardPhone":"13245678901",
"userPhone":"13370212345",
"echoData": "{pid: 123456}",
"verifyCode": "376258"
```

### 5.响应示例

> 成功示例
>
> ```text
> {
>     status: 1,
>     message: "success",
>     data: {
>         "bindStatus": "200",
>         "remark": "success",
>     }
> }
> ```
>
> 失败示例
>
> ```text
> {
>     status: 1,
>     message: "success",
>     data: {
>         "bindStatus": "505",
>         "remark": "其它错误原因请备注",
>     }
> }
> ```

### 6.绑卡结果状态列表

| bind\_status | 说明 |
| :--- | :--- |
| 100 | 需短信验证码，请输入已发送的验证码重新绑卡 |
| 200 | 绑卡成功\(当此卡在平台已绑定成功，不需要短信验证码\) |
| 401 | 认证信息不匹配 |
| 402 | 请检查卡号对应的银行是否正确 |
| 403 | 无法验证，银行卡未开通认证支付 |
| 501 | 绑卡失败次数超限，请24小时后重试！ |
| 505 | 其它绑卡失败原因，请备注用户前端透传 |

