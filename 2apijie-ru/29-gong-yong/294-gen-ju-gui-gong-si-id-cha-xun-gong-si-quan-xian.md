2.9.3 根据公司ID查询公司权限
####接口说明
- 1.**最新接口**
- 2.根据公司ID查询公司相应的权限，在同步人员信息的时候如果该公司没有某个业务权限，则相应的业务权限则相应的关掉


| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/third/company/role |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id |
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y ||
| data.company_id | 公司ID | string | Y |公司ID
| data.type | 公司类型 | integer | Y |公司类型 1:分贝通公司ID，2:第三方公司ID










请求示例：

```


{
    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":1,
    "data":{   
    "company_id":"5747fbc10f0e60e0709d8d7d",
    "type":1         
     }
}


```

响应结果：

```

{
    "request_id": "tiCXpikD7XXdsa2vfP32",
    "code": 0,
    "msg": "success",
    "data": {
        "airRule": false,//false:不允许,true:允许
        "hotelRule": false,//false:不允许,true:允许
        "trainRule": false,//false:不允许,true:允许
        "taxiRule": false,//false:不允许,true:允许
        "mallRule": false,//false:不允许,true:允许
        "dinnerRule": false//false:不允许,true:允许
    }
}


```



