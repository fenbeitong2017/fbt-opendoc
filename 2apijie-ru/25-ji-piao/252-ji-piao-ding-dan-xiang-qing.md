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
sign|签名 |string |Y|24iu7s23sdu2ewdj782dsjsdu
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data|请求数据|jsonobject|Y|请求数据
data.order_id |机票订单id|string|Y|523234c1323445f2d54dd0

请求示例：

```

	"access_token":"5747fbc10f0e60e0709d8d722",
	"timestamp":124124325,
	"sign":"oihfnlyeofdh98",
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"523234c1323445f2d54dd0"
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
insurance_info.category_code|险种| string|N| 1:航意险，2：航延险
insurance_info.unit_price|保费| integer |N|
insurant_list.policy_number |保单编号| string|N|10450061900247380997
status.key |保单状态| integer |N|8:退保成功.详细请参照保险状态码
insurant_list.insurant_name |被保人| string |N|张胜男
insurant_amount |数量| integer | N |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
employee_remark|用户备注| string |N|出差使用
is_external_order|是否是回填| integer | Y |0:不是回填  1:回填
stipulate_info|退改签规则信息| jsonobject |N|根据是否为回填单来进行获取数据
endorse_price|改签差价| double |N|10
endorse_cost|改签费| double |N|30
endorse_total_price|改签总价| double |N|40
third_org_id|第三方部门id|string|Y|OWKD8ED8JR4
third_org_name|第三方部门名称|string|Y|服务端
third_parent_org_id|第三方父部门id|string|Y|JD8E8J9EJD8
third_parent_org_name|第三方父部门名称|string|Y|研发部
third_employee_id|第三方员工ID|string|Y|8792794244
company_name|公司名称|string|Y|北京分贝金服科技有限公司
third_cost_attribution_id|第三方费用归属ID |79984672984398|
third_cost_attribution_type|第三方费用归属ID类型|Y|1，部门，2项目



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
            "par_price": 950
        },
        "policy_info": {
            "policy_id": "229099290"
        },
        "stipulate_info": {
            "cabin": "Y",//仓位
            "comment": "以航空公司规定为准",//特殊说明
            "refund_stipulate": "取消座位时间计算手续费；按照当前舱位票面价收取退票费；起飞前2.0小时（含）以外收取当前舱位票面价的5.0%退票费,起飞前2.0小时以内及起飞后收取当前舱位票面价的10.0%退票费；\n*此规定仅供参考，最终以航空公司规定为准",//退票条件
            "modify_stipulate": "不能签转；\n*此规定仅供参考，最终以航空公司规定为准",//签转
            "change_stipulate": "按照当前舱位票面价收取变更费；起飞前2.0小时（含）以外免收改期费,起飞前2.0小时以内及起飞后收取当前舱位票面价的5.0%改期费；\n*此规定仅供参考，最终以航空公司规定为准",//改签条件
            "par_price": 950,//票面价
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
        "third_parent_org_id": "JD8E8J9EJD8",
        "third_org_name": "服务端",
        "third_parent_org_name": "研发部",
        "third_org_id": "OWKD8ED8JR4",
        "third_employee_id":"8792794244",
        "company_name":"北京分贝金服科技有限公司",
        "order_total_price": -950
    }
}


```

