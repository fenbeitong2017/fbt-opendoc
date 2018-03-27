请求方式|请求地址
----|---
POST|/open/api/train/order/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y||
data.order_id| 查询状态|string |Y|5aab90ac279863130a86296f|

请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
	  "order_id":"5aab90ac279863130a86296f"
	}
}


```



响应结果:

```

{
    "request_id": "gWwcHPzSZaY2oOaXkWY9",
    "code": 0,
    "msg": "success",
    "data": {
        "order_basic_info": {
            "order_id": "5aab90ac279863130a86296f",
            "create_time": 1521193133629,
            "employee_name": "韩树起",
            "employee_phone": "17080151667",
            "total_price": 563,
            "order_status": {
                "key": 3101,
                "value": "已取消"
            },
            "comment": "",
            "remark_reason": "其他",
            "remark_detail": "",
            "apply_id": "",
            "is_grab_order": false,
            "use_customer12306_account": false,
            "exceeded": false,
            "is_external_order": 0,
            "total_price_str": "￥563.00"
        },
        "passengers_info": [
            {
                "passenger_info": {
                    "passenger_id": "5aa23c8923445f33d46d9899",
                    "name": "滚滚滚",
                    "mobile_no": "17080151777",
                    "identity_no": "123456",
                    "identity_type": {
                        "key": 2,
                        "value": "护照"
                    }
                },
                "ticket_info": {
                    "seat_no": "O",
                    "seat_type": "二等座",
                    "ticket_price": 553,
                    "seat_location": "",
                    "ticket_no": "",
                    "product_id": "5aab90ad279863130a862970",
                    "can_group_change": true,
                    "ticket_status": {
                        "key": 3101,
                        "value": "已取消"
                    }
                },
                "refund_info": {
                    "refund_money": 0,
                    "refund_fee": 0,
                    "reason": ""
                },
                "endorse_info": {
                    "supplementary_payment": 0,
                    "diff_price": 0,
                    "endorse_fee": 0,
                    "reason": ""
                },
                "ticket_tips": ""
            }
        ],
        "contact_info": {
            "contact_name": "滚滚滚",
            "contact_phone": "17080151777"
        },
        "insurance_info": [
            {
                "category_code": 3,
                "category_name": "火车意外险",
                "desc": "火车意外险",
                "desc_link": "https://static.fenbeitong.com/mobile/jiaotong.html",
                "unit_price": 10,
                "insurant_list": [
                    {
                        "insurant_name": "滚滚滚",
                        "premium": 10,
                        "status": {
                            "key": 3,
                            "value": "已取消"
                        },
                        "policy_number": "",
                        "start_date": "2018-04-09",
                        "end_date": "2018-04-10",
                        "insurance_link": {}
                    }
                ]
            }
        ],
        "can_process": true,
        "cost_attribution": "北京分贝金服科技有限公司",
        "check_info": [
            {
                "title": "未提前天预订火车票",
                "reason": "票数不够了",
                "comment": ""
            }
        ],
        "price_detail": [
            {
                "key": "票价",
                "price": "553.00",
                "amount_desc": "1人",
                "dc": 1
            },
            {
                "key": "火车意外险",
                "price": "10.00",
                "amount_desc": "1份",
                "dc": 1
            },
            {
                "key": "优惠券",
                "price": "0.00",
                "amount_desc": "",
                "dc": -1
            }
        ],
        "route_info": {
            "train_code": "G101",
            "train_no": "240000G1010D",
            "from_station_name": "北京南",
            "from_station_code": "VNP",
            "to_station_name": "上海虹桥",
            "to_station_code": "AOH",
            "start_time": "06:43",
            "arrive_time": "12:39",
            "run_time": "5:56",
            "arrive_days": "0",
            "train_start_date": "20180409",
            "train_end_date": "20180409",
            "choose_seat_msg": ""
        }
    }
}


```














