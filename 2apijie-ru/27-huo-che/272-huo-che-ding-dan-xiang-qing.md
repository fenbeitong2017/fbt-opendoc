2.7.2 火车订单详情

####接口说明
- 1.**最新接口**
- 2.查询火车订单详情接口
  通过该接口可以查询企业使用分贝通APP下的火车订单详情信息




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
data || jsonobject |Y|
data.order_id| 火车订单ID|string |Y|5aab90ac279863130a86296f

请求示例：

```



	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":"1",
	"data":{
	  "order_id":"5aab90ac279863130a86296f"
	}



```



响应结果:



响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
order_basic_info.order\_id| 订单ID|string |Y|5aab90ac279863130a86296f
order_basic_info.create\_time|订单创建时间 |integer |Y|1523533736260
order_basic_info.employee\_name| 下单人姓名|string | Y |强仔
order_basic_info.total\_price |总价| double | Y | 
order_basic_info.employee\_name| 下单人姓名|string | Y |强仔
order_basic_info.pre_order_id| 上级订单id|string | N |(退票单,改签的的原单id)
order_basic_info.original_order_id| 最上级订单id|string | N |(改签后又进行退票操作,改签单的原单id)
order_basic_info.order\_status |订单状态|jsonobject | Y |详细订单状态参照火车状态码
order_basic_info.order\_status.key |订单状态码| integer | Y |3400
order_basic_info.order\_status.value |订单状态名称| String | Y |有退改记录
comment |评论| String | Y |
use\_customer12306\_account |是否使用12306账号| boolean | Y |false
exceeded|是否超标| boolean| N|false
apply_id |审批单ID| string | N|17948763419761f9209db83
is\_grab\_order|是否抢票订单 |boolean | Y |false
is\_external\_order |是否外采订单| integer |  Y |1
employee\_remark|用户备注| string|  Y |
total\_price\_str |价格字符串| string |  Y |订单金额字符串  ￥2.00
passengers\_info|乘客信息数组 |jsonarray |  Y |
passenger\_info|乘客信息 |jsonobject | Y |
passenger\_info.passenger\_id |乘客id| string | Y |4567988645345
passenger\_info.name|姓名| string|  Y |张三
passenger\_info.mobile\_no|手机号码 |string | Y |17080187999
passenger\_info.identity\_no |身份号码| string |  Y |23456789098765
passenger\_info.identity\_type|身份证件类型| jsonobject|  Y |1:身份证
passenger\_info.identity\_type.key|身份证件id| integer|  Y |1
passenger\_info.identity\_type.value|身份证件类型| string|  Y |身份证
ticket\_info |票信息| jsonobject |  Y |  
ticket\_info.seat\_type |席座类型| string | Y |二等座
ticket\_info.ticket\_price|票价| double|  Y |100
ticket\_info.seat\_location|坐席位置 |string | Y |08车厢,10B座
ticket\_info.ticket\_no |票号| string |  Y |E931804546
ticket\_info.can\_group_change |批量改签| boolean |  Y | 非:高级软卧", "软卧", "硬卧 均可以批量改签 false
ticket\_info.ticket\_status|订单状态|jsonobject | Y |详细订单状态参照火车订单状态码
ticket\_info.ticket\_status.key|订单状态id|integer | Y |3801
ticket\_info.ticket\_status.value|订单状态信息|string | Y |退票成功
refund\_info |退票信息| jsonobject | Y |
refund\_info.refund\_money|退票金额| double|  Y |0
refund\_info.refund\_fee|退票费 |double | Y |0
refund\_info.reason |退票原因| string |  Y |""
endorse\_info|改签信息| jsonobject|  Y |
endorse\_info.supplementary\_payment |改签生成新单的价格| double |  Y |  20
endorse\_info.diff\_price|改签差价| double| Y |0
endorse\_info.endorse\_fee |改签手续费| double | Y |2 
endorse\_info.reason|改签原因| string| Y |时间紧张
ticket\_tips |票状态说明| string | Y | 
insurance\_info|保险信息 |jsonarray | Y |
can\_process |是否可查看企业订单| boolean |  Y |false
cost\_attribution|费用归属| string|  Y |研发部//按部门费用归属;国开行项目:按项目
contact\_info |联系人信息| jsonobject | Y|  
contact\_info.contact\_name|联系人姓名| string| Y |强仔
contact\_info.contact\_phone |联系人手机号| string | Y |13848420234
refund\_price\_info|退票信息| jsonobject|N|可能为空，为空不展示
refund\_price |退订金额（票价单价)|double|N| 退订金额（票价）
refund\_cost |退票手续费| double |N|退订费（扣除的钱）
refund\_total\_price|退票总价 |double |N|退款总额（到手的钱）
endorse\_price\_info |改签信息| jsonobject | N |可能为空，为空不展示
endorse\_price|改签差价（差价）| double|  N |改签差价（差价）
endorse\_cost |改签手续费| double |  N | 改签费（改签费）
endorse\_total\_price|改签总价| double| N |改签总额（改签总花费即差价+改签费)
dc| 正负|integer |N|如票价是正（1）、优惠券是负（-1
grab\_info|抢票信息|jsonobject|N|
excced_info|超标信息 |jsonobject|N|超标信息
excced_info.reason|超标理由 |string|N|超标理由
excced_info.comment|超标理由备注 |string|N|超标理由备注
third_cost_attribution_id|第三方费用归属ID |79984672984398|
third_cost_attribution_type|第三方费用归属ID类型|Y|1，部门，2项目










