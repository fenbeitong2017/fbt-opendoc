字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|string| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|string|Y|分贝通
type_name |订单类型名称 |string| Y |火车
type |订单类型| integer | Y |火车:3
status |订单状态|integer| Y |已完成:3202
apply_name|申请人姓名|string |Y|张三
contact_phone|申请人联系电话|string|Y|
contact_name|联系人姓名|string |Y|李四（申请人和联系人和使用人可以是同一人，也可以是不同的人）
phone|联系人电话|string|Y|18090180901
use_name|使用人姓名|string |Y|王五
use_phone|使用人联系电话|string|Y|18767909349
use_depname|使用人部门名称|string|Y|人事部
dept_name|申请人部门名称|string |Y|事业部
monetary_unit|货币单位|string |Y|人民币
third_remark |三方备注|string|Y|需要进行备注的信息，可以当备用字段
budget_money|预估费用总计|double |Y|单位：分
estimated_amount|预估费用|double |Y|单位：分
order_id |订单id|string| Y |9884hhkhfsk
total_price |订单金额 | double| Y |302.90，总价=火车票票价+保险价格-优惠券价格
train_code|车次|string|Y|
departure_place|出发站|string|Y|北京站
destination_place|到达站|string|Y|上海站
begin_time|火车出发时间|string |Y|2018-01-01 10:04:30
end_time|火车到达时间|string|Y|2018-01-01 10:04:30
premium|保险费|double|Y| 88.99
refund_amount|退票费|double|Y| 78.33
refund_fee|手续费|double|Y|9.00
change_fee|改签费|double|Y|9.00
change_ticket_fee|改签差价手续费|double|Y|1.22
third_approve_id|申请单ID|string|Y|jljo8iewnfsl
create_time | 下单时间 | string | Y |2018-04-05 13:13:34
coupon_amount | 优惠券金额 | double | Y |10.25





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


返回数据格式:

```
{
    "code":"1", //1表示成功，其他表示失败
    "msg":"success"
}





```
