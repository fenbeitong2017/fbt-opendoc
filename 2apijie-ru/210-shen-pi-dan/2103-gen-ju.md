2.10.3 查询公司用车类型
####接口说明
- 1.**最新接口**


| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/approve/car/type |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID|
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y |请求数据


请求示例：

```

    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{}


```

响应结果：

```
{
  "request_id": "pf8MoH87QOzvyNaO",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": [
    {
      "key": 50,
      "value": "出租车"
    },
    {
      "key": 600,
      "value": "经济型"
    },
    {
      "key": 900,
      "value": "优享型"
    },
    {
      "key": 100,
      "value": "舒适型"
    },
    {
      "key": 400,
      "value": "六座商务"
    },
    {
      "key": 200,
      "value": "豪华型"
    }
  ]
}

```



