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
    "access_token":"5747fbc10f0e60e0709d8d722",
    "sign":"oihfnlyeofdh98",
    "timestamp":124124325,
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{
        "order_id":"5a98fe1b2798636ba9006f1e"                    
    }

```

 字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 order\_id | 订单ID | string | Y | 5abc5eff27986354622e6b94 
 original_order_id| 原单ID | string | Y | 5abc5eff27986354622e6980
 status | 订单状态码 | integer | Y | 2501 
 status\_name | 订单状态名称 | string | Y | 订房成功 
 checkin\_date | 入住日期 | integer | Y | 1524499200000 
 checkout\_date | 离店日期 | integer | Y | 1524585600000 
 create\_time | 创建时间 | integer | Y | 1522294527444 
 excced_info|超标信息 |jsonobject|N|超标信息
excced_info.reason|超标理由 |string|N|超标理由
excced_info.comment|超标理由备注 |string|N|超标理由备注
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
third_org_id|第三方部门id|string|Y|OWKD8ED8JR4
third_org_name|第三方部门名称|string|Y|服务端
third_parent_org_id|第三方父部门id|string|Y|JD8E8J9EJD8
third_parent_org_name|第三方父部门名称|string|Y|研发部
third_employee_id|第三方员工ID|string|Y|8792794244
company_name|公司名称|string|Y|北京分贝金服科技有限公司
third_cost_attribution_id|第三方费用归属ID |string|Y|79984672984398|
third_cost_attribution_type|第三方费用归属ID类型|string|Y|1，部门，2项目










```

{
  "request_id": "14RmpTXcfW7azSY6WPim",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "third_org_name": "权限测试(勿删)",
    "exceed_info": {
      "reason": ""
    },
    "SpecialRequests": {
      "IsSupportSpecialInvoice": false,
      "ReceiveTextRemark": false,
      "context": "无"
    },
    "third_parent_org_name": "北京分贝金服科技有限公司",
    "room_code": "18856203",
    "window_type": "无窗",
    "plan_code": "H756893|51973895|qiantao2|145657137",
    "order_person_id": "59b8acf023445f70c3eaef80",
    "hotel_address": "雅宝路7号",
    "hotel_code": "5ab4e3fd979d9654fc46d938",
    "remark_reason": "学习培训",
    "cost_attribution": "刘悦小青蛙测试",
    "member_rights": "",
    "hotel_phone": "010-85621093",
    "check_info": [],
    "order_person_phone": "13911381353",
    "price": 227,
    "price_rule_tag": "不可取消",
    "over_time": "14:54",
    "order_type": 1,
    "is_can_apply_refund": false,
    "hotel_lng": "116.436630",
    "exceeded": true,
    "create_time": 1557469482022,
    "last_cancel_time": "",
    "total_pay_price": "¥227.00",
    "bed_type": "大床",
    "contact_phone_no": "13911381353",
    "custom_remark": [],
    "brand_name": "99旅馆",
    "person_pay_flag": true,
    "breakfast_pair": {
      "value": "不含早餐",
      "key": 0
    },
    "limit_price": 182,
    "hotel_lat": "39.916085",
    "plan_name": "普通大床房(公卫)(无窗)",
    "hotel_name": "99优选酒店(北京雅宝路儿研所店)",
    "room_name": "普通大床房",
    "checkin_date": 1559059200000,
    "third_cost_attribution_type": 2,
    "company_name": "北京分贝金服科技有限公司",
    "insurance_info": [],
    "guest_type": 0,
    "breakfast": "无早",
    "order_id": "5cd519292798633b8a8fd10f",
    "has_enterprise_price": false,
    "star_rated": "经济型",
    "status": 2301,
    "order_person": "谷健波",
    "personal_pay_price": "¥45.00",
    "order_person_org_unit_id": "5bf2651123445f5335612351",
    "order_person_org_unit_full_name": "北京分贝金服科技有限公司/权限测试(勿删)",
    "can_process": true,
    "city_code": "1000001",
    "remark": "学习培训",
    "checkout_date": 1559145600000,
    "is_external_order": 0,
    "cost_attribution_id": "5cd3e50223445f61f5a515e4",
    "third_cost_attribution_id": "",
    "price_detail": [],
    "order_person_org_unit_name": "权限测试(勿删)",
    "city_name": "北京市",
    "total_price_str": "¥182.00",
    "policy_code": "(null)",
    "original_order_id": "5cd519292798633b8a8fd10f",
    "contact_name": "谷健波",
    "per_room_night_prices_raw": [
      [
        220
      ]
    ],
    "third_parent_org_id": "dingding10",
    "total_price": "¥182.00",
    "status_name": "已取消",
    "room_count": 1,
    "areaList": [
      "72",
      "1000001",
      "1"
    ],
    "third_employee_id": "third_jianren",
    "refund_info": {
      "is_has_refund": false
    },
    "third_org_id": "third_privilege_test",
    "other_refund_desc": "无",
    "campaign_info": [],
    "per_room_night_prices": [
      [
        227
      ]
    ],
    "cost_attribution_type": 2,
    "guests": [
      {
        "is_employee": true,
        "full_org_unit": "北京分贝金服科技有限公司/权限测试(勿删)",
        "phone_no": "13911381353",
        "org_unit": "权限测试(勿删)",
        "gender": {
          "value": "男",
          "key": 1
        },
        "birth_date": "1984-12-24 00:00:00",
        "name": "谷健波",
        "org_unit_id": "5bf2651123445f5335612351",
        "id": "59bf8abe23445f31bd64bc62",
        "identity_no": "110101198412242019",
        "identity_type": {
          "value": "身份证",
          "key": 1
        }
      }
    ],
    "comment": "",
    "price_rule": "不可取消，未入住将扣除全部房费"
  }
}
```



