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
----|---|---|---|---
total_price |订单金额| double|Y| 453
status |订单状态	| jsonobject | Y |
status. key |订单状态	| integer | Y |1900:有退改签
status. value |订单状态名称	| string | Y |1900:有退改签
order_id |订单号	| string | Y|59b5fe4a2798631761f29db8
order_owner  |预定人信息| jsonobject|Y| 
order_owner.name |预定人姓名| string|Y| "name": "辛植"
order_owner.user_id |用户ID| string|Y| 59dc3c3323445f71ddcf56a8
order_owner.phone |预定人手机号| string|Y| 18310480640
order_owner.idType |身份类型| jsonobject|Y| 
order_owner.idType.key |类型ID| integer|Y| 0.未知 1:身份证  2.护照 3.回乡证 4.台胞
order_owner.idType.value |身份类型名称| string|Y| 身份证
order_owner.idNumber |身份证件号码| string|Y| 230203198512240032
create_time|订单创建时间|string|Y|2017-09-11 11:08:58
cost_attribution |费用归属| string|Y|例：研发部
passenger_list |乘机人信息数组| jsonoarray |Y| 
passenger_list.passenger_info |乘机人信息| jsonobject |Y| 
passenger_list.ticket_no |票号| string | Y | 784-2310286513
passenger_list.status|乘机人信息| jsonobject |Y| 
passenger_list.status.key|状态码| integer |Y| 详情参见状态码
passenger_list.status.value|状态码信息| String |Y|详情参见状态码 
passenger_list.passenger_info.name |乘机人姓名| String |Y| 强仔
passenger_list.passenger_info.id |乘机人姓名| String |Y| 59dd8df023445f08c579db7d
passenger_list.passenger_info.type |乘机人类型| integer |Y| 0  0:成人,1:婴儿
passenger_list.passenger_info.identity_type |身份类型| string  |Y|1 
passenger_list.passenger_info.identity\_type_name |乘机人信息| jsonobject |Y| 
passenger_list.passenger_info.identity\_type_name.key |乘机人证件类型ID| integer |Y| 
passenger_list.passenger_info.identity\_type_name.value |乘机人证件类型名称| string |Y| 身份证
passenger_list.passenger_info.identity_no |乘机人身份证号| String |Y| 230203198512240032
passenger_list.passenger_info.phone |乘机人手机号| String |Y| 18310480640
price_info.par_price|机票单价| Integer |Y|3370
price_info.airport_tax |机建| Integer | Y |50
price_info.fuel_tax |燃油| Integer| Y |44 
price_info.coupon_amount|订单优惠券| Integer |Y|例：20
refund_amount |退款金额| Integer |Y|  1600
refund_fee |手续费| Integer | Y |100
segment_info.seat_msg |舱位| string |Y|头等舱/商务舱
segment_info.starting_city |出发城市| string | Y |北京
segment_info.starting_airport |出发机场| string|Y|中英文  首都国际机场
segment_info.starting_code |出发航程三字码| string | Y |PEK
segment_info.starting_terminal |起飞航站楼| string |Y|首都T3
segment_info.departure_timestamp |起飞时间| Integer | Y|1507079400000
segment_info.destination_city|到达城市| string|Y| 上海
segment_info.destination_airport |到达机场| string|Y|虹桥国际机场
segment_info.destination_code|到达航程三字码|string|Y|SHA
segment_info.destination_terminal |到达航站楼| string |Y|T4
segment_info.arrived_timestamp |到达时间|Integer | Y | 1537099400000
segment_info.airline_name |航空公司| string|Y|例：吉祥航空
segment_info.flight_no |航班号	|string| Y |HO1252
segment_info.cabin |仓位|string| Y |F
segment_info.departure_date |出发日期|string| Y |2018-03-27
segment_info.departure_time |出发时间|string| Y |2012
segment_info.arrived_date |到达日期|string| Y |2018-03-27
segment_info.arrived_time |到达时间|string| Y |2312
insurance_info.category_code|险种| string|Y| 1:航意险，2：航延险
insurance_info.unit_price|保费| Integer |Y|
insurant_list.policy_number |保单编号| string|Y|10450061900247380997
insurant_list.status.key |保单状态| Integer |Y|8:退保成功
insurant_list.insurant_name |被保人| string |Y|张胜男
insurant_amount |数量| Integer | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
employee_remark|用户备注| string |Y||



