2.5.2 机票订单详情

####接口说明
- 1.**最新接口**
- 2.查询机票订单详情接口
  通过该接口可以查询企业使用分贝通APP下的机票订单详情信息



请求方式|请求地址
----|---
POST|/open/api/flight/order/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data||jsonobject|Y|请求数据
data.order_id |机票订单id|string|Y|523234c1323445f2d54dd0

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
-----|-----|----|----|----
total_price |订单金额| double|Y| 453
status|订单状态	| jsonobject | Y |订单状态
status.key |订单状态码	| integer | Y |1900(详情参照状态码)
status.value |订单状态名称| string | Y |有退改签
order_id |订单号	| string | Y|59b5fe4a2798631761f29db8
pre_order_id |原单号| string | N|59b5fe4a2798631761f29d098
apply_id |审批单ID| string | N|17948763419761f9209db83
excced_info|超标信息 |jsonobject|N|超标信息
excced_info.reason|超标理由 |string|N|超标理由
excced_info.comment|超标理由备注 |string|N|超标理由备注
order_owner|预定人信息| jsonobject|Y|预订人信息
order_owner.name |预定人姓名| string|Y| "name": "辛植"
order_owner.user_id |用户ID| string|Y| 59dc3c3323445f71ddcf56a8
order_owner.phone |预定人手机号| string|Y| 18310480640
order_owner.idType |身份类型| jsonobject|Y| 
idType.key |类型ID| integer|Y| 0.未知 1:身份证  2.护照 3.回乡证 4.台胞
idType.value |身份类型名称| string|Y| 身份证
order_owner.idNumber |身份证件号码| string|Y| 230203198512240032
create_time|订单创建时间|string|Y|2017-09-11 11:08:58
cost_attribution |费用归属| string|Y|例：研发部
passenger_list |乘机人信息数组| jsonoarray |Y| 
passenger_list.passenger_info |乘机人信息| jsonobject |Y|乘机人信息 
passenger_list.ticket_no |票号| string | Y | 784-2310286513
passenger_list.status|订单状态信息| jsonobject |Y|订单状态信息 
status.key|状态码| integer |Y| 订单状态码，详情参见状态码
status.value|状态码信息| string |Y|状态码信息 
passenger_info.name |乘机人姓名| string |Y| 强仔
passenger_info.id |乘机人姓名| string |Y| 59dd8df023445f08c579db7d
passenger_info.type |乘机人类型| integer |Y| 0  0:成人,1:婴儿
passenger_info.identity_type |身份类型| string  |Y|1 
passenger_info.identity_type_name |乘机人证件信息| jsonobject |Y| 乘机人证件信息
identity_type_name.key |乘机人证件类型ID| integer |Y| 1
identity_type_name.value |乘机人证件类型名称| string |Y| 身份证
passenger_info.identity_no |乘机人身份证号| string |Y| 230203198512240032
passenger_info.phone |乘机人手机号| string |Y| 18310480640
price_info.par_price|机票单价| integer |Y|3370
price_info.airport_tax |机建| integer | Y |50
price_info.fuel_tax |燃油| integer| Y |44 
price_info.coupon_amount|订单优惠券| integer |Y|例：20
refund_amount |退款金额| integer |Y|  1600
refund_fee |手续费| integer | Y |100
segment_info.seat_msg |舱位| string |Y|头等舱/商务舱
segment_info.starting_city |出发城市| string | Y |北京
segment_info.starting_airport |出发机场| string|Y|中英文  首都国际机场
segment_info.starting_code |出发航程三字码| string | Y |PEK
segment_info.starting_terminal |起飞航站楼| string |Y|首都T3
segment_info.departure_timestamp |起飞时间| integer | Y|1507079400000
segment_info.destination_city|到达城市| string|Y| 上海
segment_info.destination_airport |到达机场| string|Y|虹桥国际机场
segment_info.destination_code|到达航程三字码|string|Y|SHA
segment_info.destination_terminal |到达航站楼| string |Y|T4
segment_info.arrived_timestamp |到达时间|integer | Y | 1537099400000
segment_info.airline_name |航空公司| string|Y|例：吉祥航空
segment_info.flight_no |航班号	|string| Y |HO1252
segment_info.cabin |仓位|string| Y |F
segment_info.departure_date |出发日期|string| Y |2018-03-27(年月日)
segment_info.departure_time |出发时间|string| Y |1812(时分)
segment_info.arrived_date |到达日期|string| Y |2018-03-27(年月日)
segment_info.arrived_time |到达时间|string| Y |2312(时分)
insurance_info.category_code|险种| string|Y| 1:航意险，2：航延险
insurance_info.unit_price|保费| integer |Y|
insurant_list.policy_number |保单编号| string|Y|10450061900247380997
status.key |保单状态| integer |Y|8:退保成功.详细请参照保险状态码
insurant_list.insurant_name |被保人| string |Y|张胜男
insurant_amount |数量| integer | N |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
employee_remark|用户备注| string |Y|出差使用
endorse_price|改签差价| double |Y|10
endorse_cost|改签费| double |Y|30
endorse_total_price|改签总价| double |Y|40














