请求方式|请求地址
----|---
POST|/open/api/hotel/order/detail

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.order_id|订单号|string|Y|

请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"5a98fe1b2798636ba9006f1e"					
	}
}


```



