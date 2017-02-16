# 用户邮箱:

### 1.列举用户邮箱

```
GET /api/v1/user/emails
```

响应：

```
Status: 200 OK
Content-Type: application/json
```

```
[
    {
        "email": "jianwu.bin@hand-china.com",
        "verified": true,
        "primary": false
    },
    {
        "email": "abc@hand-china.com",
        "verified": true,
        "primary": true
    }
]
```

### 2.添加邮箱地址

```
POST /api/v1/user/emails
```

例子：

```
[
  "user1@user.com",
  "user2@user.com"
]
```

响应：

```
Status: 201 Created
Content-Type: application/json
```

```
[
  {
    "email": "user1@user.com",
    "verified": false,
    "primary": false
  },
  {
    "email": "user1@user.com",
    "verified": false,
    "primary": false
  }
]
```

### 3.删除邮箱地址

```
DELETE /api/v1/user/emails
```

例子：

```
[
  "user1@user.com",
  "user2@user.com"
]
```

响应：

```
Status: 204 No Content
```



