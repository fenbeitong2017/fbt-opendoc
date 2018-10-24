#### 2.4.4
####接口说明
- 1.**最新接口**
- 2.酒店消息推送接口,现有接口推送消息只包含订房成功，退房成功状态


字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|string| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|string|Y|分贝通
type_name |订单类型名称 |string| Y |酒店
type |订单类型| integer | Y |酒店:4
status |订单状态|integer| Y |订房成功:2501
apply_name|申请人姓名|string |Y|张三
contact_phone|申请人联系电话|string|Y|13090323472
contact_name|联系人姓名|string |Y|李四（申请人和联系人和使用人可以是同一人，也可以是不同的人）
phone|联系人电话|string|Y|18090180901
use_name|使用人姓名|string |Y|王五
use_phone|使用人联系电话|string|Y|18767909349
use_depname|使用人部门名称|string|Y|人事部
dept_name|申请人部门名称|string |Y|事业部
monetary_unit|货币单位|string |Y|人民币
order_id |订单id|string| Y |9884hhkhfsk
total_price |总价 | double| Y |388.00,总价=房间价格+保险价格-优惠券价格
refund_amount| 金额|double|Y|供应商退给我们的钱
refund_fee|手续费|double|Y|退票产生的手续费
begin_time|入住时间|string|Y|2018-01-01 00:00:00
end_time|离店时间|string|Y|2018-01-06 00:00:00
hotel_name|酒店名称|string|Y|如家
hotel_address|酒店地址|string|Y|南京市北京路
third_approve_id|审批单ID|string |N|9d8hj84kfd5hf5g46kb(如果下单时选择了第三方推送的审批单)
third_remark |三方备注|string|N|备注的信息(如果下单时选择了第三方推送的审批单)
budget_money|预估费用总计|double |N|单位：分(如果下单时选择了第三方推送的审批单)
estimated_amount|预估费用|double |N|单位：分(如果下单时选择了第三方推送的审批单)
create_time | 下单时间 | string | Y |2018-04-05 13:13:34
coupon_amount | 优惠券金额 | double | Y |10.25
third_employee_id | 第三方用户id | string | Y |第三方用户ID





数据格式:


```
{"type_name":"酒店",
"contact_phone":"15090897656",
"hotel_address":"广元西路319号",
"type":4,
"use_phone":"15090897656",
"premium":0.0,
"refund_amount":0.00,
"use_depname":"企业合作部",
"use_name":"王栋",
"coupon_amount":0.0,
"contact_name":"王栋",
"monetary_unit":"人民币",
"company_id":"595c4c225f281a59eb295bb5",
"create_time":"2018-07-18 16:24:02",
"total_price":780.0,
"end_time":"2018-07-22 00:00:00",
"dept_name":"企业合作部",
"begin_time":"2018-07-20 00:00:00",
"apply_name":"王栋",
"hotel_name":"锦江之星(上海徐家汇交大店)",
"phone":"15090897656",
"company_name":"北京分贝通科技有限公司",
"refund_fee":0.00,
"order_id":"5b4ef9225f281a392c61379f",
"third_approve_id":"hksf83ho93lsbvnos145",
"third_remark":"第三方审批备注",
"third_employee_id":"oule893883892iue38e8",
"status":2501}

```


返回数据格式:

```

{
    "code":"1", //1表示成功，其他表示失败
    "msg":"success"
}




```
