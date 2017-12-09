字段|名称|类型|必填|详情
----|----|---|---|---
order_id |订单id|String| Y |9884hhkhfsk
type_name |订单类型名称 |String| Y |火车
type |订单类型| Integer | Y |火车:3
status |订单状态|Integer| Y |已完成:3202
company_id |公司id|String| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|String|Y|分贝通
apply_id|申请单ID|String|Y|
apply_name|申请人姓名|String |Y|张三
contact_phone|联系电话|String|Y|
dept_name|部门名称|String |Y|事业部
total_day|出差天数|String |Y|3（单位:天）
begin_day|开始时间|String |Y|
end_day|结束时间|String |Y|
budget_money|预估费用总计|Integer |Y|单位：分
monetary_unit|货币单位|String |Y|人民币
estimated_amount|预估费用|Integer |Y|单位：分
third_remark|出差事由备注|String|Y|出差
use_name|使用人姓名|String|Y|李四
use_phone|使用人手机号|String|Y|
use_dep|使用人部门|String|Y|
total_price |订单金额 | Integer| Y |302
train_code|车次|String|Y|
from_station|出发站|String|Y|北京站
to_station|到达站|String|Y|上海站
train_start_time|火车出发时间|String |Y|2018-01-01
trin_end_time|火车到达时间|String|Y|
premium|保险费|Integer|Y|单位：分
refund_amount|退票费|Integer|Y|单位：分
refund_fee|手续费|Integer|Y|单位：分
change_fee|改签费|Integer|Y|单位：分
change_ticket_fee|改签差价手续费|Integer|Y|
endorse_price|改签价格|Integer|Y|







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

"apply_id":"hksf83ho93lsbvnos145",
"apply_name":"李四",
"contact_phone":"567689752",
"dept_name":"人力部",
"total_day":3,
"begin_day":"2018-01-01",
"end_day":""

"budget_money":787,
"monetary_unit":人民币,
"estimated_amount"8887:,
"third_remark":"搜索",
"use_name":"网三",
"use_phone":"125764837980549",
"total_price"565:

"train_code":"1024",
"from_station": "北京",
"to_station":"上海",
"train_start_time":"2018-01-01",
"trin_end_time":"2018-01-01",
"premium":32,
"refund_amount":333,

"refund_fee":33,
"change_fee": 302,
"change_ticket_fee":343,
"endorse_price":30




}


```
