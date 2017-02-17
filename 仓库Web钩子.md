# Web钩子：

### 1.查询钩子列表

```
GET /api/v1/repos/:username/:reponame/hooks
```

响应：

```
Status: 200 OK
Content-Type: application/json
```

```
[
  {
    "id": 1,
    "type": "gogs",
    "config": {
      "content_type": "json",
      "url": "http://127.0.0.1:3000/unknwon/repo1/settings/hooks/14"
    },
    "events": [
      "push"
    ],
    "active": true,
    "updated_at": "2017-02-17T15:17:39+08:00",
    "created_at": "2017-02-17T15:17:39+08:00"
  }
]
```

### 2.创建钩子

```
POST /api/v1/repos/:username/:reponame/hooks
```

参数：

| Name | Type | Desc |
| :--- | :--- | :--- |
| type | string | \(必填\)钩子的类型，"gogs"或"slack" |
| config | object | \(必填\)钩子的配置，健值对 |
| event | array | 哪些操作触发钩子，"create","push","pull\_request",默认"push" |
| active | bool | 钩子是否触发 |

config参数：

* \`url\` :钩子推送的地址\(必填\)
* \`content\_type\`:数据格式，"json"或者"x-www-form-urlencoded"
* \`secret\`:可选的

例子：

```
{
    "type": "gogs",
    "config": {
        "url": "http://gogs.io",
        "content_type": "json"
    },
    "events": [
        "create",
        "push"
    ],
    "active": true
}
```

响应：

```
Status: 201 Created
Content-Type: application/json
```

```
{
    "type": "gogs",
    "config": {
    "content_type": "json",
    "url": "http://127.0.0.1:3000/unknwon/repo1/settings/hooks/24"
},
    "events": [
        "push",
        "create"
],
    "active": true
}
```

### 3.编辑钩子

```
PATCH /api/v1/repos/:username/:reponame/hooks/:id
```

参数：

| Name | Type | Desc |
| :--- | :--- | :--- |
| config | object | \(必填\)健值对，同上 |
| events | array | 触发事件，同上 |
| active | bool | 是否触发钩子 |

例子：

```
{
    "config": {
        "url": "http://gogs.io/hook"
    },
    "events": [
        "push"
    ]
}
```

响应：

```
Status: 200 OK
Content-Type: application/json
```

### 4.删除钩子

```
DELETE /api/v1/repos/:username/:reponame/hooks/:id
```

响应：

```
Status: 204 No Content
```



