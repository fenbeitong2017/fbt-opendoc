2.6.2 用车订单详情

####接口说明
- 1.**最新接口**
- 2.查询用车订单详情接口
  通过该接口可以查询企业使用分贝通APP下的用车订单详情信息



请求方式|请求地址
----|---
POST|/open/api/car/order/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonobject |Y|
data.order_id| 用车订单id|string|Y|

请求示例：

```

	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":"1",
	"data":{
		"order_id":"523234c1323445353dd0"
	}



```
返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
order_id |订单id| String | Y |23456y6uy
vorder_id|供应商订单id| String |Y|
can_process |是否可查看订单| Boolean|Y|true,false
em_name | 下单人| string | Y |例：韩冰
em_tel |下单人手机号| string |Y|例：15070713001
tel |用车人手机号| string | Y |例：15070713088
status|订单状态| Integer |Y|700
status_info |订单状态名| string | Y |
city |城市编码| Integer |Y|1000001:北京
city_name |城市名| string | Y |北京
type |用车类型| string | Y |0：实时；1：预约；2：接机；3：送机
total_price |订单金额| Double | Y |88.99
coupon_amount |优惠券金额|Double|Y|99.00 
distance |行驶距离| Double |Y|99.22
is_complaint|是否已投诉| boolean|Y|true
comment |评论信息| jsonobject | N |
comment.score |评分| Integer |N  |1
comment.content |评价信息| string | N |太差 
order_time|下单时间| String|Y|格式：yyyy-MM-dd HH:mm:ss
schedule_time |用车时间| String | Y |yyyy-MM-dd HH:mm:ss
remark_reason|备注| string|N|出差使用
remark_detail|备注明细| string|N|北京出差使用
exceeded |是否超标| Boolean | N |false
exceed_info |超标信息| jsonobject | N |超标信息
exceed_info.reason |超标原因| string|N|没有原因
exceed_info.comment |超标补充说明|string|N |超标
cost_attribution |费用归属| string |Y|人力部//按部门费用归属;国开行项目:按项目
spec |用车类型信息|jsonobject|Y|类型信息
spec.id |车辆类型id	|Integer|Y| 100:舒适；400：七座商务；200：豪华型；600:快车
spec.name|用车类型名称| String |Y 
price_detail | 费用明细| jsonarray|Y|可能是空数组
price_detail.name |费用名称| string | Y |加班
price_detail.amount |费用金额|Double|Y|44.22
price_detail.type|费用类型| String | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
driver_info|司机信息| jsonobject |N|可能为空数据
driver_info.driver_name|司机姓名| string|N|王师傅
driver_info.driver_phone|司机手机| string|N|17090900988
driver_info.driver_card |车牌号	| string | N |京Q87899
driver_info.driver\_car_type |车型号| string |N|
driver_info.driver_level |司机评分| Double | N |5.0
driver_info.driver\_order_count|接单数| Integer|N|3  可能为空（神州没有），注意兼容
driver_info.driver_car_color|车辆颜色| string|N|红色
driver_info.driver_avatar|司机头像| string | N |可能为空（神州没有），注意兼容
departure_place|出发地信息| jsonobject | Y |出发地信息
departure_place.name |出发地名称| String|Y|国贸
departure_place.address |出发地详细地址| String | Y|国贸大楼 
departure_place.dlng | 出发地经度| Double|Y|12.22
departure_place.dlat|出发地纬度| Double | Y |55.22
arrival_place |目的地信息|jsonobject|Y|目的地信息
arrival_place.name |目的地名称| String | Y |东大桥
arrival_place.address |目的地详细地址| String |Y|东大桥地铁站
arrival_place.tlng | 目的地经度| Double|Y|77.22
arrival_place.tlat|目的地纬度| Double | Y |22.22
insurance_info |保险信息	| jsonarray | N |可能是空Array
insurance_info.category_code |保险类型id|Integer|N|
insurance_info.category_name |保险类型名| String | N |意外险
insurance_info.desc |保险描述信息|String|N|
insurance_info.desc_link |保险说明连接| String | N |url跳转
insurance_info.unit_price |单价| Double |N|8.22
insurance_info.insurant_list |被保人信息列表	| jsonarray | N |列表信息
insurance_info.insurant_list.insurant_name |被保人姓名|String|N|张三
insurance_info.insurant_list.premium |投保金额| String | N |7.2
insurance_info.unit_price |单价| Double |N|2.4
insurance_info.insurant_list.policy_number |供应商保单号|String|N|
insurance_info.insurant_list.start_date |起保时间| String | N |2017-06-27
insurance_info.insurant_list.end_date |终止时间| String | N |2017-06-29
insurance_info.insurant_list.status |状态信息| jsonobject | N |
insurance_info.insurant_list.status.key |状态码| integer | N |
insurance_info.insurant_list.status.value |状态名| String | N |投保中
vendor|供应商信息| jsonobject | Y |
vendor.key |供应商id| Integer|Y|1：滴滴；2：神州 （此字段有修改，原来vendor_id废弃）
vendor.value |供应商名称| String | Y |展示供应商名字的地方使用此字段（原来vendor_name废弃）
customer_service_phone | 客服电话| String|Y|4008009090
is_call_customer_service|是否拨打客服电话| Boolean | Y |（神州司机电话为虚拟号码，订单结束后无法联系司机，需要拨打客服电话）
can_complaint|是否可投诉|Boolean|Y|false 
can_comment |是否可评价| Boolean | Y |false
passenger_name |乘车人姓名| String |Y|王柳   可能为空
personal_pay_price | 个人支付金额| Double|Y|8.2
company_pay_price|企业支付金额|Double|Y| 60.22
need_personal |是否需要个人支付| Integer | Y |0：否；1：是
is_personal_paied |是否个人已支付| Integer |Y|0：否；1：是
total_price_str | 订单金额字符串| String|Y|
status_description | 金额描述| String|Y|金额描述
third_org_id|第三方部门id|string|Y|OWKD8ED8JR4
third_org_name|第三方部门名称|string|Y|服务端
third_parent_org_id|第三方父部门id|string|Y|JD8E8J9EJD8
third_parent_org_name|第三方父部门名称|string|Y|研发部
third_employee_id|第三方员工ID|string|Y|8792794244
third_cost_attribution_id|第三方费用归属ID |string|Y|79984672984398|
third_cost_attribution_type|第三方费用归属ID类型|string|Y|1，部门，2项目