```
{
    "request_id": "sX9e4zRTBpY5emyUcwqO",
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "5b9b59bae4b0ffb767208b44",
        "pre_order_id": "5ab8b626279863224fef078e",   // 关联订单ID
        "apply_id": "5b61757323445f071a732860",
		"remote_order_id": "",
		"supplier_id": 110,
		"create_time": "2018-09-14 14:48:30",
		"over_time": "15:03",
		"can_process": true,
		"cost_attribution": "X部门",
		"total_price": 4685.00,
		"passenger_list": [{
			"passenger_info": {
				"id": "59c3803423445f653d812a1c",
				"name": "韩冰",
				"type": 0,
				"phone": "170****1667",
				"gender": {
					"key": 1,
					"value": "男"
				},
				"identity_type": "2",
				"identity_type_name": {
					"key": 2,
					"value": "护照"
				},
				"identity_no": "782********62",
				"org_unit": "X部门",
				"org_unit_id": "58c21a365f281a7e6f810ae6",
				"company_id": "5747fbc10f0e60e0709d8d7d",
				"company_name": "北京分贝金服科技有限公司",
				"full_org_unit": "北京分贝金服科技有限公司/X部门",
				"birth_date": "2016-10-20"
			},
			"status": {
				"key": 1100,
				"value": "待支付"
			},
			"product_id": "5b9b59bbe4b0ffb767208b45",
			"ticket_tips": "",
			"can_endorse": false,
			"can_refund": false
		}],
		"status": {
			"key": 1100,
			"value": "待支付"
		},
		"segment_info": {
			"cabin": "A",
			"starting_airport": "首都机场",
			"destination_terminal": "T2",
			"code_share": false,
			"share_num": "",
			"is_official": false,
			"flight_no": "CA1405",
			"plane_type": "",
			"starting_city": "北京市",
			"departure_time": "0740",
			"destination_airport": "双流机场",
			"arrived_time": "1045",
			"share_airline_name": "",
			"arrived_timestamp": 1539744300000,
			"departure_date": "2018-10-17",
			"destination_code": "CTU",
			"seat_msg": "头等舱/商务舱",
			"starting_terminal": "T3",
			"departure_timestamp": 1539733200000,
			"starting_code": "PEK",
			"airline_name": "中国国航",
			"destination_city": "成都市"
		},
		"price_info": {
			"discount": 2.5,
			"price": 0,
			"add_price": 50,
			"airport_tax": 50,
			"fuel_tax": 10,
			"par_price": 4630,
			"sale_price": 4630,
			"settle_price": 4619,
			"coupon_amount": 5
		},
		"policy_info": {
			"policy_id": "QW_BB"
		},
		"stipulate_info": {
			"cabin": "A",
			"comment": "以航空公司规定为准",
			"refund_stipulate": "起飞前，收取费用： 10%\n起飞后，收取费用： 20%\n*此规定仅供参考，最终以航空公司规定为准",
			"modify_stipulate": "不允许\n*此规定仅供参考，最终以航空公司规定为准",
			"change_stipulate": "改期：起飞前，收取费用： 5%\n起飞后，收取费用： 10%\n升舱：不允许\n*此规定仅供参考，最终以航空公司规定为准",
			"par_price": 4630,
			"stipulate_name": "退改签规则"
		},
		"contact_name": "韩冰",
		"contact_phone": "170****1667",
		"is_manual": false,
		"order_owner": {
			"user_id": "59bf74f423445f31bd64bc5c",
			"name": "韩冰",
			"phone": "17080151667",
			"email": ""
		},
		"remark_reason": "学习培训",
		"comment": "请在15:03前完成支付，超时订单将关闭",
		"check_info": [],
		"is_external_order": 0,
		"price_detail": [{
			"key": "票价",
			"price": 4630.00,
			"amount_desc": "1人",
			"dc": 1
		}, {
			"key": "机建",
			"price": 50.00,
			"amount_desc": "1人",
			"dc": 1
		}, {
			"key": "燃油",
			"price": 10.00,
			"amount_desc": "1人",
			"dc": 1
		}, {
			"key": "优惠券",
			"price": 5.00,
			"amount_desc": "",
			"dc": -1
		}],
		"total_price_str": "¥4685.00",
		"manual_remark": "无",
		"custom_remark": [],
		"has_endorse": false,
		"excced_info": {
			"reason": "舱位没票了",
			"comment": "仓位没票"
		},
		"trip_type": 0,
		"order_type": 1,
		"endorse_price_info": {
			"endorse_price": 10,//改签差价
			"endorse_cost": 101,改签费
			"endorse_total_price": 111
		},
		"order_total_price": 4685.00

    }
}

```



