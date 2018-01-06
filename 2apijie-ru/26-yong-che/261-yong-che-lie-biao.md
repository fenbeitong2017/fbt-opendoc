请求方式|请求地址
----|---
POST|/open/api/car/order/list

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.search\_category|搜索维度| Integer | N | 1:企业 2:个人
data.state|查询状态|Integer|N|  0:全部(默认值) 1:处理中 2:已完成
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| Integer | N | 1(默认值)
data.page\_size|每页显示条数| Integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":"0"
	}
}
```



响应结果示例：


```

{
    "code": 0,
    "msg": "Success",
    "data": {
        "results": [
            {
                "order_id": "596dcb622798634dbc16768b",
                "vorder_id": "1125899951260423",
                "departure_name": "世贸国际公寓",
                "departure_lat": 39.914876,
                "departure_lng": 116.451379,
                "arrival_name": "物资学院路[地铁站]",
                "spec": {
                    "id": 600,
                    "name": "快车"
                },
                "type": 0,
                "status": 610,
                "status_info": "已取消",
                "price": 0,
                "order_time": "2017-07-18 16:48:34",
                "schedule_time": "2017-07-18 16:48:34",
                "can_process": true,
                "vendor_id": 1,
                "vendor_name": "滴滴",
                "type_name": "实时",
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "driver_info": {}
            },
            {
                "order_id": "596c830d2798630a935b5dd4",
                "vorder_id": "1125899949696928",
                "departure_name": "东大桥路24号楼",
                "departure_lat": 39.914829,
                "departure_lng": 116.451343,
                "arrival_name": "物资学院路[地铁站]",
                "spec": {
                    "id": 600,
                    "name": "快车"
                },
                "type": 1,
                "status": 610,
                "status_info": "已取消",
                "price": 0,
                "order_time": "2017-07-17 17:27:41",
                "schedule_time": "2017-07-18 23:00:00",
                "can_process": true,
                "vendor_id": 1,
                "vendor_name": "滴滴",
                "type_name": "预约",
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "driver_info": {}
            }...
        ],
        "total_count": 247
    }
}

```
