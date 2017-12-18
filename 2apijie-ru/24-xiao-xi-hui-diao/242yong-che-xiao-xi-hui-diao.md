
字段|名称|类型|必填|详情
----|----|---|---|---
order_id |订单id|String| Y |9884hhkhfsk
total_price |订单金额 | Integer| Y |777
type_pame |订单类型名称 |String| Y |用车
type |订单类型| Integer | Y |用车:2
status |订单状态|Integer| Y |已完成:700
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
use_name |使用人姓名|String| Y |张三
use_phone |使用人手机号|String| Y | 13080899009
use_dep |使用人部门|String|Y|研发部
begin_time |开始计费时间|String|Y|2018-01-01：10：10：10
end_time|结束计费时间|String |Y|2018-01-01：11：10：10
departure_place |出发地|String|Y|中关村
destination_place|目的地|String |Y|北土城地铁站
third_approve_id|审批单ID|String |Y|98898hjhkhk





数据格式:


```
{
	"order_id":"hksf83ho93lsbvnos145",
	"total_price": 344.33,
	"type_name":"用车",
	"type":2,
	"status":400,
	"company_id":"5747fbc10f0e60e0709d8d89",
	"company_name":"分贝通"
	"use_name":"张三",
       "use_phone":"2343555554",
       "use_dep":"人事部",
       "begin_charge_time":"2018-01-01 10:10:10",
       "finish_charge_time":"2018-01-01 11:10:10",
    
	

}


```
