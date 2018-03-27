
请求方式|请求地址
----|---
POST|/open/api/train/order/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----|
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.order_id| 查询状态|string |Y|5aab90ac279863130a86296f

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



响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
order\_id| 订单ID|string |Y|5aab90ac279863130a86296f
create\_time|订单创建时间 |integer |Y|
employee\_name| 下单人姓名|string | Y |
total\_price |总价| double | Y |
order\_status |订单状态|jsonobject | Y |详细订单状态参照火车状态码
use\_customer12306\_account |是否使用12306账号| jsonarray | Y |
exceeded|| boolean|  Y |
is\_grab\_order|是否抢票订单 |boolean | Y |
is\_external\_order |是否外采订单| integer |  Y |
employee\_remark|用户备注| string|  Y |
total\_price\_str |价格字符串| string |  Y |订单金额字符串
passengers\_info|乘客信息数组 |jsonarray |  Y |
passenger\_info|乘客信息 |jsonobject | Y |
passenger\_id |乘客id| string | Y |4567988645345
name|姓名| string|  Y |张三
mobile\_no|手机号码 |string | Y |17080187999
identity\_no |身份号码| string |  Y |23456789098765
identity\_type|身份证件类型| jsonobject|  Y |身份证
ticket\_info |票信息| jsonobject |  Y |  
seat\_type |席座类型| string | Y |二等座
ticket\_price|票价| double|  Y |100
seat\_location|坐席位置 |string | Y |08车厢,10B座
ticket\_no |票号| string |  Y |E931804546
can\_group_change |批量改签| boolean |  Y | 非:高级软卧", "软卧", "硬卧 均可以批量改签 false
ticket\_status|订单状态|jsonobject | Y |详细订单状态参照火车订单状态码
refund\_info |退票信息| jsonarray | Y |
refund\_money|退票金额| double|  Y |
refund\_fee|退票费 |double | Y |
reason |退票原因| string |  Y |
endorse\_info|改签信息| boolean|  Y |
supplementary\_payment |改签生成新单的价格| double |  Y |  
diff\_price|改签差价| double| Y |
endorse\_fee |改签手续费| double | Y | 
reason|改签原因| string| Y |
ticket\_tips |票状态说明| string | Y | 
insurance\_info|保险信息 |jsonarray | Y |
can\_process |是否可查看企业订单| boolean |  Y |
cost\_attribution|费用归属| string|  Y |
contact\_info |联系人信息| jsonobject | Y|  
contact\_name|联系人姓名| string| Y |
contact\_phone |联系人手机号| string | Y |
refund\_price\_info|退票信息| jsonobject|N|可能为空，为空不展示
refund\_price |退订金额（票价单价)|double|N| 退订金额（票价）
refund\_cost |退票手续费| double |N|退订费（扣除的钱）
refund\_total\_price|退票总价 |double |N|退款总额（到手的钱）
endorse\_price\_info |改签信息| jsonobject | N |可能为空，为空不展示
endorse\_price|改签差价（差价）| double|  N |改签差价（差价）
endorse\_cost |改签手续费| double |  N | 改签费（改签费）
endorse\_total\_price|改签总价| double| N |改签总额（改签总花费即差价+改签费)
price\_detail |价格信息| jsonobject | N | 
key|费用明细key| string| N |
price |费用明细金额| string | N| 
amount\_desc |费用明细金额|string|N
dc| 正负|integer |N|如票价是正（1）、优惠券是负（-1
grab\_info|抢票信息|jsonobject|N|



