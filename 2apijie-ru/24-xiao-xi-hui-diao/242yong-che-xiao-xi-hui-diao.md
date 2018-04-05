
字段|名称|类型|必填|详情
----|----|---|---|---
company_id |公司id|string| Y | 5747fbc10f0e60e0709d8d89
company_name | 公司名称|string|Y|分贝通
type_pame |订单类型名称 |string| Y |用车
type |订单类型| integer | Y |用车:2
status |订单状态|integer| Y |已完成:700
use_name |使用人姓名|string| Y |张三(用车无需审批)
use_phone |使用人手机号|string| Y | 13080899009(用车无需审批)
use_deptname |使用人部门|string|Y|研发部
monetary_unit |货币单位|string| Y | 人民币
third_remark |三方备注|string|Y|需要进行备注的信息，可以当备用字段
order_id |订单id|string| Y |9884hhkhfsk
total_price |订单金额 | double| Y |77.30
begin_time |开始计费时间|string|Y|2018-01-01 10:10:10
end_time|结束计费时间|string |Y|2018-01-01 11:10:10
departure_place |出发地|string|Y|中关村
destination_place|目的地|string |Y|北土城地铁站
third_approve_id|审批单ID|string |Y|98898hjhkdh546kb
create_time | 下单时间 | string | Y |2018-04-05 13:13:34|
coupon_amount | 优惠券金额 | double | Y |10.25|





数据格式:


```
{
	"company_id":"5747fbc10f0e60e0709d8d89",
	"company_name":"分贝通"
	"type_name":"用车",
	"type":2,
	"status":700,
	"apply_name":"张三",
        "contact_phone":"13080899009",
        "dept_name":"人事部",
	"monetary_unit":人民币,
	"third_remark":"搜索",
	"order_id":"hksf83ho93lsbvnos145",
	"total_price": 302,
	"budget_money":787.80,
	"departure_place": "北京",
	"destination_place":"上海",
	"begin_time":"2018-01-01",
	"end_time":"2018-01-01",
	"third_approve_id":"hksf83ho93lsbvnos145",




      
	

}


```