```
退票成功数据结构:

{
    "request_id": "LYWoaylhD1AXfNuADWOe",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "order_id": "5bc2836ae4b0a94c804f4e42",
        "pre_order_id": "5bc07049e4b0087ca188f84e",
        "remote_order_id": "112018101287795441",
        "supplier_id": 101,
        "create_time": "2018-10-14 07:44:42",
        "over_time": "07:59",
        "can_process": false,
        "cost_attribution": "嘟嘟搞测试",
        "total_price": -950,
        "passenger_list": [
            {
                "passenger_info": {
                    "id": "5a09690923445f11ade39f7d",
                    "name": "强Zai",
                    "type": 0,
                    "phone": "183****0640",
                    "gender": {
                        "key": 1,
                        "value": "男"
                    },
                    "identity_type": "2",
                    "identity_type_name": {
                        "key": 2,
                        "value": "护照"
                    },
                    "identity_no": "289**qs",
                    "org_unit": "嘟嘟搞测试",
                    "org_unit_id": "59a80dd92798630fd780babf",
                    "company_id": "5747fbc10f0e60e0709d8d7d",
                    "company_name": "北京分贝金服科技有限公司",
                    "full_org_unit": "北京分贝金服科技有限公司/嘟嘟搞测试",
                    "birth_date": "2010-10-13"
                },
                "ticket_no": "8762829733063",
                "status": {
                    "key": 1811,
                    "value": "退票成功"
                },
                "product_id": "5bc2836ae4b0a94c804f4e43",
                "ticket_tips": "",
                "can_endorse": false,
                "can_refund": false,
                "refund_info": {
                    "refund_amount": 998,
                    "refund_amount_msg": "退票处理中",
                    "refund_fee": 48,
                    "refund_fee_msg": "退票处理中"
                }
            }
        ],
        "status": {
            "key": 1811,
            "value": "退票成功"
        },
        "segment_info": {
            "cabin": "Y",
            "middle_stop": false,
            "starting_airport": "咸阳机场",
            "destination_terminal": "T1",
            "code_share": false,
            "share_num": "",
            "is_official": false,
            "flight_no": "3U8379",
            "plane_type": "321",
            "starting_city": "西安市",
            "departure_time": "0615",
            "destination_airport": "双流机场",
            "arrived_time": "0755",
            "share_airline_name": "",
            "arrived_timestamp": 1541634900000,
            "departure_date": "2018-11-08",
            "destination_code": "CTU",
            "seat_msg": "经济舱",
            "starting_terminal": "T3",
            "departure_timestamp": 1541628900000,
            "starting_code": "XIY",
            "is_middle_stop": false,
            "stop_info": "",
            "airline_name": "四川航空",
            "destination_city": "成都市"
        },
        "price_info": {
            "discount": 0.98,
            "add_price": 0,
            "airport_tax": 50,
            "fuel_tax": 20,
            "par_price": 950,
            "sale_price": 928,
            "settle_price": 928
        },
        "policy_info": {
            "policy_id": "229099290"
        },
        "stipulate_info": {
            "cabin": "Y",
            "comment": "以航空公司规定为准",
            "refund_stipulate": "取消座位时间计算手续费；按照当前舱位票面价收取退票费；起飞前2.0小时（含）以外收取当前舱位票面价的5.0%退票费,起飞前2.0小时以内及起飞后收取当前舱位票面价的10.0%退票费；\n*此规定仅供参考，最终以航空公司规定为准",
            "modify_stipulate": "不能签转；\n*此规定仅供参考，最终以航空公司规定为准",
            "change_stipulate": "按照当前舱位票面价收取变更费；起飞前2.0小时（含）以外免收改期费,起飞前2.0小时以内及起飞后收取当前舱位票面价的5.0%改期费；\n*此规定仅供参考，最终以航空公司规定为准",
            "par_price": 950,
            "stipulate_name": "退改费低"
        },
        "contact_name": "强仔",
        "contact_phone": "183****0640",
        "is_manual": false,
        "order_owner": {
            "user_id": "59dc3c3323445f71ddcf56a8",
            "name": "强Zai",
            "phone": "18310480640"
        },
        "remark_reason": "学习培训",
        "comment": "",
        "check_info": [],
        "is_external_order": 0,
        "price_detail": [
            {
                "key": "票价",
                "price": 928,
                "amount_desc": "1人",
                "dc": 1
            },
            {
                "key": "机建",
                "price": 50,
                "amount_desc": "1人",
                "dc": 1
            },
            {
                "key": "燃油",
                "price": 20,
                "amount_desc": "1人",
                "dc": 1
            }
        ],
        "total_price_str": "-¥950.00",
        "manual_remark": "无",
        "custom_remark": [],
        "has_endorse": false,
        "refund_price_info": {
            "refund_price": 998,
            "refund_total_price": 950,
            "refund_cost": 48
        },
        "excced_info": {},
        "trip_type": 0,
        "order_type": 1,
        "order_total_price": -950
    }
}


```