```


{
  "request_id": "4pOh6uSWKXfSFM0UrSm6",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "em_name": "谷健波",
    "customer_service_phone": "400-000-0999",
    "em_tel": "13911381353",
    "status_info": "已完成",
    "passenger_id": "59b8acf023445f70c3eaef80",
    "order_time": "2019-03-07 09:40:24",
    "type": 1,
    "remark_reason": "加班",
    "cost_attribution": "权限测试(勿删)",
    "spec": {
      "name": "出租车",
      "id": 50
    },
    "begin_charge_time": "2019-03-07 09:54:26",
    "can_comment": false,
    "is_call_customer_service": false,
    "tel": "13911381353",
    "order_type": 1,
    "can_complaint": true,
    "exceeded": false,
    "fb_employee_id": "59b8acf023445f70c3eaef80",
    "custom_remark": [],
    "departure_place": {
      "address": "北京市朝阳区平房镇达美中心",
      "dlat": 39.93638610839844,
      "name": "达美中心T2",
      "dlng": 116.51688385009766
    },
    "third_cost_attribution_type": 1,
    "org_unit_id": "5bf2651123445f5335612351",
    "order_id": "5c80768723445f0830149ea1",
    "vorder_id": "3059933",
    "cost_attribution_category": 1,
    "status": 700,
    "personal_pay_price": 0,
    "distance": 0,
    "city": "1000001",
    "can_process": true,
    "cost_attribution_id": "5bf2651123445f5335612351",
    "third_cost_attribution_id": "third_privilege_test",
    "price_detail": [
      {
        "amount": 15,
        "name": "基础费用",
        "type": "price"
      },
      {
        "amount": 0,
        "name": "调度费",
        "type": "tipping"
      },
      {
        "amount": 0,
        "name": "高速费过桥费等额外费用",
        "type": "extraFee"
      }
    ],
    "city_name": "北京市",
    "total_price_str": "¥15.00",
    "need_personal": 0,
    "driver_info": {
      "driver_name": "分贝通师傅",
      "driver_card": "京QqPSnr",
      "driver_avatar": "https://www-ecs.didapinche.com/pics//g/20181024201715-ec0131cc.png",
      "driver_car_type": "北京市通州海鸥出租汽车公司",
      "driver_phone": "16000020021",
      "driver_level": "5.0",
      "driver_order_count": "150"
    },
    "vendor": {
      "value": "嘀嗒",
      "key": 4
    },
    "passager_org_unit": {
      "passenger_org_unit_full_name": "北京分贝金服科技有限公司/权限测试(勿删)",
      "passenger_org_unit_id": "5bf2651123445f5335612351",
      "passenger_org_unit_name": "权限测试(勿删)"
    },
    "sub_status": 0,
    "total_price": 15,
    "finish_charge_time": "2019-03-07 09:57:08",
    "passenger_name": "谷健波",
    "arrival_place": {
      "address": "北京市朝阳区平房镇达美中心",
      "tlng": 116.495986,
      "name": "四惠枢纽站-公交站",
      "tlat": 39.907329
    },
    "schedule_time": "2019-03-07 10:15:00",
    "complaint": true,
    "company_pay_price": 15,
    "comment": {
      "score": 2,
      "content": ""
    },
    "is_personal_paied": 1
  }
}




{
    "request_id": "bzrjeo6329O6xwajy8uc",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "third_org_name": "钉钉测试3.22",
        "em_name": "一把就",
        "customer_service_phone": "10101111",
        "em_tel": "18911207670",
        "third_parent_org_name": "钉钉测试3.22",
        "status_info": "已取消",
        "passenger_id": "5c65124e23445f483068b917",
        "order_time": "2019-04-11 10:39:58",
        "type": 2,
        "remark_reason": "",
        "cost_attribution": "钉钉测试3.22",
        "spec": {
            "name": "舒适型",
            "id": 100
        },
        "can_comment": false,
        "is_call_customer_service": true,
        "tel": "18911207670",
        "order_type": 1,
        "can_complaint": false,
        "exceeded": false,
        "fb_employee_id": "5c65124e23445f483068b917",
        "custom_remark": [],
        "departure_place": {
            "address": "北京首都国际机场T2航站楼",
            "dlat": 40.07958,
            "name": "首都国际机场",
            "dlng": 116.59348
        },
        "third_cost_attribution_type": 1,
        "company_name": "钉钉测试3.22",
        "org_unit_id": "5c94844d23445f1dff51fac6",
        "order_id": "5caea8fd23445f28ffc0f65b",
        "vorder_id": "6678461106474319875",
        "cost_attribution_category": 1,
        "status": 610,
        "personal_pay_price": 0,
        "distance": 0,
        "city": "1000001",
        "can_process": false,
        "cost_attribution_id": "5c94844d23445f1dff51fac6",
        "third_cost_attribution_id": "ding284e8ddc05b1043135c2f4657eb6378f",
        "price_detail": [],
        "city_name": "北京市",
        "total_price_str": "¥0.00",
        "need_personal": 0,
        "vendor": {
            "value": "神州",
            "key": 2
        },
        "passager_org_unit": {
            "passenger_org_unit_full_name": "钉钉测试3.22",
            "passenger_org_unit_id": "5c94844d23445f1dff51fac6",
            "passenger_org_unit_name": "钉钉测试3.22"
        },
        "third_parent_org_id": "ding284e8ddc05b1043135c2f4657eb6378f",
        "sub_status": 0,
        "total_price": 0,
        "remark_detail": "",
        "third_employee_id": "manager2487",
        "third_org_id": "ding284e8ddc05b1043135c2f4657eb6378f",
        "passenger_name": "家家酒",
        "arrival_place": {
            "address": "北京首都国际机场T2航站楼",
            "tlng": 116.397026,
            "name": "故宫博物院",
            "tlat": 39.918058
        },
        "schedule_time": "2019-04-11 10:45:00",
        "complaint": false,
        "company_pay_price": 0,
        "is_personal_paied": 0
    }
}

```

