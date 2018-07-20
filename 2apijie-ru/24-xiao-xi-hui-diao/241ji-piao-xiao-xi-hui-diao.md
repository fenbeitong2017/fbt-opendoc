#### 2.4.1 
####接口说明
- 1.**最新接口**
- 2.机票消息推送接口,现有接口推送消息只包含出票成功，退票成功，改签成功状态



 字段 | 名称 | 类型 | 必填 | 详情 
 --- | --- | --- | --- | --- 
 company\_id | 公司id | string | Y | 5747fbc10f0e60e0709d8d89 
 company\_name | 公司名称 | string | Y | 分贝通 
 type\_name | 订单类型名称 | string | Y | 机票 
 type | 订单类型 | integer | Y | 机票:1 
 status | 订单状态 | integer | Y | 出票成功:1800 
 apply\_name | 申请人姓名 | string | Y | 张三 
 contact\_phone | 申请人联系电话 | string | Y |17909090909
contact_name|联系人姓名|string |Y|李四（申请人和联系人和使用人可以是同一人，也可以是不同的人）
phone|联系人电话|string|Y|18090180901
use_name|使用人姓名|string |Y|王五
use_phone|使用人联系电话|string|Y|18767909349
use_depname|使用人部门名称|string|Y|人事部
dept\_name | 申请人部门名称 | string | Y | 事业部 
monetary\_unit | 货币单位 | string | Y | 人民币 
third\_remark | 出差事由备注 | string | Y | 出差 
order\_id | 订单id | string | Y | 9884hhkhfsk 
total\_price | 总价 | double | Y | 388.00 总价=票价+保险-优惠券
departure_place|出发地|string|Y|北京
destination_place|目的地|string|Y|上海
begin_time|航班起飞时间|string |Y|2018-01-01 10:04:30
end_time|航班到达时间|string|Y|2018-01-01 10:55:30
 budget\_money | 预估费用总计 | double | Y | 单位：分 
 estimated\_amount | 预估费用 | double | Y | 单位：分 
refund\_amount | 金额 | double | Y | 供应商退给我们的钱 
 refund\_fee | 手续费 | double | Y | 退票产生的手续费 
 third\_approve\_id | 申请单ID | string | Y |
 create_time | 下单时间 | string | Y |2018-04-05 13:13:34
 coupon_amount | 优惠券金额 | double | Y |10.25
 flight_no | 航班号 | string | Y |CA2808
 seat_msg |仓位信息 | string | Y |经济舱


请求数据格式:

```



{"type_name":"机票",
"contact_phone":"17080151666",
"destination_place":上海,
"change_fee":0.0,
"type":1,
"use_phone":"17080151666",
"premium":0.0,
"refund_amount":0.0,
"use_depname":"办公室",
"change_ticket_fee":0.0,
"use_name":"刘丹",
"coupon_amount":0.0,
"contact_name":"刘丹",
"monetary_unit":"人民币",
"company_id":"595c4c225f281a59eb295bb5",
"create_time":"2018-06-21 09:17:58",
"total_price":890.0,
"end_time":"2018-06-22 13:40:00",
"dept_name":"办公室",
"begin_time":"2018-06-22 11:30:00",
"apply_name":"刘丹",
"departure_place":北京,
"phone":"17080151666",
"company_name":"达内时代科技集团有限公司",
"refund_fee":0.0,
"order_id":"5b2afcc13ce30d54dad0bc8c",
"status":1800}
```




返回数据格式:

```

{
    "code":"1", //1表示成功，其他表示失败
    "msg":"success"
}


```