```
出票成功返回的数据结构:
{
    "request_id": "VLbTpyx6e4ycojRIoteB",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "order_id": "5bbc2a5b2798636cb1e8c6a0",
        "pre_order_id": "5bbc2a5b2798636cb1e8c6a0",
        "remote_order_id": "xc123456",
        "supplier_id": 105,
        "create_time": "2018-10-25 00:00:00",
        "over_time": "00:15",
        "can_process": false,
        "cost_attribution": "北京分贝金服科技有限公司",
        "total_price": 1417,
        "passenger_list": [
            {
                "passenger_info": {
                    "id": "59bf8abe23445f31bd64bc62",
                    "name": "谷健波",
                    "type": 0,
                    "phone": "139****1353",
                    "gender": {
                        "key": 1,
                        "value": "男"
                    },
                    "identity_type": "1",
                    "identity_type_name": {
                        "key": 1,
                        "value": "身份证"
                    },
                    "identity_no": "110101**********19",
                    "birth_date": "1984-12-24"
                },
                "ticket_no": "123456",
                "status": {
                    "key": 1800,
                    "value": "出票成功"
                },
                "product_id": "5bbc2a5c2798636cb1e8c6a1",
                "ticket_tips": "",
                "can_endorse": false,
                "can_refund": false
            }
        ],
        "status": {
            "key": 1800,
            "value": "出票成功"
        },
        "segment_info": {
            "cabin": "G",
            "middle_stop": true,
            "starting_airport": "首都机场",
            "destination_terminal": "T2",
            "flight_no": "CA1589",
            "plane_type": "",
            "starting_city": "北京市",
            "departure_time": "2030",
            "destination_airport": "虹桥机场",
            "arrived_time": "2240",
            "arrived_timestamp": 1540478400000,
            "departure_date": "2018-10-25",
            "destination_code": "SHA",
            "seat_msg": "G",
            "starting_terminal": "T3",
            "departure_timestamp": 1540470600000,
            "starting_code": "PEK",
            "is_middle_stop": true,
            "stop_info": "",
            "airline_name": "中国国航",
            "destination_city": "上海市"
        },
        "price_info": {
            "discount": 0,
            "airport_tax": 50,
            "fuel_tax": 10,
            "par_price": 1417,
            "sale_price": 1357,
            "settle_price": 1350,
            "insurance_price": 0,
            "insurance_cost": 0
        },
        "policy_info": {
            "policy_id": ""
        },
        "stipulate_info": {
            "cabin": "G",
            "comment": "以航空公司规定为准",
            "return_change_condition": "此规定仅供参考，最终以航空公司规定为准",
            "par_price": 1417
        },
        "contact_name": "谷健波",
        "contact_phone": "139****1353",
        "is_manual": true,
        "order_owner": {
            "user_id": "59b8acf023445f70c3eaef80",
            "name": "谷健波",
            "phone": "13911381353"
        },
        "comment": "",
        "check_info": [],
        "is_external_order": 1,
        "total_price_str": "¥1417.00",
        "manual_remark": "无",
        "custom_remark": [],
        "has_endorse": false,
        "apply_id": "",
        "excced_info": {},
        "trip_type": 0,
        "order_type": 1,
        "order_total_price": 1417
    }
}

```



