根据订单id查询机票详情

请求方式|请求地址
----|---
POST|/open/api/flight/order/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| |string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.order_id |机票订单id|String|Y|

请求示例：

```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"timestamp":124124325,
	"sign":"oihfnlyeofdh98",
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"523234c1323445f2d54dd0"
	}
}

```


返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
total_price |订单金额| Inreger|Y| 453
status. key |订单状态	| string | Y |1900:有退改签
order_id |订单号	| string | Y|59b5fe4a2798631761f29db8
order_owner.name |预定人| string|Y| "name": "辛植"
create_time|订单创建时间|string|Y|2017-09-11 11:08:58
ticket_no |票号| string | Y | 784-2310286513
cost_attribution |费用归属| string|Y|例：研发部
airline_name |航空公司| string|Y|例：吉祥航空
flight_no |航班号	|string| Y |HO1252
passenger_info .name |乘机人姓名| string |Y| name:"辛植"
identity\_type_name.key |证件类型|string|Y|0.未知 1:身份证  2.护照 3.回乡证 4.台胞证
phone |乘机人手机号| string|Y|16676823457
identity_no |乘机人证件号| string | Y |数字，英文字母
status.key |机票状态| string|Y| 1811:退票成功 
refund_amount |退款金额| Integer |Y|  1600
refund_fee |手续费| Integer | Y |100
seat_msg |舱位| string |Y|头等舱/商务舱
starting_city |出发城市| string | Y |北京
starting_airport |出发机场| string|Y|中英文  首都国际机场
starting_code |出发航程三字码| string | Y |PEK
starting_terminal |起飞航站楼| string |Y|首都T3
departure_timestamp |起飞时间| string | Y|1507079400000
destination_city|到达城市| string|Y| 上海destination_airport |到达机场| string|Y|虹桥国际机场
destination_code|到达航程三字码|string|Y|SHA
destination_terminal |到达航站楼| string |Y|T4
arrived_timestamp |到达时间|Integer | Y | 1537099400000
par_price|机票单价| Integer |Y|3370
airport_tax |机建| Integer | Y |50
fuel_tax |燃油| Integer| Y |44
coupon_amount|订单优惠券	| Integer |Y|例：20
category_code|险种| string|Y| 1:航意险，2：航延险
policy_number |保单编号| string|Y|10450061900247380997
status.key |保单状态| Integer |Y|8:退保成功
insurant_name |被保人| string |Y|张胜男
insurant_amount |数量| Integer | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
unit_price|保费| Integer |Y|
type |乘客类型| Integer |Y|0:成人,1:婴儿


```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": {
    		"order_id": "576b917bdec24c7c091d2f72",			"remote_order_id": "102016062360137545",    		"create_time": 1466667402270,   			"can_process": false,   			"cost_attribution":  "",    		"total_price": 7540,    		“apply_id”:”23423sdrefds”,//审批单ID    		“exceeded”:false, //是否已超标    		“exceed_info” :{				“reason”:”就是要超”,     //超标理由				“comment”:”超标补充说明”    		},   			"check_info":[			{				"title":"未选择最低价格理由",				"reason":"陪客户出行",				"comment":"额外补充"			},			{				"title":"未提前3天预订机票",				"reason":"陪领导出差",				"comment":"额外补充"			},  		],    	"passenger_list": [      {        "passenger_info": {          "identity_type": "1",          "identity_no": "410183198603180012",          "name": "王超",          "type": 0        },        "ticket_no": "xxxxxxxxx",        "status": {     //机票状态				"key":1800,				"value":"出票成功"					},        "product_id": "5774c54f7a3170af796ba290",        "refund_info": {          "refund_amount": 700,          "refund_amount_msg": "退票处理中",          "refund_fee": 300,          "refund_fee_msg": "退票处理中"        },        "change_info": {          "upgrade_price": 300,          "upgrade_price_msg": "改签处理中",          "change_fee": 200,//改签费          "agency_fee": 10,//改签手续费          "change_fee_msg": "改签处理中"        }      }    ],   "status": {     //订单状态		"key":1800,"value":"出票成功"},    "segment_info": {      "starting_terminal": "T3",      "cabin": "F",      "plane_type": "787",      "arrived_time": "0940",      "destination_terminal": "T2",      "destination_code": "SHA",      "seat_msg": "头等舱",      "starting_code": "PEK",      "departure_time": "0730",      "is_middle_stop": "false",      "flight_no": "CA1831",      "departure_date": "2016-10-20",      "departure_timestamp": 1476919800000,      "arrived_timestamp": 1476927600000,      "starting_city": "北京",      "starting_airport": "首都国际机场",      "destination_city": "上海",      "destination_airport": "虹桥国际机场",      "airline_name": "中国国际航空",      "code_share": false,      "share_airline_name": "",      "share_num": ""    },    "price_info": {      "settle_price": 329.8,      "discount": 3,      "par_price": 3720,      "fuel_tax": 0,      "airport_tax": 50,      "coupon_amount": 20    },    "policy_info": {      "policy_id": "111402007"    },    "stipulate_info": {      "cabin": "F",      "par_price": 3720,      "modify_stipulate": "可以改签;",      "comment": "",      "refund_stipulate": "取消座位时间计算手续费;按照当前舱位票面价收取退票费;起飞前免收退票费,起飞后收取当前舱位票面价的10.0%退票费;",      "change_stipulate": "按照当前舱位票面价收取变更费;起飞前免收改期费,起飞后收取当前舱位票面价的5.0%改期费;"    },    "contact_name": "王超",    "contact_phone": "18610297769",    "order_owner": {      "id": "57613c435eac323d0c174216",      "name": "汪识瀚",      "phoneNum": "13717505875",      "loginInfo": {        "providerID": "credentials",        "providerKey": "13717505875"      },      "role": {        "key": 3,        "value": "普通员工"      },      "status": {        "key": 1,        "value": "启用"      }    },    "remark_reson": "remark_reson",    "remark_detail": "remark_detail",    "comment": "",    "insurance_info": [         //保险字段      {        "category_code": 1,        "category_name": "航意险",        "desc": "最高保额10000元，让关心你的人更放心",        "desc_link": "平安航延险说明链接",        "unit_price": 30,        "insurant_list": [          {            "premium": 30,            "insurant_name": "李四",            "status": {              "key": 5101,              "value": "已投保"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {              "url": "http://15607.corp.51zxtx.com/177474/				polices/{policyNumber}",              "headers": [                {                  "name": "Content-Type",                  "value": "application/pdf"                },                {                  "name": "X-Zxtx-Sign",                  "value": 					"5A492D6F67169DDA7F83611FCAD5B30C"                }              ]            }          },          {            "premium": 30,            "insurant_name": "张三",            "status": {              "key": 5101,              "value": "投保中"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {    }          }        ]      },      {        "category_code": 2,        "category_name": "航延险",        "unit_price": 30,        "desc": "最高保额10000元，让关心你的人更放心",        "desc_link": "平安航延险说明链接",        "insurant_list": [          {            "premium": 30,            "insurant_name": "李四",            "status": {              "key": 5101,              "value": "投保中"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {}          }        ]      }    ]   
        }
}
```
