# Web钩子：

### 1.查询钩子列表

```
GET /api/v1/repos/:username/:reponame/hooks
```

响应：

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



