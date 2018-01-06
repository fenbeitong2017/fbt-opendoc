请求方式|请求地址
----|---
POST|/open/api/flight/order/list


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.name\_or\_phone|乘机人/下单人姓名/手机|string|N| 如 老王/13800
data.name\_or\_phone\_type|乘机人/下单人姓名/手机号类型|string| N | （0:全部(默认值) 1:乘机人 2:下单人）
data.search\_category|搜索维度| integer | N | 1:企业 2:个人
data.state|查询状态|integer|N|  0:全部(默认值) 1:处理中 2:已完成
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| integer | N | 1(默认值)
data.page\_size|每页显示条数| integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":"0",
		"page_index":"1",
		"data.page_size":"10",
		"search_category":"0",
		"order_ date_begin":"2017-01-01",
		"order_ date_end":"2017-05-01",
		"name_ or_phone":"123456",
		"name_ or_ phone_type":"1"
				
	}
}


```



响应结果：

```


{  "code": 0,  "msg": "success",  "data": {    "results": [      {        "order_id": "58e74c125d88db6664226ac8",        "remote_order_id": "112017040184019946",        "create_time": "2017-05-04 13:28:57",        "total_price": -1948,        "passenger_list": [          "汪远"        ],        "status": 1811,        "status_info": "退票成功",        "segment_info": {          "flight_no": "CA1835",          "airline_name": "中国国航",          "starting_code": "PEK",          "starting_city": "北京",          "destination_code": "PVG",          "destination_city": "上海",          "departure_timestamp": 0,          "arrived_timestamp": 0        },        "can_process": false      },      {        "order_id": "58deb1975d88db0e98febc28",        "remote_order_id": "112017040184019935",        "create_time": 1490989482042,        "total_price": 2160,        "passenger_list": [          "刘维中",          "汪远"        ],        "status": 1211,        "status_info": "已取消",        "segment_info": {          "flight_no": "MF8518",          "airline_name": "厦门航空",          "starting_code": "SHA",          "starting_city": "上海",          "destination_code": "XMN",          "destination_city": "厦门",          "departure_timestamp": 0,          "arrived_timestamp": 0        },        "can_process": false      }    ],    "total_count": 16  }}


```


