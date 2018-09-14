2.8.2 酒店订单详情

#### 接口说明

* 1.**最新接口**
* 2.查询酒店订单详情接口
  通过该接口可以查询企业使用分贝通APP下的酒店订单详情信息
 
 
 
 
 请求方式|请求地址
----|----
POST|/open/api/hotel/order/detail




请求参数，以application/x-www-form-urlencoded传递：

字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 timestamp | 时间戳 | long | Y | 13位时间戳 
 sign | 签名 | string | Y 
 access\_token | token | string | Y | 登录 token 
 employee\_id | 操作人id | string | Y | 操作人id,调用接口人 id 
 employee\_type | 用户类型 | String | Y | 0为分贝用户，1为第三方用户 
 data | 请求数据 | jsonobject | Y | 请求数据 
 data.order\_id | 订单号 | string | Y | 订单ID 

请求示例：

```
{    "access_token":"5747fbc10f0e60e0709d8d722",
    "sign":"oihfnlyeofdh98",
    "timestamp":124124325,
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":1,
    "data":{
        "order_id":"5a98fe1b2798636ba9006f1e"                    
    }
}
```

 字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 order\_id | 订单ID | string | Y | 5abc5eff27986354622e6b94 
 status | 订单状态码 | integer | Y | 2501 
 status\_name | 订单状态名称 | string | Y | 订房成功 
 checkin\_date | 入住日期 | integer | Y | 1524499200000 
 checkout\_date | 离店日期 | integer | Y | 1524585600000 
 create\_time | 创建时间 | integer | Y | 1522294527444 
 excced_info|超标信息 |jsonobject|N|超标信息
excced_info.reason|超标理由 |jsonobject|N|超标理由
excced_info|超标理由备注 |jsonobject|N|超标理由备注
 can\_process | 是否可以查看订单 | boolean | Y | false 
 cost\_attribution | 费用归属 | string | Y | 研发部//按部门费用归属;国开行项目:按项目 
 order\_person | 下单人姓名 | string | Y | 刘维中 
 order\_person\_phone | 下单人手机号 | string | Y | 18601016943 
 city\_code | 城市编码 | string | Y | 0 1:是,0:否 
 hotel\_address | 酒店地址 | string | Y | 金钟路896号 
 hotel\_code | 酒店code | string | Y | 5abb0028979d961a343a12fb 
 hotel\_name | 酒店名称 | string | Y | 如家酒店 
 hotel\_lat | 酒店经度 | string | Y | 11.993970 
 hotel\_lng | 酒店维度 | string | Y | 11.993538 
 hotel\_phone | 酒店电话 | string | Y | 010-53767110 
 bed\_type | 床类型 | string | Y |
room\_code | 房间code | string | Y | DR 
 room\_name | 房间房型 | string | Y | 大床房 
 room\_count | 房间数量 | integer | Y | 1 
 plan\_code | 价格计划code | string | Y | 573273659/ 6647611164/51661617 
 per\_room\_night\_prices | 每间房每晚价格 | double | Y | 150 
 price\_rule | 取消详细信息 | string | Y | 订单确认后，如在北京时间2018-03-26 23:00:00 （含）点前取消，可全额退款！其它时间不可取消，不可变更。如未入住扣除全额房费 
 plan\_name | 价格计划名称 | string | Y | 大床房 
 price\_rule\_tag | 取消规则 | string | Y | 取消规则 
 price | 价格 | double | Y | 66.00 
 contact\_name | 联系人姓名 | string | Y | 王强 
 contact\_phone\_no | 联系人手机号 | string | Y | 18601016943 
 guest\_type | 使用人身份类型 | integer | Y | 0,详细信息参照身份状态码 
 guests | 使用人信息 | jsonarray | Y | 使用人信息 
 guests.name | 使用人姓名 | string | Y | 张三 
 guests.phone\_no | 使用人手机号 | string | Y | 18601016943 
 total\_price\_str | 价格字符串 | string | Y | ￥41.00 
 is\_external\_order | 是否外采订单 | integer | Y | 0 0:非外采 
 check\_info | 订房提醒信息 | jsonarray | Y |订票提醒信息
 employee\_remark | 备注 | string | Y |备注信息
 has\_enterprise\_price | 是否企业协议价 | boolean | Y | false 
other\_refund\_desc | 退房信息描述 | string | Y | 无 
is\_can\_apply\_refund | 判断是否可取消 | boolean | Y | false 
refund\_info | 退房信息 | jsonobject | Y |退票信息
is\_has\_refund | 是否有退房 | boolean | Y | false 
remark\_reason | 备注 | string | Y | 其他 
exceeded | 是否超标 | boolean | Y | false 
apply_id |审批单ID| string | N|17948763419761f9209db83
insurance\_info | 保险信息 | jsonarray | N |保险信息
comment | 评论 | string | Y | 其他 
"excced_info": {
"reason": "舱位没票了",
"comment": "仓位没票"
}

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
        "cost_attribution": "研发部",
        "order_person": "韩冰",
        "apply_id": "5b61757323445f071a732860",
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
        "check_info": [{
                "title": "未提前5天预订酒店",//事由标题
                "reason": "陪客户出行",//事由
                "comment": ""//事由补充说明
            },
            {
                "title": "未选择推荐房型的理由",
                "reason": "票数不够了",
                "comment": ""
            }],
        "employee_remark": null,
        "has_enterprise_price": false,
        "other_refund_desc": "无",
        "is_can_apply_refund": false,
        "refund_info": {
            "is_has_refund": false
        },
        "remark_reason": "其他",
        "exceeded": true,
        "excced_info": {
			"reason": "酒店没房了",
			"comment": "很重要"
		},

        "insurance_info": [],
        "comment": ""
    }
}
```



