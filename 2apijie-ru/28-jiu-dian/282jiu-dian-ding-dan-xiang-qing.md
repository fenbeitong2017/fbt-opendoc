请求方式|请求地址
----|---
POST|/open/api/hotel/order/detail

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.order_id|订单号|string|Y|

请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"5a98fe1b2798636ba9006f1e"					
	}
}


```




```

{
    "request_id": "XGabUT2cyw4Y5IdrsXlS",
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "5a98fe1b2798636ba9006f1e",
        "status": 2301,
        "status_name": "已取消",
        "create_time": 1519975963862,
        "can_process": true,
        "cost_attribution": "北京分贝金服科技有限公司",
        "order_person": "韩树起",
        "order_person_phone": "17080151667",
        "checkin_date": 1522080000000,
        "checkout_date": 1522166400000,
        "city_code": "904",
        "hotel_name": "汉庭南京六合长江路酒店",
        "hotel_lng": "118.837468",
        "hotel_lat": "32.345671",
        "hotel_address": "江苏省南京市六合区雄州街道棠城西路179号",
        "hotel_code": "5a41ed51979d9663f8b4c5de",
        "city_name": "南京市",
        "policy_code": "1",
        "hotel_phone": "025-57508988",
        "bed_type": "(null)",
        "room_code": "DR",
        "room_name": "大床房",
        "room_count": 1,
        "plan_code": "573273659|6647611164||51661617",
        "per_room_night_prices": [
            [
                150
            ]
        ],
        "price_rule": "订单确认后，如在北京时间2018-03-26 23:00:00 （含）点前取消，可全额退款！其它时间不可取消，不可变更。如未入住扣除全额房费。",
        "plan_name": "大床房",
        "price_rule_tag": "取消规则",
        "price": 150,
        "contact_name": "韩树起",
        "contact_phone_no": "17080151667",
        "guest_type": 0,
        "guests": [
            {
                "name": "韩美美",
                "phone_no": "12989890909"
            }
        ],
        "total_price_str": "￥150.00",
        "is_external_order": 0,
        "check_info": [],
        "employee_remark": null,
        "has_enterprise_price": false,
        "other_refund_desc": "无",
        "is_can_apply_refund": false,
        "refund_info": {
            "is_has_refund": false
        },
        "remark_reason": "其他",
        "exceeded": false,
        "insurance_info": [],
        "comment": ""
    }
}



```



