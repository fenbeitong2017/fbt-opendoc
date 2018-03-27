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



响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
order_id| 订单ID|string |Y||
create_time|是否抢票订单 |boolean |Y||
employee_name| |jsonobject | Y ||
total_price |出发时间| integer | Y ||
order_status |到达时间|integer | Y ||
comment|火车车次 |string | Y ||
use_customer12306_account |乘客信息| jsonarray | Y ||
exceeded|出发站名称| string|  Y ||
is_grab_order|到达站名称 |string | Y ||
is_external_order |总价| double |  Y ||
employee_remark|是否可以查看订单详情| boolean|  Y ||
total_price_str |是否外采订单| integer |  Y |  1:是,0:否 
passengers_info|订单金额字符串 |string |  Y |订单金额字符串 
passenger_info|火车车次 |string | Y ||
passenger_id |乘客信息| jsonarray | Y ||
name|出发站名称| string|  Y ||
mobile_no|手机号码 |string | Y ||
identity_no |身份号码| double |  Y ||
identity_type|身份证件类型| boolean|  Y ||
ticket_info |票信息| integer |  Y |  1:是,0:否
seat_no|火车车次 |string | Y ||
seat_type |席座类型| jsonarray | Y ||
ticket_price|票价| string|  Y ||
seat_location|坐席位置 |string | Y ||
ticket_no |票号| double |  Y ||
product_id|| boolean|  Y ||
can_group_change || integer |  Y |  1:是,0:否
ticket_status|订单状态|jsonobject | Y ||
refund_info |退票信息| jsonarray | Y ||
refund_money|退票金额| string|  Y ||
refund_fee|退票费 |string | Y ||
reason |退票原因| double |  Y ||
endorse_info|改签信息| boolean|  Y ||
supplementary_payment || integer |  Y |  1:是,0:否
diff_price|| boolean| Y ||
endorse_fee |改签手续费| integer | Y | 1:是,0:否
reason|是否可以查看订单详情| boolean| Y ||
ticket_tips |票状态说明| integer | Y | 1:是,0:否
insurance_info|保险信息 |string | Y ||
can_process |是否可查看企业订单| double |  Y ||
cost_attribution|费用归属| boolean|  Y ||
contact_info |联系人信息| integer |  Y |  1:是,0:否
contact_name|联系人姓名| boolean| Y ||
contact_phone |联系人手机号| integer | Y | 1:是,0:否
refund_price_info|退票信息| jsonobject| Y ||
refund_price |退订金额（票价单价)| integer | Y | 1:是,0:否
refund_cost |退票手续费| integer | Y | 1:是,0:否
refund_total_price|退票总价 |string | Y ||
endorse_price_info |改签信息| jsonobject |  Y ||
endorse_price|改签差价（差价）| boolean|  Y ||
endorse\_cost |改签手续费| integer |  Y | 
endorse\_total\_price|改签总价| boolean| Y ||
price\_detail |价格信息| jsonobject | N | 
key|费用明细key| string| Y ||
price |费用明细金额| integer | Y| 
amount\_desc |费用明细金额|integer|Y|  
dc| 正负|string |Y||，如票价是正（1）、优惠券是负（-1）
grab\_info|抢票信息|jsonobject|N||



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














