2.8.2 酒店订单详情

####接口说明
- 1.**最新接口**
- 2.查询酒店订单详情接口
  通过该接口可以查询企业使用分贝通APP下的酒店订单详情信息





请求方式|请求地址
----|---
POST|/open/api/hotel/order/detail

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.order_id|订单号|string|Y|订单ID

请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"5a98fe1b2798636ba9006f1e"					
	}
}


```



字段|名称|类型|必填|描述
-----|-----|----|----|----
order_id|订单ID |String |Y|5abc5eff27986354622e6b94
status|订单状态 |integer |Y|2501
status_name|订单状态名称 | string |Y|订房成功
checkin_date| 入住日期|integer |Y|1524499200000
checkout_date| 离店日期|integer|Y|1524585600000
create_time|创建时间|integer|Y|1522294527444
can_process|是否可以查看订单|boolean|Y|false
cost_attribution|费用归属| string | Y |X部门
order_person|下单人姓名| string |Y| 刘维中
order_person_phone|下单人手机号| string |Y| 18601016943
city_code|城市编码| String |Y| 0 1:是,0:否
hotel_address |酒店地址| string |Y|金钟路896号
hotel_code|酒店code|string|Y| 5abb0028979d961a343a12fb
hotel_name|酒店名称|string|Y| 如家酒店
hotel_lat|酒店经度|string| Y | 11.993970
hotel_lng|酒店维度| string | Y |11.993538
hotel_phone|酒店电话| string | Y |010-53767110
bed_type |床类型| string |Y|
room_code|房间code|string|Y| DR
room_name|房间房型|string|Y| 大床房
room_count|房间数量|integer| Y | 1
plan_code|价格计划code| string | Y|  573273659/ 6647611164/51661617
per_room_night_prices|每间房每晚价格| double | Y |150
price_rule|价格|string| Y |订单确认后，如在北京时间2018-03-26 23:00:00 （含）点前取消，可全额退款！其它时间不可取消，不可变更。如未入住扣除全额房费
plan_name|计划名称| string |Y|大床房
price_rule_tag|取消规则| string |Y|取消规则
price|价格| double |Y| 66
contact_name|联系人姓名| string |Y|王强
contact_phone_no|联系人手机号| string |Y|18601016943
guest_type|使用人身份类型| integer |Y|0
guests|使用人信息| jsonarray |Y|使用人信息
guests.name|使用人姓名| string |Y| 66
guests.phone_no|使用人手机号| string |Y|18601016943
total_price_str|价格字符串| string |Y|￥41.00
is_external_order|是否外采订单| integer |Y|0
check_info|订票提醒信息| jsonarray |Y|
employee_remark|备注| String |Y|
has_enterprise_price|是否企业协议价| boolean |Y| false
other_refund_desc|退票信息描述| string |Y|无
is_can_apply_refund|判断是否可取消| boolean |Y| false
refund_info|退票信息| jsonobject |Y|
is_has_refund|是否有退票| boolean |Y|false
remark_reason|备注| String |Y|其他
exceeded|是否超标| boolean |Y|false
insurance_info|保险信息| jsonarray |N|
comment|评论| String |Y|其他




















```
{
    "request_id": "XGabUT2cyw4Y5IdrsXlS",
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "5a98fe1b2798636ba9006f1e",
        "status": 2301,
        "status_name": "已取消",
        "create_time": 1519975963862,
        "can_process": true,
        "cost_attribution": "北京分贝金服科技有限公司",
        "order_person": "韩冰",
        "order_person_phone": "17080151888",
        "checkin_date": 1522080000000,//入住时间
        "checkout_date": 1522166400000,//离店时间
        "city_code": "904",//城市编码
        "hotel_name": "汉庭南京六合长江路酒店",//酒店名称
        "hotel_lng": "118.837468",//酒店经度
        "hotel_lat": "32.345671",//酒店维度
        "hotel_address": "江苏省南京市六合区雄州街道棠城西路179号",//酒店地址
        "hotel_code": "5a41ed51979d9663f8b4c5de",//酒店code
        "city_name": "南京市",
        "policy_code": "1",
        "hotel_phone": "025-57508988",
        "bed_type": "(null)",
        "room_code": "DR",
        "room_name": "大床房",
        "room_count": 1,
        "plan_code": "573273659|6647611164||51661617",
        "per_room_night_prices": [
            [
                150
            ]
        ],
        "price_rule": "订单确认后，如在北京时间2018-03-26 23:00:00 （含）点前取消，可全额退款！其它时间不可取消，不可变更。如未入住扣除全额房费。",
        "plan_name": "大床房",
        "price_rule_tag": "取消规则",
        "price": 150,//价格
        "contact_name": "韩树起",//联系人姓名
        "contact_phone_no": "17080151667",//联系人手机号
        "guest_type": 0,
        "guests": [
            {
                "name": "韩美美",
                "phone_no": "12989890909"
            }
        ],
        "total_price_str": "￥150.00",
        "is_external_order": 0,
        "check_info": [],
        "employee_remark": null,
        "has_enterprise_price": false,
        "other_refund_desc": "无",
        "is_can_apply_refund": false,
        "refund_info": {
            "is_has_refund": false
        },
        "remark_reason": "其他",
        "exceeded": false,
        "insurance_info": [],
        "comment": ""
    }
}


```








