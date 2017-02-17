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



