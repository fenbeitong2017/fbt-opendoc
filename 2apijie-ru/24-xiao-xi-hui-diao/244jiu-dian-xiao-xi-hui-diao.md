字段|名称|类型|必填|详情
----|----|---|---|---
order_id |订单id|String| Y |9884hhkhfsk
type_pame |订单类型名称 |String| Y |火车
type |订单类型| Integer | Y |酒店:4
status |订单状态|Integer| Y |订房成功:2501
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
apply_id|申请单ID|String|Y|
apply_name|申请人姓名|String |Y|张三
contact_phone|联系电话|String|Y|
dept_name|部门名称|String |Y|事业部
total_day|出差天数|String |Y|3（单位:天）
budget_money|预估费用总计|Integer |Y|单位：分
monetary_unit|货币单位|String |Y|人民币
estimated_amount|预估费用|Integer |Y|单位：分
third_remark|出差事由备注|String|Y|
third_remark|出差事由备注|String|Y|出差
use_name|使用人姓名|String|Y|李四
use_phone|使用人手机号|String|Y|
use_dep|使用人部门|String|Y|人力部
total_price |总价 | Integer| Y |388
actual_price|原始价格|Integer|不带手续费的价格
refund_amount|退票费|Integer|Y|供应商退给我们的钱
refund_fee|手续费|Integer|Y|退票产生的手续费
checkin_date|入住时间|String|Y|2018-01-01
checkout_date|离店时间|String|Y|2018-01-06











































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