```
出票成功返回的数据结构:


```
{
  "request_id": "JFX6e3w5QFBjGeGeXtjU",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "third_org_name": "",
    "excced_info": {},
    "contact_phone": "139****1353",
    "third_parent_org_name": "",
    "org_unit_full_name": "北京分贝金服科技有限公司/农村工作小组/测试部门删除后返回数据",
    "remark_reason": "其他",
    "cost_attribution": "测试部门删除后返回数据",
    "manual_remark": "无",
    "attribution_id": "5cd515b923445f1800049463",
    "check_info": [],
    "policy_info": {
      "policy_type": "0",
      "policy_id": "0"
    },
    "exceed": false,
    "order_total_price": 850,
    "remote_order_id": "8543892",
    "over_time": "14:29",
    "order_type": 1,
    "price_info": {
      "coupon_amount": 0,
      "settle_price": 800,
      "add_price": 0,
      "price": 800,
      "airport_tax": 50,
      "discount": 0.56,
      "fuel_tax": 0,
      "sale_price": 800,
      "par_price": 800
    },
    "create_time": "2019-05-10 14:14:01",
    "custom_remark": [],
    "destination_city_use_car_authority": true,
    "online_check": {
      "online_check_url": "https://h5.133.cn/hangban/partner/fenbeitong/checkin",
      "online_check_authority": true
    },
    "third_cost_attribution_type": 1,
    "company_name": "",
    "org_unit_id": "5cd515b923445f1800049463",
    "order_id": "5cd516a9e4b02bcc50902fd1",
    "supplier_id": 118,
    "starting_city_use_car_authority": true,
    "status": {
      "value": "待支付",
      "key": 1100
    },
    "pre_order_id": "5cd516a9e4b02bcc50902fd1",
    "is_manual": false,
    "can_process": true,
    "is_external_order": 0,
    "third_cost_attribution_id": "",
    "price_detail": [
      {
        "amount_desc": "1人",
        "price": 800,
        "key": "票价",
        "dc": 1
      },
      {
        "amount_desc": "1人",
        "price": 50,
        "key": "机建",
        "dc": 1
      }
    ],
    "total_price_str": "¥850.00",
    "trip_type": 0,
    "starting_city_code": "1000001",
    "destination_city_code": "2000002",
    "passenger_list": [
      {
        "ticket_tips": "",
        "product_id": "5cd516a9e4b02bcc50902fd2",
        "passenger_info": {
          "org_unit": "测试部门删除后返回数据",
          "identity_type_name": {
            "value": "身份证",
            "key": 1
          },
          "gender": {
            "value": "男",
            "key": 1
          },
          "company_id": "5747fbc10f0e60e0709d8d7d",
          "birth_date": "1984-12-24",
          "type": 0,
          "full_org_unit": "北京分贝金服科技有限公司/农村工作小组/测试部门删除后返回数据",
          "phone": "139****1353",
          "company_name": "北京分贝金服科技有限公司",
          "name": "谷健波",
          "org_unit_id": "5cd515b923445f1800049463",
          "id": "59bf8abe23445f31bd64bc62",
          "identity_no": "110101**********19",
          "identity_type": "1",
          "not_encryption": "13911381353"
        },
        "can_refund": false,
        "can_endorse": false,
        "status": {
          "value": "待支付",
          "key": 1100
        }
      }
    ],
    "stipulate_info": {
      "stipulate_name": "退改签规则",
      "refund_stipulate": "航班起飞前168小时之前，退票手续费为83元；航班起飞前48小时之前，退票手续费为166元；航班起飞前4小时之前，退票手续费为332元；航班起飞前4小时之后，退票手续费为415元\n*此规定仅供参考，最终以航空公司规定为准",
      "modify_stipulate": "不可签转\n*此规定仅供参考，最终以航空公司规定为准",
      "cabin": "V",
      "change_stipulate": "航班起飞前168小时之前，改期手续费为42元；航班起飞前48小时之前，改期手续费为125元；航班起飞前4小时之前，改期手续费为249元；航班起飞前4小时之后，改期手续费为332元\n*此规定仅供参考，最终以航空公司规定为准",
      "comment": "手提行李：1件，10KG，20×55×40CM；托运行李：20KG，40×60×100CM；婴儿票行李：无免费行李额，每个婴儿可免费托运婴儿手推车1辆。\n\n*此规定仅供参考，最终以航空公司规定为准",
      "baggage_info": {
        "baggage_name": "行李规定",
        "baggage_context": "手提行李：1件，10KG，20×55×40CM；托运行李：20KG，40×60×100CM；婴儿票行李：无免费行李额，每个婴儿可免费托运婴儿手推车1辆。\n\n*此规定仅供参考，最终以航空公司规定为准",
        "color": "#666666"
      },
      "par_price": 800
    },
    "segment_info": {
      "bk_info": {
        "bookingTag": "XNUWpgpYqKYAD6r8uFHIB/sXcMR2NIkPWH2q7A==",
        "priceInfo": {
          "ticketPrice": "0",
          "childtof": "0",
          "priceTag": {
            "ADU": [
              {
                "barePrice": 800,
                "originalBarePrice": 0,
                "policyPrice": 0,
                "packagePrice": 800,
                "addPrice": 0,
                "tag": "CXF1",
                "viewPrice": 800,
                "originalPackagePrice": 0
              }
            ],
            "adu": [
              {
                "barePrice": 800,
                "originalBarePrice": 0,
                "policyPrice": 0,
                "packagePrice": 800,
                "addPrice": 0,
                "tag": "CXF1",
                "viewPrice": 800,
                "originalPackagePrice": 0
              }
            ],
            "chi": [
              {
                "barePrice": 680,
                "originalBarePrice": 0,
                "policyPrice": 0,
                "packagePrice": 680,
                "addPrice": 0,
                "tag": "CHI1",
                "viewPrice": 680,
                "originalPackagePrice": 0
              }
            ],
            "CHI": [
              {
                "barePrice": 680,
                "originalBarePrice": 0,
                "policyPrice": 0,
                "packagePrice": 680,
                "addPrice": 0,
                "tag": "CHI1",
                "viewPrice": 680,
                "originalPackagePrice": 0
              }
            ]
          },
          "discount": "5.9",
          "tof": "0",
          "prdTag": "CXF",
          "inventory": {
            "all": "A",
            "baby": "A",
            "adult": "A",
            "child": "A"
          },
          "babyTicketPrice": "0",
          "babyServiceFee": "0",
          "babyPrice": "0",
          "cutMoney": "0",
          "childTicketPrice": "0",
          "arf": "50",
          "price": "0",
          "barePrice": "0",
          "returnMoney": "0",
          "childPrice": "0",
          "dtTag": "CXF1",
          "basePrice": "1360"
        },
        "ticketTime": "支付成功后1小时内出票",
        "flightInfo": [
          {
            "arrDate": "2019-05-23",
            "dptAirport": "首都机场",
            "arrCity": "上海",
            "cabin": "V",
            "tof": "0",
            "ccbcn": "全价经济舱",
            "babyCabin": "Y",
            "dptTime": "06:50",
            "flightNum": "HO1252",
            "arf": "50",
            "carrierName": "上海吉祥航空公司",
            "codeShare": false,
            "actFlightNum": "",
            "arrAirport": "虹桥机场",
            "childCabin": "Y",
            "arr": "SHA",
            "dptCity": "北京",
            "cbcn": "经济舱",
            "ctof": "0",
            "dptDate": "2019-05-23",
            "flightTimes": "2小时15分钟",
            "dpt": "PEK",
            "dptTerminal": "T3",
            "carrier": "HO",
            "planeCode": "321",
            "arrTerminal": "T2",
            "stops": 0,
            "arrTime": "09:05",
            "bcbcn": "全价经济舱"
          }
        ],
        "tgqShowData": {
          "changeRule": "5-168-15-48-30-4-40",
          "signText": "不可签转",
          "tgqFrom": 0,
          "canRefund": true,
          "tgqPointCharges": [
            {
              "returnFee": 83,
              "timeText": "2019年05月16日 06:50前",
              "changeFee": 42,
              "time": 168
            },
            {
              "returnFee": 166,
              "timeText": "2019年05月21日 06:50前",
              "changeFee": 125,
              "time": 48
            },
            {
              "returnFee": 332,
              "timeText": "2019年05月23日 02:50前",
              "changeFee": 249,
              "time": 4
            },
            {
              "returnFee": 415,
              "timeText": "2019年05月23日 02:50后",
              "changeFee": 332,
              "time": -2147483648
            }
          ],
          "hasTime": true,
          "returnText": "航班起飞前168小时之前，退票手续费为83元；航班起飞前48小时之前，退票手续费为166元；航班起飞前4小时之前，退票手续费为332元；航班起飞前4小时之后，退票手续费为415元",
          "changeText": "航班起飞前168小时之前，改期手续费为42元；航班起飞前48小时之前，改期手续费为125元；航班起飞前4小时之前，改期手续费为249元；航班起飞前4小时之后，改期手续费为332元",
          "tgqCabin": "V",
          "airlineTgq": false,
          "canCharge": true,
          "viewType": 1,
          "tgqText": "同舱更改条件：航班起飞前168小时之前，改期手续费为42元；航班起飞前48小时之前，改期手续费为125元；航班起飞前4小时之前，改期手续费为249元；航班起飞前4小时之后，改期手续费为332元<br />退票条件：航班起飞前168小时之前，退票手续费为83元；航班起飞前48小时之前，退票手续费为166元；航班起飞前4小时之前，退票手续费为332元；航班起飞前4小时之后，退票手续费为415元<br />签转条件：不可签转",
          "basePrice": 830,
          "allowChange": false,
          "returnRule": "10-168-20-48-40-4-50"
        },
        "expressInfo": {
          "receiverType": {
            "2": "个人",
            "3": "企业",
            "4": "政府机关单位"
          },
          "price": 20,
          "invoiceType": {
            "2": "行程单和差额发票"
          },
          "id": 7
        },
        "errMsg": "",
        "bookingStatus": "BOOKING_SUCCESS",
        "extInfo": {
          "bookingTime": "",
          "qt": "3b63d505-899d-4555-b3f8-d93a56d5876c",
          "clientId": "lah.trade.qunar.com",
          "wrapperId": "ttsgndh3335",
          "deptTime": "0650",
          "cabin": "V",
          "flightType": "1",
          "flightNum": "HO1252",
          "carrier": "",
          "policyId": "0",
          "barePrice": "800",
          "price": "800",
          "policyType": "0",
          "ticketPirce": "800",
          "from": "PEK",
          "startTime": "2019-05-23",
          "tag": "CXF1",
          "to": "SHA",
          "basePrice": "0"
        }
      },
      "starting_terminal": "T3",
      "departure_date": "2019-05-23",
      "cabin": "V",
      "business_ext": "Vma/KC3/v9FG2M3TO/nM1J8q60F104fP8XtXYneKfcTnhiX1ETA6C1fT/ZDPeJowjI+M4EGgZETp76y8qlBVE3Ib9/HiaQTf921EnclWemqNIm7VmtbthQgmJvY3j6C1Pyx/v+07sbZZ4TGOLL/Iqi4n7IFLXUkHovhJ6SlHdAF9IkHU8RA+h6yd4P8nKBU7bHHyqMLlKB80NDvSsTrx6iSyuT8liwxomZnmEyvfh1RqGnz1nGBFEd6RQIuT+mpSJ+mZBtzNMu4jaP5XtF3PPake+t0V9VDYnl9PMpQgoDuncmAGtsRVFS9db8c85LzPdY9rt7KueAr1/yG8icyLNn0spXMW6sDdwR7c9QZhio3edt3bpsWm+YMgE1HLmX6sev8egog4qqEUsfuqji4uUyTK4Ytys+4yDPuugS0ZXVqZGx9FNlU7sUN2swsY/nVsKfOEoQWpVSBpvbppWrCn/u80XkzdMObZNGCih7U1BOaP39eUuW1JoRTiOKH8mAY2EC9JCbZtbAxGp4kQTr+xMMAVDk9MnNicU2hfe7JoAw7zBNcg+g+w1uy7ZYLiLJxWPZv7u4DYYn7p5bzY20JJXYgVQ2NVMI274IhlmQN6sOKXYKuz2OD4loyOSqRIxGF/V5Wdq0HevCZjW/hy0ZX2u+scKIVI8Woj2XBbH9wl38UKJdgKwjFeSGXykq3GeyYgdqcawgkF1hTEQ6U8c8ls1UgmraqDhvkmMrnWd55Mdya+3X4C1zUqiPlWo8KNHkhQ4X//nQFJRi2Ic9HR74hFMbTyGC4szEZLu/QMCfpsqYVmmXXkmquX3mEsrwceim5HKfnSGjjlSPt2e535+Kc+7jn2q+4/uGpqQXsoquFgflTCrGUk4OG4hZ9heF+COMyotE7zRR+I3cUoQ0RWRGTOPC+fXlx+fHiwpqLcE1x9UyFfINCdQZCl3Ocoo3uJ78vsad+AOU/4IqgbAv52G7V01PteN36li6empqjLNpAmJ6JQ3X7j9VMOIzhZ7SY8JUZ+V71AWDj02U549WxEDR2sdl/3gScQEtRZhDeZFi3j0hiTXB6TSjaJSAV6Q9l4M5Dyn6Bom/UGs5pwYOR9zwZbpKl3vQUkZUWcDNWOL5Y2K0/WKezFd+SERIFeadamp6qkgJzzWhrChSCajkAcv5VxQyXyql82q1Dd7KyYAugnf7iirn8se5LRnCa3XPSW7vJU+WvquzOTr9qDF3U1iWR7kqyGu/8dKU6JFxd7BRegzAKIXqxtCp5h3VhyJawbiA+c/VvZbNW5pxKeUeXv0GuwOfJPymFUgTFS8g8saWMo2L7+M5F/UbnwjOS3tIWRwu4QgGxwIy0/kLW0GdvXu4Rh5DupDXzVtxl920Gzr90HyTBehZq0irRxR8w1O/m2TsMdkePIaY+VS+20HuOa2naRVItGuCfxiulw/Vi9RQPXHIpZ9es6RHCnX8YfKLhAejziU4SjM79jX/3aUX/mNDzrb1ENE1c5uDYEOriFXADW3AfxxfdOVWw+gCPta8GE0OYYbCS/gUzW1oSTzwhPWcqev7HC3rNICefOJXckU3iI7og59LItzC6DeUj/6YRiRjZx5qDtwPRX1bh5Bv0HoFryXg==",
      "destination_terminal": "T2",
      "wrapper_id": "ttsgndh3335",
      "is_middle_stop": false,
      "airline_logo_url": "http://image.fenbeitong.com/images/2018/06/13/air_icon/5b20dc7f5d88db354cd5d7ef.png",
      "flight_no": "HO1252",
      "seat_msg": "经济舱",
      "client": "lah.trade.qunar.com",
      "tag": "CXF1",
      "departure_time": "0650",
      "arrived_timestamp": 1558573500000,
      "share_num": "",
      "starting_airport": "首都机场",
      "departure_timestamp": 1558565400000,
      "starting_code": "PEK",
      "starting_city": "北京市",
      "share_airline_name": "",
      "airline_name": "吉祥航空",
      "destination_city": "上海市",
      "destination_airport": "虹桥机场",
      "destination_code": "SHA",
      "stop_info": "",
      "code_share": false,
      "is_official": false,
      "carrier": "HO",
      "middle_stop": false,
      "plane_type": "321",
      "arrived_time": "0905"
    },
    "contact_name": "谷健波",
    "has_endorse": false,
    "third_parent_org_id": "",
    "total_price": 850,
    "order_owner": {
      "user_id": "59b8acf023445f70c3eaef80",
      "phone": "13911381353",
      "name": "谷健波",
      "email": ""
    },
    "third_employee_id": "third_jianren",
    "third_org_id": "",
    "attribution_category": 1,
    "not_encryption_contact_phone": "13911381353",
    "comment": "请在14:29前完成支付，超时订单将关闭"
  }
}


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
                    "upgrade_price":5,//升舱费用
                    "upgrade_price_msg":"升舱成功",//升舱说明
                    "change_fee":4,//改期费用
                    "agency_fee":0,
                    "change_fee_msg":"改期成功"//改期说明
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
        "third_parent_org_id": "JD8E8J9EJD8",
        "third_org_name": "服务端",
        "third_parent_org_name": "研发部",
        "third_org_id": "OWKD8ED8JR4",
        "third_employee_id":"8792794244",
        "company_name":"北京分贝金服科技有限公司",
        "order_total_price": 15
    }
}

```