```

{
    "request_id": "gWwcHPzSZaY2oOaXkWY9",
    "code": 0,
    "msg": "success",
    "data": {
        "order_basic_info": {
            "order_id": "5a0ec1d627986320cbdfd27f",
            "create_time": 1510916567259,
            "employee_name": "刘维中",
            "total_price": 34,
            "order_status": {
                "key": 3400,
                "value": "有退改记录"
            },
            "comment": "",
            "use_customer12306_account": false,
            "exceeded": false,
            "is_grab_order": false,                           //是否抢票订单
            "is_external_order": 1, // 是否是外采订单
            "employee_remark": "", // 用户备注
            "total_price_str": "￥34" // 订单金额字符串
        },
        "passengers_info": [
            {
                "passenger_info": {
                    "passenger_id": "5a0ec1aa23445f2808a20323",
                    "name": "徐璞",
                    "mobile_no": "15311412713",
                    "identity_no": "410581199212019110",
                    "identity_type": {
                        "key": 1,
                        "value": "身份证"
                    }
                },
                "ticket_info": {
                    "seat_no": "O",
                    "seat_type": "二等座",
                    "ticket_price": 17,
                    "seat_location": "08车厢,10B座",
                    "ticket_no": "E931804546",
                    "product_id": "5a0ec1d727986320cbdfd281",
                    "can_group_change": true,
                    "ticket_status": {
                        "key": 3801,
                        "value": "退票成功"
                    }
                },
                "refund_info": {
                    "refund_money": 17,
                    "refund_fee": 0,
                    "reason": ""
                },
                "endorse_info": {
                    "supplementary_payment": 0,
                    "diff_price": 0,
                    "endorse_fee": 0,
                    "reason": ""
                },
                "ticket_tips": ""// 票状态说明
            },
            {
                "passenger_info": {
                    "passenger_id": "5a0ec19d23445f2808a20322",
                    "name": "贾斌",
                    "mobile_no": "18500986085",
                    "identity_no": "510823198905064717",
                    "identity_type": {
                        "key": 1,
                        "value": "身份证"
                    }
                },
                "ticket_info": {
                    "seat_no": "O",
                    "seat_type": "二等座",
                    "ticket_price": 17,
                    "seat_location": "08车厢,11A座",
                    "ticket_no": "E931804546",
                    "product_id": "5a0ec1d727986320cbdfd280",
                    "can_group_change": true,
                    "ticket_status": {
                        "key": 3801,
                        "value": "退票成功"
                    }
                },
                "refund_info": {
                    "refund_money": 17,
                    "refund_fee": 0,
                    "reason": ""
                },
                "endorse_info": {
                    "supplementary_payment": 0,
                    "diff_price": 0,
                    "endorse_fee": 0,
                    "reason": ""
                },
                "ticket_tips": ""// 票状态说明
            }
        ],
        "contact_info": {
            "contact_name": "刘维中",
            "contact_phone": "18601016943"
        },
        "insurance_info": [],
        "can_process": false,
        "cost_attribution": "北京分贝金服科技有限公司",
        "check_info": [
            {
                "title": "未提前2天预订火车票",
                "reason": "陪客户出行",
                "comment": ""
            },
            {
                "title": "未选择推荐车次的理由",
                "reason": "票数不够了",
                "comment": ""
            }
        ],
        "route_info": {
            "train_code": "D379",
            "train_no": "5l0000D37961",
            "from_station_name": "上海虹桥",
            "from_station_code": "AOH",
            "to_station_name": "金山北",
            "to_station_code": "EGH",
            "start_time": "07:02",
            "arrive_time": "07:20",
            "run_time": "18",
            "arrive_days": "0",
            "train_start_date": "20171206",
            "train_end_date": "20171206",
            "choose_seat_msg": "指定座位余票不足，已为您随机申请座位"     //选座结果提示
        },
        "refund_price_info":{ // 可能为空，为空不展示
            "refund_price": 600,  // 退订金额（票价）
            "refund_cost": 80, // 退订费（扣除的钱）
            "refund_total_price": 520, // 退款总额（到手的钱）
        },
        "endorse_price_info":{ // 可能为空，为空不展示
            "endorse_price": 600,  // 改签差价（差价）
            "endorse_cost": 80, // 改签费（改签费）
            "endorse_total_price": 520, // 改签总额（改签总花费即差价+改签费）
        },
        "price_detail":[
            {
                "key":"", // 费用明细key，如“票价”
                "price":"1500", // 费用明细金额
                "amount_desc":"2人", // 数量描述，如2人
                "dc":1 // 正负，如票价是正（1）、优惠券是负（-1）
            },
            ...
        ],
        "grab_info": {//抢票信息“待支付”“抢票中”“出票失败”“已取消”状态的抢票订单存在该信息
            "train_code": "D379,D325",
            "from_station_name": "上海虹桥",
            "to_station_name": "金山北",
            "seat_type": "二等座,一等座",
            "train_start_date": "20171206"
        }
    }
}


```














