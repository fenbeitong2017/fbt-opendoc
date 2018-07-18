#### 2.4.3 
####接口说明
- 1.**最新接口**
- 2.火车消息推送接口,现有接口推送消息只包含出票成功，退票成功，改签成功状态

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
change_ticket_fee|改签差价手续费|double|Y|1.20
third_approve_id|审批单ID|string |N|9d8hj84kfd5hf5g46kb(如果下单时选择了第三方推送的审批单)
third_remark |三方备注|string|N|备注的信息(如果下单时选择了第三方推送的审批单)
create_time | 下单时间 | string | Y |2018-04-05 13:13:34
coupon_amount | 优惠券金额 | double | Y |10.25





数据格式:


```

{"type_name":"火车",
"contact_phone":"17608978076",
"destination_place":"北京西",
"change_fee":0.0,
"type":3,
"use_phone":"17608978076",
"refund_amount":0.0,
"use_depname":"办公室",
"train_code":"G618",
"change_ticket_fee":0.0,
"use_name":"刘涛",
"coupon_amount":0.0,
"contact_name":"刘涛",
"monetary_unit":"人民币",
"company_id":"595c4c225f281a59eb295bb5",
"create_time":"2018-07-18 15:58:30",
"total_price":197.0,
"end_time":"2018-07-22 17:41:00",
"dept_name":"办公室",
"begin_time":"2018-07-22 14:58:00",
"apply_name":"刘涛",
"departure_place":"太原南",
"phone":"17608978076",
"company_name":"北京分贝通科技有限公司",
"refund_fee":0.0,
"order_id":"5b4ef3245d88db70c6a5043b",
"third_approve_id":"hksf83ho93lsbvnos145",
"third_remark":"第三方审批备注",
"status":3202}


```


返回数据格式:

```
{
    "code":"1", //1表示成功，其他表示失败
    "msg":"success"
}





```
