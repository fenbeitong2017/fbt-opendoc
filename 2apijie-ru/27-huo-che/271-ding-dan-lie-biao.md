根据企业appId/appKey等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/api/train/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|String|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.state| 查询状态|Integer |Y|0全部，1正处理，2已完成
data.name\_or\_phone|乘客/下单人姓名/手机号 |string |N|
data.name\_or\_phone\_type|乘客/下单人姓名/手机号类型 |string | N |
data.search\_category |搜索维度| Integer | N |
data.order\_date\_begin |下单开始日期|string | N |yyyy-MM-dd
data.order\_date\_end|下单结束日期 |string | N |yyyy-MM-dd
data.page\_index |页码| Integer |  N |1(默认值)
data.page\_size|每页显示条数| Integer|  N |10(默认值)


请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
	  "state":0
	}
}


```


响应数据：



```


{
    "request_id": "IOCCucbNYCDEkCOOakDP",
    "code": 0,
    "msg": "success",
    "data": {
        "results": [
            {
                "order_id": "59e456cd2798636090cdf339",
                "status": {
                    "key": 3101,
                    "value": "已取消"
                },
                "departure_time": 1509686700000,
                "arrival_time": 1509691260000,
                "train_code": "6026",
                "passenger_names": [
                    "韩树起"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            },
            {
                "order_id": "59e4526b2798636090cdf30c",
                "status": {
                    "key": 3203,
                    "value": "出票失败"
                },
                "departure_time": 1509686700000,
                "arrival_time": 1509691260000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            },
                       {
                "order_id": "59df44392798637cf9d5913a",
                "status": {
                    "key": 3400,
                    "value": "有退改纪录"
                },
                "departure_time": 1510205100000,
                "arrival_time": 1510209660000,
                "train_code": "6026",
                "passenger_names": [
                    "韩树起"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            }
        ],
        "total_count": 6
    }
}


```

