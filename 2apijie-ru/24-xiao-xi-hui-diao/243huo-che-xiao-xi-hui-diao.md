字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
type_name |订单类型名称 |String| Y |火车
type |订单类型| Integer | Y |火车:3
status |订单状态|Integer| Y |已完成:3202
apply_name|申请人姓名|String |Y|张三
contact_phone|联系电话|String|Y|
dept_name|部门名称|String |Y|事业部
monetary_unit|货币单位|String |Y|人民币
third_remark |三方备注|String|Y|需要进行备注的信息，可以当备用字段
budget_money|预估费用总计|Double |Y|单位：分
estimated_amount|预估费用|Double |Y|单位：分
order_id |订单id|String| Y |9884hhkhfsk
total_price |订单金额 | Double| Y |302.90
train_code|车次|String|Y|
departure_place|出发站|String|Y|北京站
destination_place|到达站|String|Y|上海站
begin_time|火车出发时间|String |Y|2018-01-01
end_time|火车到达时间|String|Y|
premium|保险费|Double|Y| 
refund_amount|退票费|Double|Y| 
refund_fee|手续费|Double|Y|
change_fee|改签费|Double|Y|
change_ticket_fee|改签差价手续费|Double|Y|
third_approve_id|申请单ID|String|Y|







数据格式:


```
{
"company_id":"5747fbc10f0e60e0709d8d89",
"company_name":"分贝通",
"type_name":"火车",
"type":3,
"status":3202,
"apply_name":"李四",
"contact_phone":"567689752",
"dept_name":"人力部
"monetary_unit":人民币,
"third_remark":"搜索",
"order_id":"hksf83ho93lsbvnos145",
"total_price": 302,
"budget_money":787.80,
"train_code":"1024",
"departure_place": "北京",
"destination_place":"上海",
"begin_time":"2018-01-01",
"end_time":"2018-01-01",
"premium":32.80,
"refund_amount":333.80,
"refund_fee":33.80,
"change_fee": 302.80,
"change_ticket_fee":343.80,
"third_approve_id":"hksf83ho93lsbvnos145",



}


```
