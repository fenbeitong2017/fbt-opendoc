字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|string| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|string|Y|分贝通
type_pame |订单类型名称 |string| Y |酒店
type |订单类型| integer | Y |酒店:4
status |订单状态|integer| Y |订房成功:2501
apply_name|申请人姓名|string |Y|张三
contact_phone|联系电话|string|Y|
dept_name|部门名称|string |Y|事业部
monetary_unit|货币单位|string |Y|人民币
third_remark|出差事由备注|string|Y|出差
order_id |订单id|string| Y |9884hhkhfsk
total_price |总价 | double| Y |388.00
budget_money|预估费用总计|double |Y|单位：分
estimated_amount|预估费用|double |Y|单位：分
refund_amount| 金额|double|Y|供应商退给我们的钱
refund_fee|手续费|double|Y|退票产生的手续费
begin_time|入住时间|string|Y|2018-01-01
end_time|离店时间|string|Y|2018-01-06
third_approve_id|申请单ID|string|Y||




数据格式:


```
{
"company_id":"5747fbc10f0e60e0709d8d89",
"company_name":"分贝通",
"type_name":"酒店",
"type":4,
"status":2501,
"apply_name":"李四",
"contact_phone":"567689752",
"dept_name":"人力部
"monetary_unit":人民币,
"third_remark":"搜索",
"order_id":"hksf83ho93lsbvnos145",
"total_price": 302,
"budget_money":787.80,
"begin_time":"2018-01-01",
"end_time":"2018-01-01",
"premium":32.80,
"refund_amount":333.80,
"refund_fee":33.80,
"third_approve_id":"hksf83ho93lsbvnos145",



}





```
