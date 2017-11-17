
字段|名称|类型|必填|详情
----|----|---|---|---
order_id|订单id|String| Y | hksf83ho93lsbvnos145
total_price|订单金额 | Double| Y |344.33
type_pame|订单类型名称 |String| Y |机票
type |订单类型| Integer | Y |机票:1
status |订单状态|Integer| Y |出票中:1700，出票成功:1800
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name| 公司名称|String|Y|分贝通



数据格式:


```
{
	"order_id":"hksf83ho93lsbvnos145",
	"total_price": 344.33,
	"type_pame":"机票",
	"type":1,
	"status":1700,
	"company_id":"5747fbc10f0e60e0709d8d89",
	"company_name":"分贝通"
	

}


```
