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


{  "code": 0, 
   "msg": "success", 
  "data": {   
"results": [    
{"order_id": "58e74c125d88db6664226ac8",//订单ID       "remote_order_id": "112017040184019946",   
"create_time": "2017-05-04 13:28:57",//创建时间 
"total_price": -1948,//订单价格，负数为退票状态，退票返回金额
"passenger_list": ["汪远"],//乘客信息
"status": 1811,//订单状态,详情参照状态码
"status_info": "退票成功",//订单详细信息
"segment_info": { "flight_no": "CA1835",//航班号    "airline_name": "中国国航",//航班名称
"starting_code": "PEK",//出发城市编码  
 "starting_city": "北京",//出发城市名称
 "destination_code": "PVG",//目的地城市编码     
 "destination_city": "上海",//目的地城市名称
 "departure_timestamp": 1522580110000, // 出发时间    
 "arrived_timestamp": 1522587319000//到达时间 },
 "can_process": false / 是否可以查看订单详情，分为企业订单和个人名单，个人不能查看企业订单详情
 is_external_order": 1,//是否外采订单
 "total_price_str": "￥100.00"//订单金额字符串},    
{"order_id": "58deb1975d88db0e98febc28",     
"remote_order_id": "112017040184019935",    
 "create_time": 1490989482042,
 "total_price": 2160,
 "passenger_list": ["刘维中","汪远"],
"status": 1211,
"status_info": "已取消","segment_info": {"flight_no": "MF8518","airline_name": "厦门航空","starting_code": "SHA","starting_city": "上海","destination_code": "XMN", "destination_city": "厦门","departure_timestamp": 0,"arrived_timestamp": 0},"can_process": false}], 
 "total_count": 16  }}


```


