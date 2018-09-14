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
apply_id |审批单ID| string | N|17948763419761f9209db83
excced_info|超标信息 |jsonobject|N|超标信息
excced_info.reason|超标理由 |string|N|超标理由
excced_info|超标理由备注 |string|N|超标理由备注
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



```
{
    "request_id": "sX9e4zRTBpY5emyUcwqO",
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "5b9b59bae4b0ffb767208b44",
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
		"order_total_price": 4685.00

    }
}







```
