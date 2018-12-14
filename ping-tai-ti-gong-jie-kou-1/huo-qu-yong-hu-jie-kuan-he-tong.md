# 获取用户借款合同

### 1.请求路径

/contract

### 2.请求参数 <a id="2-qing-qiu-can-shu"></a>

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| orderNo | string | 是 | 订单唯一编号 |

### 3.响应参数

| 参数 | 类型 | 是否必选 | 描述 |
| :--- | :--- | :--- | :--- |
| name | string | 是 | 协议名称 |
| link | string | 是 | 协议链接 |

### 4.请求示例

```text
ua: "YBQB_PARTNER_XL",
call: "Order.getContracts",
args: {                 
    "orderNo":"246964109149933",
},
sign: "略...",
timestamp: "1500693926"

```

### 5.响应示例

```text
{
    "status": 1,
    "message": "success",
    "data": {
        name: "协议类型名称", link: "协议查看地址",
    {
}
```

