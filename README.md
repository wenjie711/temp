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
GET /api/ufops/:id/versions
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
GET /api/ufops/:id/instances
```

结果

```js
{
   "code": 200
   "data":
   [
      {
        "index":"1",
        "version":"v1.1",
        "state":"Stopped"
      },
      {
        "index":"2",
        "version":"v1.1",
        "state":"Running"
      },
      {
        "index":"3",
        "version":"v1.0",
        "state":"Running"
      }
   ]
}
```

错误

```js
UfopNotfound    Code = ?//待定
ResultError     Code = 500 // 请求结果发生错误
```

###6. POST /api/ufops/:id/instances/:id/start(启用一个ufop实例)

请求

```js
POST /api/ufops/:id/instances/:id/start
```

结果

```js
{
   "code": 200
   "data":
   {
        "index":"1",
        "version":"v1.1",
        "state":"Stopped"
   }
    
}
```

错误

```js
UfopNotfound    Code = ?//待定
ResultError     Code = 500 // 请求结果发生错误
```

###7. POST /api/ufops/:id/instances/:id/stop(停用一个ufop实例)

请求

```js
POST /api/ufops/:id/instances/:id/stop
```

结果

```js
{
   "code": 200
   "data":
   {
        "index":"1",
        "version":"v1.1",
        "state":"Stopped"
   }
    
}
```

错误

```js
UfopNotfound    Code = ?//待定
ResultError     Code = 500 // 请求结果发生错误
```

###8. POST /api/ufops/:id/instances/:id/reboot(重启某一实例号的ufop实例)

请求

```js
POST /api/ufops/:id/instances/:id/reboot
```

结果

```js
{
   "code": 200
   "data":
   {
        "index":"1",
        "version":"v1.1",
        "state":"Stopped"
   }
}
```

错误

```js
ResultError     Code = 500 // 请求结果发生错误
UfopNotfound    Code = ? // Code待定，Ufop删除失败
```

###9. POST /api/ufops/:id/instances(添加ufop实例)

请求

```js
POST /api/ufops/:id/instances

{
   "size":"3"   
   "version":"v1.0"
}

//得先切换到对应版本才能添加那个版本的实例
```

结果

```js
{
   "code": 200
   "data":
   [
      {
        "index":"1",
        "version":"v1.1",
        "state":"Stopped"
      },
      {
        "index":"2",
        "version":"v1.1",
        "state":"Running"
      },
      {
        "index":"3",
        "version":"v1.0",
        "state":"Running"
      }
   ]
    
}
```

错误

```js
InvalidArgs     Code = 400 // 请求参数错误，或者数据未通过验证
ResultError     Code = 500 // 请求结果发生错误
UfopNotfound    Code = ?//待定
```

##10. DELETE /api/ufops/:id/instances/:id(删除某一实例号的ufop实例)

请求

```js
DELETE /api/ufops/:id/instances/:id
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
UfopNotfound    Code = ? // Code待定，Ufop删除失败
```

###11. POST /api/ufops/:id/instances/:id/switch(切换到当前ufop实例)

请求

```js
POST /api/ufops/:id/instances/:id/switch
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
UfopNotfound    Code = ?//待定
```

###12. GET /api/ufops/:id/instances/:id/log(查看某一个运行的ufop实例的日志)

请求

```js
GET /api/ufops/:id/instances/:id/log
```

结果

```js
{
   "code": 200
   "data":
   {
      "log":"2015-07-13 [INFO] start up successfully"
   }
}
```

错误

```js
ResultError     Code = 500 // 请求结果发生错误
UfopNotfound    Code = ?//待定
```