```
改签成功返回的数据结构:

{
    "request_id": "4orFjqF11oNPMwmPJiM7",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "order_id": "5bbd72352798637dc8f413ba",
        "pre_order_id": "5bbd6d64e4b0ce69ca6eb5b9",
        "remote_order_id": "测试2123124",
        "supplier_id": 105,
        "create_time": "2018-10-10 11:29:57",
        "over_time": "11:44",
        "can_process": false,
        "cost_attribution": "嘟嘟搞测试",
        "total_price": 15,
        "passenger_list": [
            {
                "passenger_info": {
                    "id": "5b598c2223445f0e4391d6c0",
                    "name": "强仔QS",
                    "type": 0,
                    "phone": "123****8923",
                    "gender": {
                        "key": 1,
                        "value": "男"
                    },
                    "identity_type": "4",
                    "identity_type_name": {
                        "key": 4,
                        "value": "台胞证"
                    },
                    "identity_no": "243***76",
                    "org_unit": "嘟嘟搞测试",
                    "org_unit_id": "59a80dd92798630fd780babf",
                    "company_id": "5747fbc10f0e60e0709d8d7d",
                    "company_name": "北京分贝金服科技有限公司",
                    "full_org_unit": "北京分贝金服科技有限公司/嘟嘟搞测试",
                    "birth_date": "1916-07-26"
                },
                "ticket_no": "223523",
                "status": {
                    "key": 1823,
                    "value": "改签成功"
                },
                "product_id": "5bbd72352798637dc8f413bb",
                "ticket_tips": "",
                "can_endorse": false,
                "can_refund": false,
                "change_info": {
                    "upgrade_price": 5,
                    "upgrade_price_msg": "改期成功",
                    "change_fee": 4,
                    "agency_fee": 6,
                    "change_fee_msg": "改期成功"
                }
            }
        ],
        "status": {
            "key": 1821,
            "value": "改签成功"
        },
        "segment_info": {
            "cabin": "Z",
            "middle_stop": false,
            "starting_airport": "首都机场",
            "destination_terminal": "T2",
            "code_share": false,
            "share_num": "",
            "is_official": false,
            "flight_no": "CZ3288",
            "plane_type": "73N",
            "starting_city": "北京市",
            "departure_time": "2018-11-09 21:05:00",
            "destination_airport": "两江机场",
            "arrived_time": "2018-11-10 00:30:00",
            "share_airline_name": "",
            "arrived_timestamp": 1541781000000,
            "departure_date": "2018-11-09 21:05:00",
            "destination_code": "KWL",
            "seat_msg": "特价舱位",
            "starting_terminal": "T2",
            "departure_timestamp": 1541768700000,
            "starting_code": "PEK",
            "is_middle_stop": false,
            "stop_info": "",
            "airline_name": "南方航空",
            "destination_city": "桂林市"
        },
        "price_info": {
            "discount": 1,
            "price": 0,
            "add_price": 0,
            "airport_tax": 50,
            "fuel_tax": 30,
            "par_price": 988,
            "sale_price": 900,
            "settle_price": 888,
            "coupon_amount": 1
        },
        "policy_info": {
            "policy_id": "229058079"
        },
        "stipulate_info": {
            "cabin": "Z",
            "comment": "以航空公司规定为准",
            "return_change_condition": "退票：根据航空公司规定执行  退票3\n改签：根据航空公司规定执行 改签 3\n签转：签转 3\n\n此规定仅供参考，最终以航空公司规定为准",
            "par_price": 988
        },
        "contact_name": "强仔",
        "contact_phone": "183****0640",
        "is_manual": true,
        "order_owner": {
            "user_id": "59dc3c3323445f71ddcf56a8",
            "name": "强Zai",
            "phone": "18310480640"
        },
        "comment": "如需退票或改签请联系客服",
        "check_info": [],
        "is_external_order": 1,
        "total_price_str": "¥15.00",
        "manual_remark": "无",
        "custom_remark": [],
        "has_endorse": false,
        "endorse_price_info": {
            "endorse_price": 5,
            "endorse_cost": 10,
            "endorse_total_price": 15
        },
        "excced_info": {},
        "trip_type": 0,
        "order_type": 1,
        "order_total_price": 15
    }
}

```



