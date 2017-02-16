# 组织管理：

### 1.创建一个新的组织

```
POST /api/v1/admin/users/:username/orgs
```

参数：

| Name | Type | Desc |
| :--- | :--- | :--- |
| username | string | 组织的用户名 |
| full\_name | string | 全名 |
| description | string | 描述 |
| website | string | 网址 |
| location | string | 组织位置 |

例子：

```
{
  "username": "hip2",
  "full_name": "HIP2",
  "description": "desc...",
  "website": "https://gogs.io",
  "location": "HAND"
}
```

响应：

```
Status: 201 Created
Content-Type: application/json
```

```
{
    "id": 4,
    "username": "hip2",
    "full_name": "HIP2",
    "avatar_url": "http://localhost:3000/avatars/4",
    "description": "desc...",
    "website": "https://gogs.io",
    "location": "HAND"
}
```

### 2.给组织添加一个团队

```
POST /api/v1/admin/orgs/:orgname/teams
```



