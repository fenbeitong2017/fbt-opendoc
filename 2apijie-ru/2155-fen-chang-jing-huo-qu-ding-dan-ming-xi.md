2.15.5分场景获取订单明细

#### 接口说明

* 1.**新接口**
* 2.根据账单单号分场景查询账单消费明细数据

| 名称 | 描述 |
| --- | --- |
| 沙箱环境地址 | [https://open-plus-test.fenbeijinfu.com](https://open-plus-test.fenbeijinfu.com) |
| 生产环境地址 | [https://open-plus.fenbeitong.com](https://open-plus.fenbeitong.com) |
| HTTP方法 | POST |
| Content-Type | application/x-www-form-urlencoded |
| method | /openapi/func/approve/create |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳 1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID |
| employee\_type | 用户类型 | string | Y | 类型，0为分贝用户，1为第三方用户 |
| data | 请求数据 | jsonobject | Y | 请求数据 |
| data.bill\_no | 账单编号 | string | Y | 账单编号 |
| data.order\_id | 订单号 | string | Y | 订单号 |
| data.order\_category | 业务类型 | integer | Y | 业务类型，3:用车;7:机票;11:酒店;15:火车;20:采购;30:口碑用餐;40:机票;50:外卖;60:美团点评;126:分贝通虚拟卡;131:快递;130:闪送;911:其他订单 |
| data.page\_index | 页码 | integer | N | 默认值1 |
| data.page\_size | 条数 | integer | N | 默认值20 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
"bill_no":"6666684100000000",
"order_id":"5be03ce02798631ecfb996b5",
"order_category":7,
"page_index":1,
"page_size":10
}
```

响应结果：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| page\_info | 分页信息 | jsonobject | Y | 分页信息 |
| page\_info.page\_size | 每页条数 | integer | Y | 每页条数 |
| page\_info.current\_page | 当前页码 | integer | Y | 当前面码 |
| page\_info.total\_pages | 分页总数 | integer | Y | 分页总数 |
| page\_info.total\_size | 数据总数 | integer | Y | 数据总数 |
| bill\_detail\_air | 机票 | jsonarray | Y | 机票 |
| bill\_detail\_hotel | 酒店 | jsonarray | Y | 酒店 |
| bill\_detail\_train | 火车 | jsonarray | Y | 火车 |
| bill\_detail\_text | 用车 | jsonarray | Y | 用车 |
| bill\_detail\_mall | 采购 | jsonarray |  | 采购 |
| bill\_detail\_mei\_shi | 口碑 | jsonarray | Y | 口碑 |
| bill\_detail\_takeout | 外卖 | jsonarray | Y | 外卖 |
| bill\_detail\_dinner | 用餐 | jsonarray | Y | 用餐 |
| bill\_detail\_virtual\_card | 分贝通虚拟卡 | jsonarray | Y | 分贝通虚拟卡 |
| bill\_detail\_express | 闪送 | jsonarray | Y | 闪送 |
| bill\_detail\_altman | 快递 | jsonarray | Y | 快递 |
| bill\_detail\_express\_delivery | 其他 | jsonarray | Y | 其他 |

```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "page_info": {
            "page": 1,
            "page_size": 10,
            "current_page": 1,
            "total_pages": 1,
            "total_size": 1
        },
        "bill_detail_air": [
            {
                "reason": " ",
                "cost_attribution_category": null,
                "cost_attribution_name": "1级部门",
                "project_code": null,
                "is_need_trip_apply": null,
                "trip_apply_id": "",
                "is_hyper_gauge": null,
                "hyper_gauge_reason": "",
                "is_need_during_apply": null,
                "during_apply_id": "",
                "hyper_gauge_info": null,
                "is_need_re_apply": null,
                "re_apply_id": "",
                "re_apply_reason": "[自愿退费]:按客规收取手续费",
                "custom_field1": null,
                "custom_field2": null,
                "custom_field3": null,
                "remark": null,
                "id": "5bf28a0523445f1225e0905e",
                "bill_id": "5bf28a0523445f1225e0905f",
                "order_create_time": "2018-11-05T00:00:00.000+0800",
                "ticket_no": "123123123",
                "order_category_type": null,
                "ticket_statue": null,
                "employee_name": "狗蛋测预算",
                "employee_phone": "12312354250",
                "department_name": "1级部门",
                "department_hierarchy": "NewFbTestFirLee/1级部门",
                "customer_name": "狗蛋测预算",
                "customer_phone": "12312354250",
                "customer_dept": "未设置",
                "customer_hierarchy_dept": "未设置",
                "trip_type": null,
                "trip_info": null,
                "flight_no": "JR1521",
                "departure_time": "2018-11-29T15:10:00.000+0800",
                "back_departure_time": null,
                "discount": 1.00,
                "sale_price": -15.00,
                "airport_fee": 0.00,
                "fuel_fee": -20.00,
                "taxes": null,
                "insurance_price": 0.00,
                "change_fee": 0.00,
                "upgrate_fee": 0.00,
                "refund_ext_fee": 10.00,
                "coupon_amount": 0.00,
                "total_price": null,
                "relief_price": null,
                "company_pay_price": -35.00,
                "service_fee": 0.00,
                "total_amount": -35.00,
                "red_coupon": null
            }
        ],
        "bill_detail_hotel": [],
        "bill_detail_train": [],
        "bill_detail_taxi": [],
        "bill_detail_mall": [],
        "bill_detail_mei_shi": [],
        "bill_detail_takeout": [],
        "bill_detail_dinner": [],
        "bill_detail_virtual_card": [],
        "bill_detail_express": [],
        "bill_detail_altman": [],
        "bill_detail_express_delivery": []
    },
    "request_id": "TlOCpld1mbs6HqGO"
}
```

bill\_detail\_air：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project\_code | 项目编号 | string | N | 项目编号 |
| is\_need\_trip\_apply | 是否需要行程审批 | string | N | 是否需要行程审批 |
| trip\_apply\_id | 行程审批单号 | string | N | 行程审批单号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| is\_need\_during\_apply | 是否需要订单审批 | string | N | 是否需要订单审批 |
| during\_apply\_id | 订单审批单号 | string | N | 订单审批单号 |
| hyper\_gauge\_info | 超规项 | string | N | 超规项 |
| is\_need\_re\_apply | 是否需要退改控制 | string | N | 是否需要退改控制 |
| re\_apply\_id | 退改审批单号 | string | N | 退改审批单号 |
| re\_apply\_reason | 退改理由 | string | N | 退改理由 |
| custom\_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom\_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom\_field3 | 自定义字段3 | string | N | 自定义字段3 |
| remark | 标签 | string | N | 标签 |
| id | 订单号 | string | N | 订单号 |
| bill\_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 预订/退票日期 | string | N | 预订/退票日期 |
| ticket\_no | 票号 | string | N | 票号 |
| order\_category\_type | 机票分类 | string | N | 机票分类 |
| ticket\_statue | 机票状态 | string | N | 机票状态 |
| employee\_name | 预订人 | string | N | 预订人 |
| employee\_phone | 预定人手机号 | string | N | 预定人手机号 |
| department\_name | 预订人直属部门 | string | N | 预订人直属部门 |
| department\_hierarchy | 预订人层级部门 | string | N | 预订人层级部门 |
| customer\_name | 旅客姓名 | string | N | 旅客姓名 |
| customer\_phone | 乘客手机号 | string | N | 乘客手机号 |
| customer\_dept | 乘客直属部门 | string | N | 乘客直属部门 |
| customer\_hierarchy\_dept | 乘客层级部门 | string | N | 乘客层级部门 |
| trip\_type | 行程类型 | integer | N | 行程类型 |
| trip\_info | 行程 | string | N | 行程 |
| flight\_no | 航班号 | string | N | 航班号 |
| departure\_time | 起飞时间/去程起飞时间 | string | N | 程：起飞时间/往返：去程起飞时间 |
| back\_departure\_time | 到达时间/回程起飞时间 | string | N | 单程：到达时间/往返：回程起飞时间 |
| discount | 机票折扣 | double | N | 机票折扣 |
| sale\_price | 票销售价 | double | N | 票销售价 |
| airport\_fee | 机场建设费 | double | N | 机场建设费 |
| fuel\_fee | 燃油费 | double | N | 燃油费 |
| taxes | 税费 | double | N | 税费 |
| insurance\_price | 保险费 | double | N | 保险费 |
| change\_fee | 改签费 | double | N | 改签费 |
| upgrate\_fee | 升舱费 | double | N | 升舱费 |
| refund\_ext\_fee | 退票费 | double | N | 退票费 |
| coupon\_amount | 优惠券/折扣 | double | N | 优惠券/折扣 |
| total\_price | 销售总价 | double | N | 销售总价 |
| relief\_price | 减免金额 | double | N | 减免金额 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service\_fee | 服务费 | double | N | 服务费 |
| total\_amount | 应收总额 | double | N | 应收总额 |
| red\_coupon | 红包券支付 | double | N | 红包券支付 |
```json
{
	"reason": " ",
	"cost_attribution_category": null,
	"cost_attribution_name": "1级部门",
	"project_code": null,
	"is_need_trip_apply": null,
	"trip_apply_id": "",
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"is_need_during_apply": null,
	"during_apply_id": "",
	"hyper_gauge_info": null,
	"is_need_re_apply": null,
	"re_apply_id": "",
	"re_apply_reason": "[自愿退费]:按客规收取手续费",
	"custom_field1": null,
	"custom_field2": null,
	"custom_field3": null,
	"remark": null,
	"id": "5bf28a0523445f1225e0905e",
	"bill_id": "5bf28a0523445f1225e0905f",
	"order_create_time": "2018-11-05T00:00:00.000+0800",
	"ticket_no": "123123123",
	"order_category_type": null,
	"ticket_statue": null,
	"employee_name": "狗蛋测预算",
	"employee_phone": "12312354250",
	"department_name": "1级部门",
	"department_hierarchy": "NewFbTestFirLee/1级部门",
	"customer_name": "狗蛋测预算",
	"customer_phone": "12312354250",
	"customer_dept": "未设置",
	"customer_hierarchy_dept": "未设置",
	"trip_type": null,
	"trip_info": null,
	"flight_no": "JR1521",
	"departure_time": "2018-11-29T15:10:00.000+0800",
	"back_departure_time": null,
	"discount": 1.00,
	"sale_price": -15.00,
	"airport_fee": 0.00,
	"fuel_fee": -20.00,
	"taxes": null,
	"insurance_price": 0.00,
	"change_fee": 0.00,
	"upgrate_fee": 0.00,
	"refund_ext_fee": 10.00,
	"coupon_amount": 0.00,
	"total_price": null,
	"relief_price": null,
	"company_pay_price": -35.00,
	"service_fee": 0.00,
	"total_amount": -35.00,
	"red_coupon": null
}
```
bill\_detail\_hotel：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project\_code | 项目编号 | string | N | 项目编号 |
| is\_need\_trip\_apply | 是否需要行程审批 | string | N | 是否需要行程审批 |
| trip\_apply\_id | 行程审批单号 | string | N | 行程审批单号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| is\_need\_during\_apply | 是否需要订单审批 | string | N | 是否需要订单审批 |
| during\_apply\_id | 订单审批单号 | string | N | 订单审批单号 |
| hyper\_gauge\_info | 超规项 | string | N | 超规项 |
| is\_need\_re\_apply | 是否需要退改控制 | string | N | 是否需要退改控制 |
| re\_apply\_id | 退改审批单号 | string | N | 退改审批单号 |
| re\_apply\_reason | 退改理由 | string | N | 退改理由 |
| custom\_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom\_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom\_field3 | 自定义字段3 | string | N | 自定义字段3 |
| remark | 标签 | string | N | 标签 |
| order\_id | 订单号 | string | N | 订单号 |
| source\_order\_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 预订/退款日期 | string | N | 预订/退款日期 |
| order\_statue | 订单状态 | string | N | 订单状态 |
| employee\_name | 预订人 | string | N | 预订人 |
| employee\_phone | 预订人手机号 | string | N | 预订人手机号 |
| department\_name | 预订人直属部门 | string | N | 预订人直属部门 |
| department\_hierarchy | 预订人层级部门 | string | N | 预订人层级部门 |
| customer\_name | 旅客姓名 | string | N | 旅客姓名 |
| customer\_phone | 旅客手机号 | string | N | 旅客手机号 |
| customer\_dept | 旅客直属部门 | string | N | 旅客直属部门 |
| customer\_hierarchy\_dept | 旅客层级部门 | string | N | 旅客层级部门 |
| check\_in\_date | 入住日期 | string | N | 入住日期，如"2018-12-28T00:00:00.000+0800" |
| check\_out\_date | 离店日期 | string | N | 离店日期，如"2018-12-29T00:00:00.000+0800" |
| check\_in\_city | 入住城市 | double | N | 入住城市 |
| hotel\_name | 酒店名称 | double | N | 酒店名称 |
| number\_of\_nights | 间夜数 | integer | N | 间夜数 |
| room\_price | 平均客房单价 | double | N | 平均客房单价 |
| insurance\_price | 保险费 | double | N | 保险费 |
| coupon\_amount | 优惠券/折扣 | double | N | 优惠券/折扣 |
| total\_price | 销售总价 | double | N | 销售总价 |
| relief\_price | 减免金额 | double | N | 减免金额 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service\_fee | 服务费 | double | N | 服务费 |
| total\_amount | 应收账单金额 | double | N | 应收账单金额 |
| red\_coupon | 红包券支付 | double | N | 红包券支付 |
| personal\_pay\_price | 员工支付 | double | N | 员工支付 |
```json
{
	"reason": " ",
	"cost_attribution_category": null,
	"cost_attribution_name": "北京分贝金服科技有限公司/测试部1级",
	"project_code": null,
	"is_need_trip_apply": null,
	"trip_apply_id": "",
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"is_need_during_apply": null,
	"during_apply_id": "",
	"hyper_gauge_info": null,
	"is_need_re_apply": null,
	"re_apply_id": null,
	"re_apply_reason": "",
	"custom_field1": null,
	"custom_field2": null,
	"custom_field3": null,
	"remark": null,
	"order_id": "5c7a382627986343bd5a9709",
	"source_order_id": "5c7a381827986343bd5a9704",
	"order_create_time": "2019-03-06T15:16:07.000+0800",
	"order_statue": null,
	"employee_name": "强仔",
	"employee_phone": "18310480640",
	"department_name": "嘟嘟搞测试",
	"department_hierarchy": "北京分贝金服科技有限公司/嘟嘟搞测试",
	"customer_name": "强六抝",
	"customer_phone": "11045678902",
	"customer_dept": "",
	"customer_hierarchy_dept": "",
	"check_in_date": "2019-04-23T00:00:00.000+0800",
	"check_out_date": "2019-04-24T00:00:00.000+0800",
	"check_in_city": "长兴县",
	"hotel_name": "测试酒店帝都",
	"number_of_nights": 1,
	"room_price": 200.00,
	"insurance_price": 0.00,
	"coupon_amount": 0.00,
	"total_price": null,
	"relief_price": null,
	"company_pay_price": -200.00,
	"service_fee": -20.00,
	"total_amount": -220.00,
	"red_coupon": null,
	"personal_pay_price": 0.00
}
```
bill\_detail\_train：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project\_code | 项目编号 | string | N | 项目编号 |
| is\_need\_trip\_apply | 是否需要行程审批 | string | N | 是否需要行程审批 |
| trip\_apply\_id | 行程审批单号 | string | N | 行程审批单号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| is\_need\_during\_apply | 是否需要订单审批 | string | N | 是否需要订单审批 |
| during\_apply\_id | 订单审批单号 | string | N | 订单审批单号 |
| hyper\_gauge\_info | 超规项 | string | N | 超规项 |
| is\_need\_re\_apply | 是否需要退改控制 | string | N | 是否需要退改控制 |
| re\_apply\_id | 退改审批单号 | string | N | 退改审批单号 |
| re\_apply\_reason | 退改理由 | string | N | 退改理由 |
| custom\_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom\_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom\_field3 | 自定义字段3 | string | N | 自定义字段3 |
| remark | 标签 | string | N | 标签 |
| id | 订单号 | string | N | 订单号 |
| bill_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 预订/退票日期 | string | N | 预订/退票日期,如2018-05-08T14:58:10.000+0800 |
| ticket_no | 取票号 | string | N | 取票号 |
| ticket_status | 订单状态 | string | N | 订单状态 |
| employee_name | 预订人 | string | N | 预订人 |
| employee_phone | 预定人手机号 | string | N | 预定人手机号 |
| department_name | 预订人直属部门 | string | N | 预订人直属部门 |
| department_hierarchy | 预订人层级部门 | string | N | 预订人层级部门 |
| customer_name | 旅客姓名 | string | N | 旅客姓名 |
| customer_phone | 乘客手机号 | string | N | 乘客手机号 |
| customer_dept | 乘客直属部门 | string | N | 乘客直属部门 |
| customer\_hierarchy\_dept | 乘客层级部门 | string | N | 乘客层级部门 |
| trip_type | 行程类型 | integer | N | 行程类型 |
| trip_info | 行程 | string | N | 行程 |
| train_no | 车次 | string | N | 车次 |
| train\_start\_date | 出发时间 | string | N | 出发时间,如2018-06-04T10:35:00.000+0800 |
| train\_end\_date | 到达时间 | string | N | 到达时间，如2018-06-04T10:49:00.000+0800 |
| seat_type | 坐席 | string | N | 坐席 |
| seat_location | 座位编号 | string | N | 座位编号 |
| ticket_price | 车票单价 | double | N | 车票单价 |
| insurance_price | 保险费 | double | N | 保险费 |
| change_fee | 改签费 | double | N | 改签费 |
| endorse\_diff\_fee | 改签差价 | double | N | 改签差价 |
| change\_ext\_fee | 改签手续费 | double | N | 改签手续费 |
| refund\_ext\_fee | 退票费 | double | N | 退票费 |
| grab_fee | 抢票费用 | double | N | 抢票费用 |
| coupon_amount | 优惠券/折扣 | double | N | 优惠券/折扣 |
| total_price | 销售总价 | double | N | 销售总价 |
| relief_price | 减免金额 | double | N | 减免金额 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
```json
{
	"reason": "开发市场 啦啦啦",
	"cost_attribution_category": null,
	"cost_attribution_name": "嘟嘟搞测试",
	"project_code": null,
	"is_need_trip_apply": null,
	"trip_apply_id": "",
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"is_need_during_apply": null,
	"during_apply_id": "",
	"hyper_gauge_info": null,
	"is_need_re_apply": null,
	"re_apply_id": null,
	"re_apply_reason": "",
	"custom_field1": "标题1-北京",
	"custom_field2": null,
	"custom_field3": null,
	"remark": null,
	"id": "5de7f7c023445f35267d745b",
	"bill_id": "5e0335b423445f6473c658c8",
	"order_create_time": "2018-05-08T14:58:10.000+0800",
	"ticket_no": "E464114250",
	"ticket_status": null,
	"employee_name": "强仔",
	"employee_phone": "18310480640",
	"department_name": "嘟嘟搞测试",
	"department_hierarchy": "嘟嘟搞测试/北京分贝金服科技有限公司/嘟嘟搞测试",
	"customer_name": "王健",
	"customer_phone": "15601247725",
	"customer_dept": "未设置",
	"customer_hierarchy_dept": "未设置",
	"trip_type": null,
	"trip_info": null,
	"train_no": "6063",
	"train_start_date": "2018-06-04T10:35:00.000+0800",
	"train_end_date": "2018-06-04T10:49:00.000+0800",
	"seat_type": "硬座",
	"seat_location": "03车厢,001号",
	"ticket_price": 1.00,
	"insurance_price": 0.00,
	"change_fee": null,
	"endorse_diff_fee": null,
	"change_ext_fee": null,
	"refund_ext_fee": 3.00,
	"grab_fee": 0.00,
	"coupon_amount": 0.00,
	"total_price": null,
	"relief_price": null,
	"company_pay_price": 1.00,
	"service_fee": 0.10,
	"total_amount": 1.10
}
```
bill\_detail\_taxi：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| ticket_status | 支付状态 | string | N | 支付状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| customer_name | 乘车人姓名 | string | N | 乘车人姓名 |
| customer_phone | 乘客手机号 | string | N | 乘客手机号 |
| customer_dept | 乘客部门 | string | N | 乘客部门 |
| customer\_hierarchy\_dept | 乘客层级部门 | string | N | 乘客层级部门 |
| trip_type | 行程类型 | integer | N | 行程类型 |
| begin\_charge\_time | 行程开始时间 | string | N | 行程开始时间,如2019-05-21T18:00:45.000+0800 |
| supplier_name | 用车服务商 | string | N | 用车服务商 |
| taxi_type | 用车类型 | string | N | 用车类型 |
| service_type | 服务类型 | string | N | 服务类型 |
| finish\_charge\_time | 支付时间 | string | N | 支付时间 |
| departure_name | 出发城市 | string | N | 出发城市 |
| from\_station\_name | 出发地 | string | N | 出发地 |
| arrival_name | 目的城市 | string | N | 目的城市 |
| to\_station\_name | 目的地 | string | N | 目的地 |
| insurance_name | 被保人姓名 | string | N | 被保人姓名 |
| insurance_price | 保险费 | double | N | 保险费 |
| taxi_price | 用车金额 | double | N | 用车金额 |
| tipping | 调度费 | double | N | 调度费 |
| coupon_amount | 优惠券/折扣 | double | N | 优惠券/折扣 |
| total_price | 销售总价 | double | N | 销售总价 |
| relief_price | 减免金额 | double | N | 减免金额 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| personal\_pay\_price | 员工支付 | double | N | 员工支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| during\_apply\_id | 用车申请单号 | string | N | 用车申请单号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
| deal_type | 标签 | string | N | 标签 |
```json
{
	"order_id": "5ce3cc4d23445f3fb8277cee",
	"order_create_time": "2019-05-21T18:00:45.000+0800",
	"ticket_status": null,
	"employee_name": "徐璞",
	"employee_phone": "15311412713",
	"department_name": "徐璞自个儿",
	"department_hierarchy": "北京分贝金服科技有限公司/徐璞自个儿",
	"customer_name": "徐璞",
	"customer_phone": "15311412713",
	"customer_dept": "徐璞自个儿",
	"customer_hierarchy_dept": "北京分贝金服科技有限公司/徐璞自个儿",
	"trip_type": null,
	"begin_charge_time": "2019-05-21T18:00:45.000+0800",
	"supplier_name": null,
	"taxi_type": "舒适型",
	"service_type": null,
	"finish_charge_time": "2019-05-21T19:50:51.000+0800",
	"departure_name": "光华路丙12号楼",
	"from_station_name": null,
	"arrival_name": "东大桥-地铁站",
	"to_station_name": null,
	"insurance_name": null,
	"insurance_price": 0.00,
	"taxi_price": 0.00,
	"tipping": 0.00,
	"coupon_amount": 0.00,
	"total_price": null,
	"relief_price": null,
	"company_pay_price": 0.00,
	"service_fee": 0.00,
	"total_amount": 0.00,
	"red_coupon": null,
	"personal_pay_price": 0.00,
	"reason": "加班 ",
	"cost_attribution_category": null,
	"cost_attribution_name": "徐璞自个儿",
	"project_code": null,
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"during_apply_id": "",
	"custom_field1": "任天堂-地滚蛋是否",
	"custom_field2": "1-45",
	"custom_field3": null,
	"deal_type": null
}
```
bill\_detail\_mall：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 支付状态 | string | N | 支付状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| finish_time | 完成时间 | string | N | 完成时间 |
| category_name | 产品类目 | string | N | 产品类目 |
| sku_detail | 明细 | string | N | 明细 |
| sku_price | 商品单价 | double | N | 商品单价 |
| sku_count | 商品数量 | double | N | 商品数量 |
| sku\_total\_amount | 商品总价 | double | N | 商品总价 |
| freight | 运费 | double | N | 运费 |
| coupon_amount | 优惠券/折扣 | double | N | 优惠券/折扣 |
| total_price | 销售总价 | double | N | 销售总价 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| is\_need\_during\_apply | 是否需要采购审批 | string | N | 是否需要采购审批号 |
| during\_apply\_id | 采购审批单号 | string | N | 采购审批单号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
```json
{
	"order_id": "5ce51c4027986357bd2bc58d",
	"order_create_time": "2019-05-22T17:54:08.000+0800",
	"order_status": null,
	"employee_name": "谷健波",
	"employee_phone": "13911381353",
	"department_name": "权限测试(勿删)",
	"department_hierarchy": "北京分贝金服科技有限公司",
	"finish_time": "2019-06-06T17:56:20.000+0800",
	"category_name": null,
	"sku_detail": null,
	"sku_price": null,
	"sku_count": null,
	"sku_total_amount": null,
	"freight": 0.00,
	"coupon_amount": 0.00,
	"total_price": null,
	"company_pay_price": 49.90,
	"service_fee": 0.50,
	"total_amount": 50.40,
	"red_coupon": null,
	"reason": "",
	"cost_attribution_category": null,
	"cost_attribution_name": "O落花流水",
	"project_code": null,
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"is_need_during_apply": null,
	"during_apply_id": "",
	"custom_field1": null,
	"custom_field2": null,
	"custom_field3": null
}
```
bill\_detail\_mei\_shi：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| contact_name | 用餐人 | string | N | 用餐人 |
| contact_phone | 用餐人手机号 | string | N | 用餐人手机号 |
| org_name | 用餐人部门 | string | N | 用餐人部门 |
| person_count | 用餐人数 | string | N | 用餐人数 |
| shop_city | 用餐城市 | string | N | 用餐城市 |
| main\_shop\_name | 主门店名 | string | N | 主门店名 |
| branch\_shop\_name | 分门店名 | string | N | 分门店名 |
| shop_addr | 门店地址 | string | N | 门店地址 |
| request_price | 本次企业最高支付 | double | N | 本次企业最高支付 |
| actual_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| is\_need\_during\_apply | 是否需要审批 | string | N | 是否需要审批 |
| during\_apply\_id | 超规用餐审批单号 | string | N | 超规用餐审批单号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
```json
{
	"order_id": "RMS201906251828465003473",
	"order_create_time": "2019-06-25T18:28:47.000+0800",
	"order_status": null,
	"contact_name": null,
	"contact_phone": null,
	"org_name": null,
	"person_count": null,
	"shop_city": null,
	"main_shop_name": null,
	"branch_shop_name": null,
	"shop_addr": null,
	"request_price": null,
	"actual_price": null,
	"service_fee": 0.00,
	"total_amount": 0.00,
	"red_coupon": 0.00,
	"reason": "-",
	"cost_attribution_category": null,
	"cost_attribution_name": "权限测试(勿删)-子部门2",
	"project_code": null,
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "其他",
	"is_need_during_apply": null,
	"during_apply_id": "",
	"custom_field1": "任天堂-加",
	"custom_field2": "1-A",
	"custom_field3": null
}
```
bill\_detail\_takeout：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| source\_order\_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| consignee_city | 用餐城市 | string | N | 用餐城市 |
| restaurant_name | 商家名称 | string | N | 商家名称 |
| total_price | 订单总价 | double | N | 订单总价 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| during\_apply\_id | 申请单号 | string | N | 申请单号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |

```json
{
	"order_id": "OTA201912261407316640232",
	"source_order_id": "OTA201912261407316640232",
	"order_create_time": "2019-12-26T14:07:32.000+0800",
	"order_statue": null,
	"employee_name": "小离",
	"employee_phone": "13261635233",
	"department_name": "温泉",
	"department_hierarchy": "红浪漫/温泉",
	"consignee_city": null,
	"restaurant_name": "Coco茶饮(尚都店)",
	"total_price": null,
	"company_pay_price": 11.00,
	"service_fee": 0.00,
	"total_amount": 11.00,
	"red_coupon": 0.00,
	"reason": "-测试",
	"cost_attribution_category": null,
	"cost_attribution_name": "温泉",
	"project_code": null,
	"is_hyper_gauge": null,
	"hyper_gauge_reason": "",
	"during_apply_id": "",
	"custom_field1": "老选项-1",
	"custom_field2": null,
	"custom_field3": null
}
```

bill\_detail\_dinner：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| source\_order\_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| shop_name | 商家名称 | double | N | 商家名称 |
| total_price | 订单总价 | double | N | 订单总价 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| personal\_pay\_price | 个人支付(含分贝币支付) | double | N | 个人支付(含分贝币支付) |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| is\_hyper\_gauge | 是否超规 | string | N | 是否超规 |
| hyper\_gauge\_info | 超规项 | string | N | 超规项 |
| hyper\_gauge\_reason | 超规理由 | string | N | 超规理由 |
| during\_apply\_id | 用餐申请单号 | string | N | 用餐申请单号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
```json
{
	"order_id": "5b90d20ee4b00ceb02eb328a",
	"source_order_id": "5b90d20ee4b00ceb02eb328a",
	"order_create_time": "2018-09-06T15:06:54.000+0800",
	"order_statue": null,
	"employee_name": "陈丞晨橙",
	"employee_phone": "15010817288",
	"department_name": "测试1部门",
	"department_hierarchy": "测试部1级-北京分贝金服科技有限公司",
	"shop_name": null,
	"total_price": null,
	"company_pay_price": 0.01,
	"service_fee": 0.00,
	"total_amount": 0.01,
	"red_coupon": null,
	"personal_pay_price": 0.00,
	"reason": "其他 天上星星飞呀飞",
	"cost_attribution_category": null,
	"cost_attribution_name": "测试1部门",
	"project_code": null,
	"is_hyper_gauge": null,
	"hyper_gauge_info": null,
	"hyper_gauge_reason": "突发事件 开会超时，刚完毕准备用餐，重点培养客户。急",
	"during_apply_id": "",
	"custom_field1": null,
	"custom_field2": null,
	"custom_field3": null
}
```

bill\_detail\_virtual\_card：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 交易时间 | string | N | 交易时间 |
| transaction_type | 交易类型 | string | N | 交易类型 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| shop_name | 商家名称 | string | N | 商家名称 |
| total_price | 交易金额 | double | N | 交易金额 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
```json
{
	"order_id": "OBK201910231931085490409",
	"order_create_time": "2019-10-23T19:31:09.000+0800",
	"transaction_type": null,
	"employee_name": "李唯",
	"employee_phone": "18211174628",
	"department_name": "1级部门",
	"department_hierarchy": "专业版Pro2 （李唯测试）Cto/1级部门",
	"shop_name": "中国银联CHINA UNIONPAY SIMULATOR",
	"total_price": null,
	"company_pay_price": 9.00,
	"service_fee": 0.00,
	"total_amount": 9.00
}
```
bill\_detail\_express：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| user_city | 下单城市 | string | N | 下单城市 |
| sender_name | 发件人姓名 | string | N | 发件人姓名 |
| sender_phone | 发件人手机号 | string | N | 发件人手机号 |
| sender_address | 发件地址 | string | N | 发件地址 |
| receiver_name | 收件人姓名 | string | N | 收件人姓名 |
| receiver_phone | 收件人手机号 | string | N | 收件人手机号 |
| receiver_address |收件地址  | string | N | 收件地址 |
| order\_tobill\_time | 完成时间 | string | N | 完成时间 |
| company\_pay\_price | 订单实付 | double | N | 订单实付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
```json
{
	"order_id": "OEX201912231137251633763",
	"order_create_time": "2019-12-23T11:37:25.000+0800",
	"order_status": null,
	"employee_name": "强仔",
	"employee_phone": "18310480640",
	"department_name": "哈哈测试",
	"department_hierarchy": "Q哈哈测试企业/哈哈测试",
	"user_city": "北京市",
	"sender_name": "貔貅强先生",
	"sender_phone": "18310480640",
	"sender_address": "北京市润诚中心211",
	"receiver_name": "强仔先生",
	"receiver_phone": "18310480640",
	"receiver_address": "北京市花园闸北里301号楼107",
	"order_tobill_time": "2019-12-25T10:37:18.000+0800",
	"company_pay_price": 14.00,
	"service_fee": 0.00,
	"total_amount": 14.00,
	"red_coupon": 16.00,
	"reason": "-测试",
	"cost_attribution_category": null,
	"cost_attribution_name": "哈哈测试",
	"project_code": null,
	"custom_field1": "1人生海-h",
	"custom_field2": "2爱情万-情",
	"custom_field3": "3晚上吃-k"
}
```
bill\_detail\_altman：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| id | 订单号 | string | N | 订单号 |
| bill_id | 主订单号 | string | N | 主订单号 |
| order\_create\_time | 预订时间 | string | N | 预订时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| employee_name | 预订人姓名 | string | N | 预订人姓名 |
| employee_phone | 预订人手机号 | string | N | 预订人手机号 |
| department_name | 预订人直属部门 | string | N | 预订人直属部门 |
| department_hierarchy | 预订人层级部门 | string | N | 预订人层级部门 |
| customer_name | 使用人姓名 | string | N | 使用人姓名 |
| customer_phone | 使用人手机号 | string | N | 使用人手机号 |
| customer_dept | 使用人直属部门 | string | N | 使用人直属部门 |
| customer\_hierarchy\_dept | 使用人层级部门 | string | N | 使用人层级部门 |
| order\_type\_classify\_name | 业务类别 | string | N | 业务类别 |
| order\_type\_name | 业务名称 | string | N | 业务名称 |
| order\_type\_desc | 业务描述 | string | N | 业务描述 |
| sku_detail | 商品明细 | string | N | 商品明细 |
| sku_price | 商品单价 | double | N | 商品单价 |
| sku_count | 商品数量 | integer | N | 商品数量 |
| sku\_total\_amount | 商品总价 | double | N | 商品总价 |
| total_price | 订单总价 | double | N | 订单总价 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
```json
{
	"id": "5df0af1823445f7c55a79ef8",
	"bill_id": "5dc6e29b23445f616d8c54f6",
	"order_create_time": "2019-12-11T16:38:42.000+0800",
	"order_status": null,
	"employee_name": "张磊",
	"employee_phone": "13311057293",
	"department_name": "洛彦驰骋（北京）科技有限公司",
	"department_hierarchy": "洛彦驰骋（北京）科技有限公司",
	"customer_name": null,
	"customer_phone": null,
	"customer_dept": null,
	"customer_hierarchy_dept": null,
	"order_type_classify_name": "任意付-充值",
	"order_type_name": "代垫话费",
	"order_type_desc": "13764893804",
	"sku_detail": null,
	"sku_price": null,
	"sku_count": null,
	"sku_total_amount": null,
	"total_price": null,
	"company_pay_price": 100.00,
	"service_fee": 10.00,
	"total_amount": 110.00,
	"red_coupon": null,
	"cost_attribution_category": null,
	"cost_attribution_name": "洛彦驰骋（北京）科技有限公司",
	"project_code": null
}
```
bill\_detail\_express\_delivery：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| order_id | 订单号 | string | N | 订单号 |
| order\_create\_time | 下单时间 | string | N | 下单时间 |
| order_status | 订单状态 | string | N | 订单状态 |
| employee_name | 下单人姓名 | string | N | 下单人姓名 |
| employee_phone | 下单人手机号 | string | N | 下单人手机号 |
| department_name | 下单人直属部门 | string | N | 下单人直属部门 |
| department_hierarchy | 下单人层级部门 | string | N | 下单人层级部门 |
| sender_name | 发件人姓名 | string | N | 发件人姓名 |
| sender_phone | 发件人手机号 | string | N | 发件人手机号 |
| sender\_address\_detail | 发件地址 | string | N | 发件地址 |
| receiver_name | 收件人姓名 | string | N | 收件人姓名 |
| receiver_phone | 收件人手机号 | string | N | 收件人手机号 |
| receiver\_address\_detail |收件地址  | string | N | 收件地址 |
| receive_time | 签收时间 | string | N | 签收时间 |
| total_price | 订单总价 | double | N | 订单总价 |
| company\_pay\_price | 企业支付 | double | N | 企业支付 |
| service_fee | 服务费 | double | N | 服务费 |
| total_amount | 应收总额 | double | N | 应收总额 |
| red_coupon | 红包券支付 | double | N | 红包券支付 |
| reason | 事由 | string | N | 事由 |
| cost\_attribution\_category | 费用归属类型 | string | N | 费用归属类型 |
| cost\_attribution\_name | 费用归属 | string | N | 费用归属 |
| project_code | 项目编号 | string | N | 项目编号 |
| custom_field1 | 自定义字段1 | string | N | 自定义字段1 |
| custom_field2 | 自定义字段2 | string | N | 自定义字段2 |
| custom_field3 | 自定义字段3 | string | N | 自定义字段3 |
```json
{
	"order_id": "OEX201911151714560296049",
	"order_create_time": "2019-11-15T17:14:56.000+0800",
	"order_status": null,
	"employee_name": "迪米特里",
	"employee_phone": "18010181062",
	"department_name": "you OK?",
	"department_hierarchy": "北京分贝金服科技有限公司/you OK?",
	"sender_name": "张无忌",
	"sender_phone": "18010131062",
	"sender_address_detail": "北京市朝阳区东大桥路12号润诚中心",
	"receiver_name": "迪米特里",
	"receiver_phone": "18010121062",
	"receiver_address_detail": "安徽省阜阳市颍州区颍河西路573号开源大厦",
	"receive_time": null,
	"total_price": null,
	"company_pay_price": 23.00,
	"service_fee": 2.30,
	"total_amount": 25.30,
	"red_coupon": 0.00,
	"reason": "-",
	"cost_attribution_category": null,
	"cost_attribution_name": "权限测试(勿删)",
	"project_code": null,
	"custom_field1": null,
	"custom_field2": null,
	"custom_field3": null
}
```