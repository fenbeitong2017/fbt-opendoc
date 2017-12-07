字段|名称|类型|必填|详情
----|----|---|---|---
order_id |订单id|String| Y |9884hhkhfsk
total_price |订单金额 | Double| Y |302
type_pame |订单类型名称 |String| Y |用车
type |订单类型| Integer | Y |用车:3
status |订单状态|Integer| Y |已完成:3202
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
apply_id|申请单ID|String|Y|
apply_name|申请人姓名|String |Y|张三

contact_phone|联系电话|String|Y|
dept_name|部门名称|String |Y|事业部
total_day|出差天数|String |Y|3（单位:天）
begin_day|开始时间|String |Y|
end_day|开始时间|String |
budget_money|预估费用总计|Integer |单位：分
monetary_unit|货币单位|String |人民币
estimated_amount|预估费用|Integer |单位：分







































































































































































数据格式:


```
{
"order_id":"hksf83ho93lsbvnos145",
"total_price": 302,
"type_name":"火车",
"type":3,
"status":3202,
"company_id":"5747fbc10f0e60e0709d8d89",
"company_name":"分贝通"

}


```
