2.9.6 根据订单ID查询自定义字段内容
####接口说明
- 1.**最新接口**
- 2.9.6 根据订单ID查询自定义字段内容



 请求方式 | 请求地址 
--- | --- 
 POST | /open/api/common/order_param
 

 字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 
 sign | 签名 | string | Y | oihfnlyeofdh98 
 timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 
 employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id 
 employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 
 data |  请求数据 | jsonobject | Y |请求数据
 data.order_id |订单ID| string | Y |59b74c132344WASF83269
 




请求示例：

```


{
    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":1,
    "data":{  
    "order_id":"59b74c132344WASF83269"
          
     }
}


```

响应结果：

```


{
    "request_id": "p5pSgFroxrzL6pKBt59P",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": [
        {
            "cost_center": [
                "项目核算成本中心",
                "客户预算成本中心"
            ]
        },
        {
            "project_center": [
                "中铁项目中心",
                "国航项目中心"
            ]
        }
    ]
}




```



