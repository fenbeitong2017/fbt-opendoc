根据企业appId/appKey等参数请求鉴权接口，返回请求Token

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
total_price |订单金额| Integer | Y |88
status.key|订单状态| Integer |Y|99
departure_place.name |出发地| string|Y|例：北京
arrival_place.name |目的地| string | Y |例：上海
em_name | 下单人| string | Y |例：韩冰
em_tel |下单人手机号| string |Y|例：15070713001
order_time |下单时间| string | Y |2017-09-11 11:08:58
cost_attribution |费用归属| string |Y|乘机人1/乘机人2/
type |用车类型| string | Y |0：实时；1：预约；2：接机；3：送机
spec.id |车辆类型	|Integer|Y| 100:舒适；400：七座商务；200：豪华型；600:快车
vendor.key |供应商| Integer |Y|2：神州
driver_name|司机姓名| string|Y|王师傅，dave han
driver_card |车牌号	| string | Y |英文字符,数字
driver\_car_type |品牌车型| string |Y|别克
driver_level |司机评分| string | Y |5.0
driver\_order_count|接单数| string|Y|3
tel |用车人手机号| string | Y |例：15070713088
begin\_charge_time |出发时间| string | Y ||
finish\_charge_time |到达时间| array|Y||
category_code |保险险种| Integer | Y ||
policy_number | 保单编号| string|Y||
status |保单状态	| string | Y ||
insurant_name |被保人姓名|string|Y||
insurant_amount |保险数量| Integer | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段|
premium |保险保费| Double |Y||




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

