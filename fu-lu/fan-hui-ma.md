---
description: >-
  不论是平台提供的接口还是合作机构提供的接口。 统一要求返回状态码为 1 代表请求成功。 当服务器异常时, 返回非 1
  值代表请求失败，如果请求失败则需要在message中说明失败原因。
---

# 返回码

### 1.请求成功返回示例

```text
{
    status: 1,
    message: "success",
    data: {
        "result": 200, 
        "loanMode": 0,
        "userId": "838f5c94a7db105e3948aa40e982427a"
    }
}
```

### 2.请求失败返回示例

```text
{
    status: 0,
    message: "error",
    data: null
}
```

