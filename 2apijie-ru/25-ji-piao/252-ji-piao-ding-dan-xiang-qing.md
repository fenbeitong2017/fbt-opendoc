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
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.order_id |机票订单id|string|Y|

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
employee_remark|用户备注| string |Y|



```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": {
    "order_id": "5ab368b127986333d6839cfc",
		"remote_order_id": "124018274918279242",
		"create_time": "2018-03-22 16:26:29",
		"can_process": false,
		"cost_attribution": "嘟嘟搞测试",
		"total_price": 56,
		"passenger_list": [{
			"passenger_info": {
				"id": "5aab2d3423445f6ebb39d88e",
				"name": "韩美美",
				"type": 0,
				"identity_type": "1",
				"identity_type_name": {
					"key": 1,
					"value": "身份证"
				},
				"identity_no": "230203198512240032",
				"phone": "18310480640"
			},
			"ticket_no": "99999999998387374",
			"status": {
				"key": 1811,
				"value": "退票成功"
			},
			"product_id": "5ab368b527986333d6839d00",
			"ticket_tips": "退票成功",
			"refund_info": {
				"refund_amount": 56,
				"refund_amount_msg": "退票处理中",
				"refund_fee": 20,
				"refund_fee_msg": "退票处理中"
			}
		}],
		"status": {
			"key": 1900,
			"value": "有退改签"
		},
		"segment_info": {
			"arrived_time": "0910",
			"arrived_timestamp": 1523495400000,
			"cabin": "F",
			"departure_date": "2018-04-12",
			"departure_time": "0650",
			"departure_timestamp": 1523487000000,
			"destination_code": "SHA",
			"destination_terminal": "T2",
			"flight_no": "HO1252",
			"is_middle_stop": false,
			"plane_type": "",
			"seat_msg": "头等舱/商务舱",
			"starting_code": "PEK",
			"starting_terminal": "T3",
			"starting_city": "北京",
			"starting_airport": "首都国际机场",
			"destination_city": "上海",
			"destination_airport": "虹桥国际机场",
			"airline_name": "吉祥航空",
			"code_share": 0,
			"share_airline_name": "",
			"share_num": "",
			"is_official": false
		},
		"price_info": {
			"add_price": 0,
			"airport_tax": 50,
			"discount": 2.76,
			"fuel_tax": 0,
			"par_price": 1,
			"price": 0,
			"sale_price": 1,
			"settle_price": 1,
			"coupon_amount": 0
		},
		"policy_info": {
			"policy_id": "HS"
		},
		"stipulate_info": {
			"cabin": "F",
			"change_stipulate": "改期：起飞前2小时前，收取费用： 0%\n起飞前2小时后，收取费用： 5%\n升舱：不允许\n此规定仅供参考，最终以航空公司规定为准",
			"comment": "以航空公司规定为准",
			"modify_stipulate": "不允许\n此规定仅供参考，最终以航空公司规定为准",
			"par_price": 3420,
			"refund_stipulate": "起飞前2小时前，收取费用： 0%\n起飞前2小时后，收取费用： 5%\n此规定仅供参考，最终以航空公司规定为准",
			"stipulate_name": "退改签规则"
		},
		"contact_name": "强仔",
		"contact_phone": "18310480640",
		"is_manual": true,
		"order_owner": {
			"user_id": "59dc3c3323445f71ddcf56a8",
			"phone": "18310480640",
			"name": "强仔",
			"idType": {
				"key": 1,
				"value": "身份证"
			},
			"idNumber": "230203198512240032",
			"avatar_url": "",
			"role": {
				"key": 2,
				"value": "普通管理员"
			},
			"status": {
				"key": 1,
				"value": "启用"
			},
			"email": "",
			"fixed_phone": ""
		},
		"remark_reason": "开发市场",
		"remark_detail": null,
		"comment": "",
		"insurance_info": [],
		"check_info": [],
		"is_external_order": 0,
		"employee_remark": null,
		"price_detail": [{
			"key": "票价",
			"price": "1.00",
			"amount_desc": "1人",
			"dc": 1
		}, {
			"key": "机建",
			"price": "50.00",
			"amount_desc": "1人",
			"dc": 1
		}],
		"total_price_str": "￥56.00",
		"refund_price_info": null,
		"endorse_price_info": null,
		"exceeded": false  
        }
}
```