```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": {
   "order_id": "576b917bdec24c7c091d2f72",
        "remote_order_id": "102016062360137545",
        "create_time": 1466667402270,
        "can_process[1] ": false,
        "cost_attribution[2] ": "",
        "total_price": 7540,
        "apply_id": ”23423sdrefds”,//审批单ID
"exceeded": false,//是否已超标"
exceed_info": {
            "reason": "就是要超",//超标理
"comment": "超标补充说明"
        },
        "check_info": [
            {
                "title": "未选择最低价格理由",
                "reason": "陪客户出行",
                "comment": "额外补充"
            },
            {
                "title": "未提前3天预订机票",
                "reason": "陪领导出差",
                "comment": "额外补充"
            },
             
        ],
        [
            3
        ]"passenger_list": [
            {
                "passenger_info": {//乘客信息
                    "identity_type": "1",//身份类型
                    "identity_no": "410183198603180012",
                    "name": "王超",
                    "type": 0//乘客类型，0:成年,1:儿童
                },
                "ticket_no": "xxxxxxxxx",
                "status": {//机票状态，详细信息参照机票状态码
"key": 1800,
                    "value": "出票成功"
                },
                "product_id": "5774c54f7a3170af796ba290",
                "refund_info": {//退票信息
                    "refund_amount": 700,//退票金额
                    "refund_amount_msg": "退票处理中",
                    "refund_fee": 300,//退票手续费
                    "refund_fee_msg": "退票处理中"
                },
                "change_info": {
                    "upgrade_price": 300,//升舱费
                    "upgrade_price_msg": "改签处理中",
                    "change_fee": 200,//改签费
                    [
                        4
                    ]"agency_fee": 10,//改签手续费"change_fee_msg": "改签处理中"
                },
                "ticket_tips": "" // 票状态说明
            }
        ],
        "status": {
            //订单状态"key": 1800,
            "value": "出票成功"
        },
        "segment_info": {
            "starting_terminal": "T3",
            "cabin": "F",
            "plane_type": "787",
            "arrived_time": "0940",
            "destination_terminal": "T2",
            "destination_code": "SHA",
            "seat_msg": "头等舱",
            "starting_code": "PEK",
            "departure_time": "0730",
            "is_middle_stop": "false",//是否经停
            "flight_no": "CA1831",
            "departure_date": "2016-10-20",
            "departure_timestamp": 1476919800000,
            "arrived_timestamp": 1476927600000,
            "starting_city": "北京",
            "starting_airport": "首都国际机场",
            "destination_city": "上海",
            "destination_airport": "虹桥国际机场",
            "airline_name": "中国国际航空",
            "code_share": false,
            "share_airline_name": "",
            "share_num": ""
        },
        "price_info": {
            "settle_price": 329.8,
            "discount": 3,//优惠券
            "par_price": 3720,//票面价
            "fuel_tax": 0,//燃油费
            "airport_tax": 50,//机建费
            "coupon_amount": 20//优惠券
        },
        "policy_info": {
            "policy_id": "111402007"
        },
        "stipulate_info": {
            "cabin": "F",//舱位
            "par_price": 3720,//票面价

            "modify_stipulate": "可以改签;",
            "comment": "",
            "refund_stipulate": "取消座位时间计算手续费;按照当前舱位票面价收取退票费;起飞前免收退票费,起飞后收取当前舱位票面价的10.0%退票费;",//退票规则
            "change_stipulate": "按照当前舱位票面价收取变更费;起飞前免收改期费,起飞后收取当前舱位票面价的5.0%改期费;"//改签规则
        },
        "contact_name": "王超",//联系人
        "contact_phone": "18610297769",//联系人手机号
        "order_owner": {
            "id": "57613c435eac323d0c174216",
            "name": "汪识瀚",
            "phoneNum": "13717505875",
            "loginInfo": {
                "providerID": "credentials",
                "providerKey": "13717505875"
            },
            "role": {//权限信息
                "key": 3,
                "value": "普通员工"
            },
            "status": {//员工状态
                "key": 1,
                "value": "启用"
            }
        },
        "remark_reson": "remark_reson",
        "remark_detail": "remark_detail",
        "comment": "",
        "insurance_info": [
            //保险字段{
                "category_code": 1,//保险类别编码

                "category_name": "航意险",//保险类别名称
                "desc": "最高保额10000元，让关心你的人更放心",
                "desc_link": "平安航延险说明链接",
                "unit_price": 30,//
                "insurant_list": [

                    {
                        "premium": 30,//保险金额
                        "insurant_name": "李四",
                        "status": {//保险状态
                            "key": 5,
                            "value": "投保成功"
                        },
                        "policy_number": "1000191573",
                        "start_date": "2017-03-20",
                        "end_date": "2017-03-21",
                        "insurance_link": {
                            [
                                5
                            ]"url": "http://15607.corp.51zxtx.com/177474/polices/{policyNumber}",
                            "headers": [
                                {
                                    "name": "Content-Type",
                                    "value": "application/pdf"
                                },
                                {
                                    "name": "X-Zxtx-Sign",
                                    "value": "5A492D6F67169DDA7F83611FCAD5B30C"
                                }
                            ]
                        }
                    },
                    {
                        "premium": 30,
                        "insurant_name": "张三",
                        "status": {
                            "key": 5,
                            "value": "投保成功"
                        },
                        "policy_number": "1000191573",
                        "start_date": "2017-03-20",
                        "end_date": "2017-03-21",
                        "insurance_link": {
                             
                        }
                    }
                ]
            },
            {
                "category_code": 2,//保险类型
                "category_name": "航延险",
                "unit_price": 30,
                "desc": "最高保额10000元，让关心你的人更放心",
                "desc_link": "平安航延险说明链接",
                "insurant_list": [
                    {
                        "premium": 30,
                        "insurant_name": "李四",
                        "status": {
                            "key": 5,
                            "value": "投保成功"
                        },
                        "policy_number": "1000191573",
                        "start_date": "2017-03-20",
                        "end_date": "2017-03-21",
                        "insurance_link": {
                             
                        }
                    }
                ]
            }
        ],
        "during_apply_info": {
            "apply": {
                "apply_order_type": 1,
                //1.行程审批单2.事中审批单"exceed_buy_desc": "机票小于7折",
                //超规说明"repulse_desc": "驳回理由",
                //驳回理由"apply_reason": "因公出差",
                "budget": 14,
                "company_id": "5747fbc10f0e60e0709d8d7d",
                "create_time": "2017-03-10 12:43:09",
                //当前时间戳"current_time": "2017-03-10 12:53:09""employee_id": "57613bac5eac323cad473d28",
                "user_name": "申请者",
                "user_dept": "申请者所在部门",
                "id": "58c22edd6819488a81120b1f",
                //审批单id//状态（1.草稿2.待审核4.已审核16.已驳回32.转交64.撤销256.审批超时）"state": 2,
                //申请单类型1.差旅2.用车3.采购"type": 1,
                //最后更新时间"update_time": "2017-03-10 12:43:09",
                "operate_auth": 0,
                //审批类型（1.弹性审批流2.固定审批流3.分条件审批流）"flow_type": 1
            },
            "guest_list": [//同行人列表
                {
                    "id": "58c22ee16819488a81120b21",//用户ID
                    "name": "佩奇",
                    "id_number": "34242583458346536",
                    "id_type": {
                        "key": 1,
                        "value": "身份证"
                    },
                    "gender": {//性别
                        "key": 1,//1:男,2:女 
                        "value": "男"
                    },
                    "birth_date": "2016-12-28",
                    "phone": "18610482862",
                    "desc": "运营部;市场部",
                    "is_employee": true,
                    //该联系人当前是否还存在"exist": true,
                     
                },
                 
            ],
            "trip_list": [
                {
                    "start_time": "2017-03-10 12:43:09",
                    "end_time": "2017-03-10 12:43:09",
                    //行程类型7.机票11.酒店15.火车3.用车"type": 7,
                    "estimated_amount": 1000,
                    //金额"start_city_name": "北京",
                    "arrival_city_name": "上海",
                    "title": "中国国航CA1501",
                    //飞机的航班信息/火车的车次/酒店的名称"content": "北京市昌平区龙水路1304号",
                    //酒店的地址"status": 1801,
                    "status_name": "出票失败"
                }
            ]
        },
        "is_external_order": 0, // 是否外采订单
        "employee_remark": "", // 用户备注
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
        "total_price_str": "-$120" 
        }
}
```
