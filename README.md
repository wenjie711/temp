#UFOP API book

###1. POST /api/ufops(注册一个Ufop)

请求

```js
POST /api/ufops

{
   "name": "name",
   "aclMode": "aclMode"
   "configuration":"configuration"
   "desc":"desc"
}
```

结果

```js
{
    "code": 200,
}
```

错误

```js
InvalidArgs     Code = 400 // 请求参数错误，或者数据未通过验证
ResultError     Code = 500 // 请求结果发生错误
```

###2. GET /api/ufops(列出所有的Ufop)

请求

```js
GET /api/ufops
```

结果

```js
{
    "code": 200
    "data":
    [
      {
        "name": "testzy_123",
        "aclMode":"0"
        "desc":"这是Ufop的描述"
      },
      {
        "name": "testzy_1234",
        "aclMode":"1"
        "desc":"这是Ufop的描述"
      }
    ]
}
```

错误

```js
ResultError     Code = 500 // 请求结果发生错误
```

###3. POST /api/images(上传一个Ufop Image)

请求

```js
POST /api/images
```

结果

```js
{
    "code": 200
}
```

错误

```js
ResultError     Code = 500 // 请求结果发生错误
```

###4. GET /api/ufops/:id/versions(获取一个ufop的版本列表)

请求

```js
POST /api/ufops/:id/versions
```

结果

```js
{
    "code": 200
    "data":
    [
      {
        "version":"v1.1",
        "state":"build success",
        "createAt":"2015-06-25 17:27:10"
      },
      {
        "version":"v1.2",
        "state":"build success",
        "createAt":"2015-06-25 17:27:10"
      },
      {
        "version":"v1.3",
        "state":"build success",
        "createAt":"2015-06-25 17:27:10"
      }
    ]
}
```

错误

```js
UfopNotfound    Code = ?//待定
ResultError     Code = 500 // 请求结果发生错误
```

###5. GET /api/ufops/:id/instances(获取一个ufop的实例列表)

请求

```js
POST /api/ufops/:id/instances
```

结果

```js
{
    "code": 200
    "data":
    [
      {
        ""
        "version":"v1.0"
        ""
      },
      {
        "name":"ufop2"
      },
      {
        "name":"ufop3"
      }
    ]
}
```

错误

```js
UfopNotfound    Code = ?//待定
ResultError     Code = 500 // 请求结果发生错误
```

