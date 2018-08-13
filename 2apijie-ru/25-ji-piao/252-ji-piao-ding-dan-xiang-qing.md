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
        "order_id": "5a30c48a279863762069cf8c",
        "remote_order_id": "lalala",
        "supplier_id": 104,
        "create_time": "2017-12-13 00:00:00",
        "can_process": false,
        "cost_attribution": "嘟嘟搞测试",//按部门费用归属;国开行项目:按项目
        "total_price": 160,
        "passenger_list": [
            {
                "passenger_info": {
                    "id": "59dd8df023445f08c579db7d",
                    "name": "强仔",
                    "type": 0,
                    "identity_type": "1",
                    "identity_type_name": {
                        "key": 1,
                        "value": "身份证"
                    },
                    "identity_no": "230203198512240032",
                    "phone": "18310480640"
                },
                "ticket_no": "987654321",
                "status": {
                    "key": 1823,
                    "value": "改签成功"
                },
                "product_id": "5a30c48a279863762069cf8d",
                "ticket_tips": "",
                "can_endorse": false,
                "can_refund": false,
                "change_info": {
                    "upgrade_price": 60,
                    "upgrade_price_msg": "改期成功",
                    "change_fee": 100,
                    "agency_fee": 80,
                    "change_fee_msg": "改期成功"
                }
            }
        ],
        "status": {
            "key": 1821,
            "value": "改签成功"
        },
        "segment_info": {
            "flight_no": "U12138",
            "starting_code": "PEK",
            "destination_code": "PVG",
            "cabin": "J",
            "starting_city": "北京市",
            "starting_airport": "首都国际机场",
            "starting_terminal": "T1",
            "destination_city": "上海市",
            "destination_airport": "浦东国际机场",
            "destination_terminal": "T6",
            "is_middle_stop": false,
            "departure_date": "2017-12-21 14:10:25",
            "departure_time": "2017-12-21 14:10:25",
            "departure_timestamp": 1513836625000,
            "arrived_time": "2017-12-21 20:10:30",
            "arrived_timestamp": 1513858230000,
            "arrived_date": "2017-12-08",
            "airline_name": "国行",
            "seat_msg": "",
            "plane_type": ""
        },
        "price_info": {
            "par_price": 312,
            "discount": 0,
            "fuel_tax": 4131,
            "airport_tax": 0,
            "settle_price": 3131,
            "sale_price": 3123
        },
        "policy_info": {
            "policy_id": ""
        },
        "stipulate_info": {
            "refund_stipulate": "",
            "modify_stipulate": "",
            "change_stipulate": ""
        },
        "contact_name": "强仔",
        "contact_phone": "18310480640",
        "is_manual": true,
        "order_owner": {
            "user_id": "59dc3c3323445f71ddcf56a8",
            "phone": "18310480640",
            "name": "强仔",
            "idType": {
                "key": 2,
                "value": "护照"
            },
            "idNumber": "89387437283",
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
        "remark_reason": null,
        "remark_detail": null,
        "comment": "如需退票或改签请联系客服",
        "insurance_info": [],
        "check_info": [],
        "is_external_order": 1,
        "employee_remark": "",
        "price_detail": null,
        "total_price_str": "￥160.00",
        "manual_remark": "无",
        "custom_remark": [],
        "has_endorse": false,
        "refund_price_info": null,
        "endorse_price_info": {
            "endorse_price": 60,
            "endorse_cost": 100,
            "endorse_total_price": 160
        },
        "exceeded": false
    }
}


```