```

{
  "request_id": "wfviC57oPVKACDNOtP9i",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "refund_price_info": {
      "refund_total_price": 3,
      "refund_price": 3,
      "refund_cost": 0
    },
    "route_info": {
      "from_station_name": "九江",
      "run_time": "1:10",
      "from_station_code": "JJG",
      "arrive_days": "0",
      "arrive_time": "14:35",
      "start_time": "13:25",
      "train_end_date": "20190514",
      "to_station_code": "WXN",
      "to_station_name": "武穴",
      "train_no": "6026",
      "choose_seat_msg": "",
      "train_code": "6026",
      "train_start_date": "20190514"
    },
    "can_process": true,
    "contact_info": {
      "contact_name": "谷健波",
      "contact_phone": "13911381353"
    },
    "cost_attribution": "权限测试(勿删)",
    "order_basic_info": {
      "is_grab_order": false,
      "batch_refund": false,
      "pre_order_id": "5cbd87b1279863316374a71f",
      "is_external_order": 0,
      "employee_phone": "13911381353",
      "order_status": {
        "color": "#26CE77",
        "value": "退票成功",
        "key": 3801
      },
      "total_price_str": "-¥3.00",
      "refund_offline": false,
      "batch_endorse": false,
      "apply_id": "5cbd865c23445f01c67bca86",
      "over_time": "17:39",
      "original_order_id": "5cbd87b1279863316374a71f",
      "exceeded": false,
      "create_time": 1556011452913,
      "total_price": -3,
      "company_id": "5747fbc10f0e60e0709d8d7d",
      "custom_remark": [],
      "employee_name": "谷健波",
      "use_customer12306_account": false,
      "vendor_id": 506,
      "employee_id": "59b8acf023445f70c3eaef80",
      "company_name": "北京分贝金服科技有限公司",
      "org_unit_id": "5bf2651123445f5335612351",
      "comment": "",
      "order_id": "5cbed9bc279863612f3fcdcf"
    },
    "cost_attribution_id": "5bf2651123445f5335612351",
    "third_cost_attribution_id": "third_privilege_test",
    "check_info": [],
    "third_cost_attribution_type": 1,
    "insurance_info": [],
    "order_type": 1,
    "passengers_info": [
      {
        "endorse_info": {
          "endorse_fee": 0,
          "reason": "",
          "supplementary_payment": 0,
          "diff_price": 0
        },
        "ticket_tips": "",
        "passenger_info": {
          "is_employee": true,
          "full_org_unit": "北京分贝金服科技有限公司/权限测试(勿删)",
          "org_unit": "权限测试(勿删)",
          "passenger_id": "59bf8abe23445f31bd64bc62",
          "name": "谷健波",
          "mobile_no": "13911381353",
          "org_unit_id": "5bf2651123445f5335612351",
          "identity_no": "110101198412242019",
          "identity_type": {
            "value": "身份证",
            "key": 1
          }
        },
        "refund_info": {
          "reason": "",
          "refund_fee": 0,
          "refund_money": 3
        },
        "ticket_info": {
          "seat_type": "硬座",
          "ticket_status": {
            "value": "退票成功",
            "key": 3801
          },
          "ticket_price": 3,
          "ticket_no": "EA43650281",
          "product_id": "5cbed9bc279863612f3fcdd0",
          "seat_no": "1",
          "seat_location": "02车厢,008号",
          "can_group_change": true
        }
      }
    ],
    "cost_attribution_category": 1
  }
}


```














