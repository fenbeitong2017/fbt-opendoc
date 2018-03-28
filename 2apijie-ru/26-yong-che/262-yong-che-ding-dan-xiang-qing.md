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
data || jsonstring |Y|
data.order_id| 用车订单id|string|Y|

请求示例：

```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"523234c1323445353dd0"
	}
}


```
返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
order_id |订单id| String | Y |23456y6uy
vorder_id|供应商订单id| String |Y
can_process |是否可查看订单| Boolean|Y|例：北京
em_name | 下单人| string | Y |例：韩冰
em_tel |下单人手机号| string |Y|例：15070713001
tel |用车人手机号| string | Y |例：15070713088
status|订单状态| Integer |Y|700
status_info |订单状态名| string | Y |
city |城市编码| Integer |Y|
city_name |城市名| string | Y |0：实时；1：预约；2：接机；3：送机
type |用车类型| string | Y |0：实时；1：预约；2：接机；3：送机
total_price |订单金额| Double | Y |88
coupon_amount |优惠券金额|Double|Y|99.00 
distance |行驶距离| Double |Y|99.22
is_complaint|是否已投诉| boolean|Y|true
comment |评论信息| jsonobject | N |
comment.score |评分| Integer |N  |1
comment.content |评价信息| string | N |太差  
remark_reason|备注| string|N|35rdfdf
exceeded |是否超标| Boolean | N |false
exceed_info |超标信息| jsonobject | N 
exceed_info.reason |超标原因| string|N|没有原因
exceed_info.comment |超标补充说明|string|N |超标
cost_attribution |费用归属| string |Y|乘机人1/乘机人2/
spec |用车类型信息|jsonobject|Y|类型信息
spec.id |车辆类型id	|Integer|Y| 100:舒适；400：七座商务；200：豪华型；600:快车
spec.name|用车类型名称| String |Y 
price_detail | 费用明细| jsonarray|Y|可能是空数组
price_detail.name |费用名称| string | Y |加班
price_detail.amount |费用金额|Double|Y|44.22
price_detail.type|费用类型| String | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
driver_info|司机信息| jsonobject |N|可能为空数据
driver_info.driver_name|司机姓名| string|N|王师傅，dave han
driver_info.driver_card |车牌号	| string | N |英文字符,数字
driver_info.driver\_car_type |品牌车型| string |N|别克
driver_info.driver_level |司机评分| string | N |5.0
driver_info.driver\_order_count|接单数| string|N|3
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
insurance_info |保险信息	| jsonarray | N |
insurance_info.category_code |保险类型id|Integer|N|
insurance_info.category_name |保险类型名| String | N |
insurance_info.unit_price |单价| Double |N|8.22
insurance_info.insurant_list |被保人信息列表	| jsonarray | N |列表信息
insurance_info.insurant_list.insurant_name |被保人姓名|String|N|张三
insurance_info.insurant_list.premium |投保金额| String | N |7.2
insurance_info.unit_price |单价| Double |N|2.4
vendor|出发地信息| jsonobject | Y 
vendor.key |供应商id| Integer|Y|1：滴滴；2：神州 （此字段有修改，原来vendor_id废弃）
vendor.value |供应商名称| String | Y |展示供应商名字的地方使用此字段（原来vendor_name废弃）
customer_service_phone | 客服电话| String|Y|4008009090
is_call_customer_service|是否拨打客服电话| Boolean | Y |（神州司机电话为虚拟号码，订单结束后无法联系司机，需要拨打客服电话）
can_complaint|是否可投诉|Boolean|Y|false 
can_comment |是否可评价| Boolean | Y |false
passenger_name |乘车人姓名| String |Y|王柳
personal_pay_price | 个人支付金额| Double|Y|8.2
company_pay_price|企业支付金额|Double|Y| 60.22
need_personal |是否需要个人支付| Integer | Y |0：否；1：是
is_personal_paied |是否个人已支付| Integer |Y|0：否；1：是
total_price_str | 订单金额字符串| String|Y
status_description | 金额描述| String|Y|金额描述


```


{
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "595242ef1a671d2446d8dc82",
        "vorder_id": "1031014486130567180",
        "can_process": true,
        "cost_attribution": "北京分贝金服科技有限公司",
        "em_name": "常龙",
        "em_tel": "18911681154",
        "tel": "18911681154",
        "status": 700,
        "sub_status": 0,
        "sub_status_name": "",
        "status_info": "已完成",
        "city": 1,
        "city_name": "",
        "type": 0,
        "total_price": 23.56,
        "price_detail": [
            {
                "name": "正常行驶距离费",
                "amount": 0.16,
                "type": "normal_fee"
            },
            {
                "name": "快车时长费",
                "amount": 22.4,
                "type": "normal_time_fee"
            },
            {
                "name": "企业实付金额",
                "amount": 22.56,
                "type": "company_real_pay"
            },
            {
                "name": "企业应付金额",
                "amount": 22.56,
                "type": "company_pay"
            },
            {
                "name": "短途意外险",
                "amount": 1,
                "type": "insurance"
            }
        ],
        "coupon_amount": 0,
        "driver_info": {},
        "spec": {
            "id": 600,
            "name": "快车"
        },
        "distance": 0.1,
        "order_time": "2017-06-27 19:35:23",
        "schedule_time": "2017-06-27 19:35:23",
        "departure_place": {
            "name": "东大桥路24号楼",
            "address": "北京市朝阳区光华路甲9号东大桥路",
            "dlat": 39.9150390625,
            "dlng": 116.4510498046875
        },
        "arrival_place": {
            "name": "团结湖-地铁站",
            "address": "地铁10号线",
            "tlat": 39.933722,
            "tlng": 116.461743
        },
        "is_complaint": false,
        "comment": null,
        "remark_reason": "出差",
        "remark_detail": "去北京",
        "insurance_info": [
            {
                "category_code": 4,
                "category_name": "短途意外险",
                "desc": "1元最高保障10万元",
                "desc_link": "https://static.fenbeitong.com/mobile/carAccidentInsurance.html",
                "unit_price": 1,
                "insurant_list": [
                    {
                        "insurant_name": "常龙",
                        "premium": 1,
                        "status": {
                            "key": 6,
                            "value": "投保成功"
                        },
                        "policy_number": "",
                        "start_date": "2017-06-27",
                        "end_date": "2017-06-28",
                        "insurance_link": {}
                    }
                ]
            }
        ],
        "exceeded": false
    }
}



```

