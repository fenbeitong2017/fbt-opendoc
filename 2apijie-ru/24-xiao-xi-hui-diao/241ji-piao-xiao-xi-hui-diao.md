字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
type_pame |订单类型名称 |String| Y |机票
type |订单类型| Integer | Y |机票:1
status |订单状态|Integer| Y |出票中:1700，出票成功:1800
apply_name|申请人姓名|String |Y|张三
contact_phone|联系电话|String|Y|
dept_name|部门名称|String |Y|事业部
monetary_unit|货币单位|String |Y|人民币
third_remark|出差事由备注|String|Y|出差
order_id |订单id|String| Y |9884hhkhfsk
total_price |总价 | Double| Y |388.00
budget_money|预估费用总计|Double |Y|单位：分
estimated_amount|预估费用|Double |Y|单位：分
refund_amount| 金额|Double|Y|供应商退给我们的钱
refund_fee|手续费|Double|Y|退票产生的手续费
begin_time|入住时间|String|Y|2018-01-01
end_time|离店时间|String|Y|2018-01-06
third_approve_id|申请单ID|String|Y|



数据格式:


```
{
	"company_id":"5747fbc10f0e60e0709d8d89",
	"company_name":"分贝通"
	"type_name":"机票",
	"type":1,
	"status":1700,
	"apply_name":"张三",
        "contact_phone":"13080899009",
        "dept_name":"人事部",
	"monetary_unit":人民币,
	"third_remark":"搜索",
	"order_id":"hksf83ho93lsbvnos145",
	"total_price": 302,
	"budget_money":787.80,
	"departure_place": "北京",
	"destination_place":"上海",
	"begin_time":"2018-01-01",
	"end_time":"2018-01-01",
	"third_approve_id":"hksf83ho93lsbvnos145",





	

}


```
