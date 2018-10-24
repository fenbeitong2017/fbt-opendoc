#### 2.4.2 
####接口说明
- 1.**最新接口**
- 2.用车消息推送接口,现有接口推送消息只包含叫车成功状态


字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|string| Y | 595c4c225f281a59eb295bb5
company_name | 公司名称|string|Y|北京分贝通科技有限公司
type_name |订单类型名称 |string| Y |用车
type |订单类型| integer | Y |用车:2
status |订单状态|integer| Y |已完成:700
use_name |使用人姓名|string| Y |张三
use_phone |使用人手机号|string| Y | 13080899009(用车无需审批)
use_deptname |使用人部门|string|Y|研发部
monetary_unit |货币单位|string| Y | 人民币
order_id |订单id|string| Y |9884hhkhfsk
total_price |订单金额 | double| Y |77.30
begin_time |开始计费时间|string|Y|2018-01-01 10:10:10
end_time|结束计费时间|string |Y|2018-01-01 11:10:10
departure_place |出发地|string|Y|中关村
destination_place|目的地|string |Y|北土城地铁站
third_approve_id|审批单ID|string |N|9d8hj84kfd5hf5g46kb(如果下单时选择了第三方推送的审批单)
third_remark |三方备注|string|N|备注的信息(如果下单时选择了第三方推送的审批单)
create_time | 下单时间 | string | Y |2018-04-05 13:13:34
coupon_amount | 优惠券金额 | double | Y |10.25
third_employee_id | 第三方用户id | string | Y |第三方用户ID










数据格式:


```


{"coupon_amount":0.0,
"type_name":"用车",
"monetary_unit":"人民币",
"create_time":"2018-07-18 10:25:24",
"total_price":20.32,
"company_id":"595c4c225f281a59eb295bb5",
"destination_place":"南岗区哈西万达广场写字楼",
"end_time":"1970-01-01 00:00:00",
"begin_time":"2018-07-18 10:32:24",
"type":2,
"use_phone":"17967538291",
"departure_place":"道里区融江路32-20号附近",
"company_name":"北京分贝通科技有限公司",
"use_depname":"办公室",
"order_id":"5b4ea5135f281a392c61176e",
"use_name":"郭德",
"third_approve_id":"hksf83ho93lsbvnos145",
"third_remark":"通过第三方系统创建",
"third_employee_id":"oule893883892iue38e8",
"status":700}


```




返回数据格式:

```
{
    "code":"1", //1表示成功，其他表示失败
    "msg":"success"
}




```
