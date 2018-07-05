2.7.1 酒店订单列表

####接口说明
- 1.**最新接口**
- 2.查询酒店订单列表接口
  通过该接口可以查询企业使用分贝通APP下的酒店订单信息





请求方式|请求地址
----|---
POST|/open/api/hotel/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|
data.state|查询状态|Integer|Y|  0:全部(默认值) 1:处理中 2:已完成
data.name\_or\_phone|乘机人/下单人姓名/手机|string|N| 如 老王/13800
data.name\_or\_phone\_type|乘机人/下单人姓名/手机号类型|string| N | （0:全部(默认值), 1:入住人, 2:下单人）
data.search\_category|搜索维度| Integer | N | 0:全部,1:企业 ,2:个人
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| Integer | N | 1(默认值)
data.page\_size|每页显示条数| Integer |N| 10(默认值)，如果不传就默认为10
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":0					
	}
}


```



字段|名称|类型|必填|描述
-----|-----|----|----|----
order_id|订单ID |String |Y|5abc5eff27986354622e6b94
status|订单状态 |integer |Y|2501
status_name|订单状态名称 | string |Y|订房成功
checkin_date| 入住日期|integer |Y|1524499200000
checkout_date| 离店日期|integer|Y|1524585600000
hotel_address |酒店地址| string |Y|金钟路896号
hotel_code|酒店code|string|Y| 5abb0028979d961a343a12fb
hotel_name|酒店名称|string|Y| 如家酒店
hotel_lat|酒店经度|string| Y | 11.993970
hotel_lng|酒店维度| string | Y |11.993538
price|价格|double| Y |41
can_process|是否可以查看订单|boolean|Y|false
hotel_phone|酒店电话| string | Y |010-53767110
guests|入住人信息| jsonobject |Y| 
guests.name|入住人姓名| string |Y| 刘维中
guests.phone_no|入住人手机号| string |Y| 18601016943
is_external_order|是否外采订单| Integer |Y| 0  1:是,0:否 
total_price_str|价格字符串| string |Y|￥41.00
employee_name | 下单人姓名 | string | Y | 张三
employee_id | 下单人id | string | Y | uejk8489u78078993u7848
create_time | 下单时间 | integer | Y | 1522294527444


响应数据：

```

{ "request_id": "IOCCucbNYCDEkCOOakDP",  "code": 0,  "msg": "Success",  "data": {   
results": [{
			"order_id": "5abc5eff27986354622e6b94",
			"status": 2501,
			"status_name": "订房成功",
			"checkin_date": 1524499200000,
			"checkout_date": 1524585600000,
			"hotel_address": "金钟路896号携程",
			"hotel_code": "5abb0028979d961a343a12fb",
			"hotel_name": "两大分销商对接ceshi酒店（请勿修改）",
			"hotel_lat": "11.993970",
			"hotel_lng": "11.993538",
			"hotel_phone": "010-53767110",
			"city_name": "北京市",
			"price": 41,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"can_process": false,
			"guests": [{
				"name": "刘维中",
				"phone_no": "18601016943"
			}],
			"is_external_order": 0,
			"total_price_str": "￥41.00"
		}, {
			"order_id": "5abc5e9027986354622e6b8e",
			"status": 2700,
			"status_name": "已关闭",
			"checkin_date": 1524499200000,
			"checkout_date": 1524585600000,
			"hotel_address": "金钟路896号携程",
			"hotel_code": "5abb0028979d961a343a12fb",
			"hotel_name": "两大分销商对接ceshi酒店（请勿修改）",
			"hotel_lat": "11.993970",
			"hotel_lng": "11.993538",
			"hotel_phone": "010-53767110",
			"city_name": "北京市",
			"price": 41,
			"can_process": false,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"guests": [{
				"name": "施伟",
				"phone_no": "18511371609"
			}],
			"is_external_order": 0,
			"total_price_str": "￥41.00"
		}, {
			"order_id": "5abb8e7227986354622e6b71",
			"status": 2700,
			"status_name": "已关闭",
			"checkin_date": 1523462400000,
			"checkout_date": 1523548800000,
			"hotel_address": "西城区大栅栏西路56号",
			"hotel_code": "5a41ea09979d9663f8b065b4",
			"hotel_name": "格林豪泰酒店(北京天安门大栅栏店)",
			"hotel_phone": "010-63156115",
			"city_name": "北京市",
			"price": 343,
			"can_process": false,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"guests": [{
				"name": "强仔",
				"phone_no": "18310480640"
			}],
			"is_external_order": 0,
			"total_price_str": "￥343.00"
		}, {
			"order_id": "5abb614d27986354622e6b4b",
			"status": 2700,
			"status_name": "已关闭",
			"checkin_date": 1523462400000,
			"checkout_date": 1523548800000,
			"hotel_address": "西城区大栅栏西路56号",
			"hotel_code": "5a41ea09979d9663f8b065b4",
			"hotel_name": "格林豪泰酒店(北京天安门大栅栏店)",
			"hotel_phone": "010-63156115",
			"city_name": "北京市",
			"price": 343,
			"can_process": false,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"guests": [{
				"name": "强仔",
				"phone_no": "18310480640"
			}],
			"is_external_order": 0,
			"total_price_str": "￥343.00"
		} ,{
			"order_id": "5abb392e2798633477a6a06c",
			"status": 2502,
			"status_name": "订房失败",
			"checkin_date": 1524585600000,
			"checkout_date": 1524672000000,
			"hotel_address": "金钟路896号携程",
			"hotel_code": "5abb0028979d961a343a12fb",
			"hotel_name": "两大分销商对接ceshi酒店（请勿修改）",
			"hotel_lat": "11.993970",
			"hotel_lng": "11.993538",
			"hotel_phone": "010-53767110",
			"city_name": "北京市",
			"price": 41,
			"can_process": false,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"guests": [{
				"name": "刘维中",
				"phone_no": "18601016943"
			}],
			"is_external_order": 0,
			"total_price_str": "￥41.00"
		}, {
			"order_id": "5abb162b27986345c41944c9",
			"status": 2700,
			"status_name": "已关闭",
			"checkin_date": 1523894400000,
			"checkout_date": 1523980800000,
			"hotel_address": "金钟路896号携程",
			"hotel_code": "5abb0028979d961a343a12fb",
			"hotel_name": "两大分销商对接ceshi酒店（请勿修改）",
			"hotel_lat": "11.993970",
			"hotel_lng": "11.993538",
			"hotel_phone": "010-53767110",
			"city_name": "北京市",
			"price": 41,
			"can_process": false,
			"employee_name":"张三",
               	 "employee_id":"56768798765645",
               	 "create_time":1523533736260,
			"guests": [{
				"name": "施伟",
				"phone_no": "18511371609"
			}],
			"is_external_order": 0,
			"total_price_str": "￥41.00"
		}],
		"total_count": 1130}}


```
