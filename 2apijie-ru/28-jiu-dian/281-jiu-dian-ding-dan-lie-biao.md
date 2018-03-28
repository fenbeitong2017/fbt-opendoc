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
data |请求数据| jsonstring |Y|
data.state|查询状态|Integer|Y|  0:全部(默认值) 1:处理中 2:已完成
data.name\_or\_phone|乘机人/下单人姓名/手机|string|N| 如 老王/13800
data.name\_or\_phone\_type|乘机人/下单人姓名/手机号类型|string| N | （0:全部(默认值), 1:入住人, 2:下单人）
data.search\_category|搜索维度| Integer | N | 0:全部,1:企业 ,2:个人
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



响应数据：

```

{ "request_id": "IOCCucbNYCDEkCOOakDP",  "code": 0,  "msg": "Success",  "data": {    "results": [      {        "order_id": "58eaf3285d88db107e2fc0da",        "status": 2700,        "status_name": "已关闭",        "checkin_date": 1492012800000,        "checkout_date": 1492185600000,        "hotel_address": "北京朝阳区弘善家园414号楼",        "hotel_code": "204_91725321",        "hotel_name": "北京市柠檬树家庭旅馆十里河店",        "hotel_lat": "0.000000",        "hotel_lng": "0.000000",        "hotel_phone": "18911949793",        "price": 466,        "can_process": false      },      {        "order_id": "58e761235d88db6828665237",        "status": 2800,        "status_name": "退订成功",        "checkin_date": 1493136000000,        "checkout_date": 1493222400000,        "hotel_address": "海淀区西二旗大街与西二旗东一路交界,G6八		 达岭高速西侧,龙兴园南区北面",        "hotel_code": "204_10101487",        "hotel_name": "格林豪泰(北京西三旗桥商务酒店)",        "hotel_lat": "0.000000",        "hotel_lng": "0.000000",        "hotel_phone": "62920998",        "price": -207,        "can_process": false      }    ],    "total_count": 26  }}


```
