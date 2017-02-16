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

参数：

| Name | Type | Desc |
| :--- | :--- | :--- |
| name | string | 团队的名字\(必填\) |
| description | string | 描述 |
| permission | string | 团队所具备的权限等级，可以是\`read\`,\`write\`或者\`admin\`,默认是\`read\` |

例子：

```
{
  "name": "new-team",
  "description": "A new team created by API",
  "permission": "write"
}
```

响应：

```
Status: 201 Created
Content-Type: application/json
```

```
{
  "id": 3,
  "name": "new-team",
  "description": "A new team created by API",
  "permission": "write"
}
```

### 3.添加团队成员

```
PUT /admin/teams/:teamid/members/:username
```

参数：

| Name | Type | Desc |
| :--- | :--- | :--- |
| :teamid | int | 团队id |
| :username | string | 成员的用户名 |

响应：

```
Status: 204 No Content
```

### 4.移除团队成员

```
DELETE /admin/teams/:teamid/members/:username
```



