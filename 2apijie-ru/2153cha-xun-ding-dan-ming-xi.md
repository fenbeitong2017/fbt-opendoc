2.15.2 查询账单明细

#### 接口说明

* 1.**新接口**
* 2.根据账单号和订单号查询账单明细数据

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
| data.page\_index | 页码 | integer | N | 默认值1 |
| data.page\_size | 条数 | integer | N | 默认值500，最大值500 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
"bill_no":"0000888820191225",
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
| list | 数据列表 | jsonarray | Y | 数据列表 |
| list.reason | 事由 | string | Y | 事由 |
| list.cost\_attribution\_category | 费用归属类型 | string | Y | 费用归属类型 |
| list.cost\_attribution\_name | 费用归属 | string | Y | 费用归属 |
| list.project\_code | 项目编号 | string | Y | 项目编号 |
| list.is\_need\_trip\_apply | 是否需要行程审批 | string | Y | 是否需要行程审批 |
| list.trip\_apply\_id | 行程审批单号 | string | Y | 行程审批单号 |
| list.is\_hyper\_gauge | 是否超规 | string | Y | 是否超规 |
| list.hyper\_gauge\_reason | 超规理由 | string | Y | 超规理由 |
| list.is\_need\_during\_apply | 是否需要订单审批 | string | Y | 是否需要订单审批 |
| list.during\_apply\_id | 订单审批单号 | string | Y | 订单审批单号 |
| list.hyper\_gauge\_info | 超规项 | string | Y | 超规项 |
| list.is\_need\_re\_apply | 是否需要退改控制 | string | Y | 是否需要退改控制 |
| list.re\_apply\_id | 退改审批单号 | string | Y | 退改审批单号 |
| list.re\_apply\_reason | 退改理由 | string | Y | 退改理由 |
| list.custom\_field1 | 自定义字段1 | string | Y | 自定义字段1 |
| list.custom\_field2 | 自定义字段2 | string | Y | 自定义字段2 |
| list.custom\_field3 | 自定义字段3 | string | Y | 自定义字段3 |
| list.remark | 标签 | string | Y | 标签 |
| 业务线 | integer | Y | 业务线，3:用车;7:机票;11:酒店;15:火车;20:采购;30:口碑用餐;40:机票;50:外卖;60:美团点评;126:分贝通虚拟卡;131:快递;130:闪送;911:其他订单 | Y |
| list.order\_id | 订单号 | string | Y | 订单号 |
| list.source\_order\_id | 主订单号 | string | Y | 主订单号 |
| list.order\_create\_time | 预订/退票/下单日期时间 | date | Y | 预订/退票/下单日期时间 |
| list.ticket\_no | 票号/取票号 | string | Y | 票号/取票号 |
| list.order\_category\_type | 机票分类/用车服务商/其他订单业务类别 | string | Y | 机票分类/用车服务商/其他订单业务类别 |
| list.ticket\_status | 机票/订单/支付状态 | string | Y | 机票/订单/支付状态 |
| list.employee\_name | 预订/下单/用餐人 | string | Y | 预订/下单/用餐人 |
| list.employee\_phone | 预订/下单/用餐人手机号 | string | Y | 预订/下单/用餐人手机号 |
| list.department\_name | 预定/下单/用餐人直属部门 | string | Y | 预定/下单/用餐人直属部门 |
| list.department\_hierarchy | 预订/下单人层级部门 | string | Y | 预订/下单人层级部门 |
| list.customer\_name | 旅客/乘车人/使用人/发件人/交易人姓名 | string | Y | 旅客/乘车人/使用人/发件人/交易人姓名 |
| list.customer\_phone | 旅客/乘车人/发件人手机号/使用人/交易人手机号 | string | Y | 旅客/乘车人/发件人手机号/使用人/交易人手机号 |
| list.customer\_dept | 旅客直属部门/乘车人部门/使用人直属部门 | string | Y | 旅客直属部门/乘车人部门/使用人直属部门 |
| list.customer\_hierarchy\_dept | 旅客/乘车人层级部门/使用人层级部门 | string | Y | 旅客/乘车人层级部门/使用人层级部门 |
| list.trip\_type | 行程/用车类型/主门店/商家名称 | string | Y | 行程/用车类型/主门店/商家名称 |
| list.trip\_info | 火车/机票行程/分门店名/被保人/收件人姓名 | string | Y | 火车/机票行程/分门店名/被保人/收件人姓名 |
| list.flight\_no | 航班号/车次/服务类型/门店地址/收件人手机号 | string | Y | 航班号/车次/服务类型/门店地址/收件人手机号 |
| list.departure\_name | 出发城市/下单城市 | string | Y | 出发城市/下单城市 |
| list.from\_station\_name | 出发车站/出发地/发件地址 | string | Y | 出发车站/出发地/发件地址 |
| list.arrival\_name | 到达城市/入住城市/目的城市/用餐城市 | string | Y | 到达城市/入住城市/目的城市/用餐城市 |
| list.to\_station\_name | 到达车站/目的地/门店地址/收件地址 | string | Y | 到达车站/目的地/门店地址/收件地址 |
| list.departure\_time | 起飞/入住/出发/行程开始时间 | string | Y | 起飞/入住/出发/行程开始时间 |
| list.back\_departure\_time | 到达/离店/支付/完成时间 | string | Y | 到达/离店/支付/完成时间 |
| list.discount | 机票折扣 | double | Y | 机票折扣 |
| list.sale\_type | 坐席/产品类目/业务描述 | string | Y | 坐席/产品类目/业务描述 |
| list.seal\_location | 座位编号/明细/商品明细 | string | Y | 座位编号/明细/商品明细 |
| list.number\_of\_nights | 间夜数/商品数量/用餐人数 | integer | Y | 间夜数/商品数量/用餐人数 |
| list.sale\_price | 票销售价/平均客房单价/车票单价/商品单价 | double | Y | 票销售价/平均客房单价/车票单价/商品单价 |
| list.airport\_fee | 机场建设费 | double | Y | 机场建设费 |
| list.fuel\_fee | 燃油费 | double | Y | 燃油费 |
| list.taxes | 税费 | double | Y | 税费 |
| list.taxi\_price | 用车金额/采购商品总价 | double | Y | 用车金额/采购商品总价 |
| list.insurance\_price | 保险费/运费 | double | Y | 保险费/运费 |
| list.endorse\_diff\_fee | 改签差价 | double | Y | 改签差价 |
| list.change\_fee | 改签费/改签手续费 | double | Y | 改签费/改签手续费 |
| list.upgrate\_fee | 升舱费/火车抢票费/用车调度费 | double | Y | 升舱费/火车抢票费/用车调度费 |
| list.refund\_ext\_fee | 退票费 | double | Y | 退票费 |
| list.coupon\_amount | 优惠券/折扣 | double | Y | 优惠券/折扣 |
| list.total\_price | 销售总价/本次企业最高支付/订单实付 | double | Y | 销售总价/本次企业最高支付/订单实付 |
| list.service\_fee\_reduction | 减免金额 | double | Y | 减免金额 |
| list.company\_pay\_price | 企业支付 | double | Y | 企业支付 |
| list.service\_fee | 服务费 | double | Y | 服务费 |
| list.total\_amount | 应收总额 | double | Y | 应收总额 |
| list.red\_coupon | 红包券支付 | double | Y | 红包券支付 |
| list.personal\_pay\_price | 员工支付/个人支付\(含分贝币支付\) | double | Y | 员工支付/个人支付\(含分贝币支付\) |

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
        "list": [
            {
                "reason": "凤凰财经同学审批用车A",
                "cost_attribution_category": "1",
                "cost_attribution_name": "工部",
                "project_code": null,
                "is_need_trip_apply": "1",
                "trip_apply_id": "5dca638723445f7156aa2f27",
                "is_hyper_gauge": "2",
                "hyper_gauge_reason": "",
                "is_need_during_apply": "2",
                "during_apply_id": "",
                "hyper_gauge_info": null,
                "is_need_re_apply": null,
                "re_apply_id": null,
                "re_apply_reason": null,
                "custom_field1": null,
                "custom_field2": null,
                "custom_field3": null,
                "remark": null,
                "order_category": 3,
                "order_id": "5dca661c23445f6229664eb9",
                "source_order_id": "5dca661c23445f6229664eb9",
                "order_create_time": null,
                "ticket_no": null,
                "order_category_type": "1",
                "ticket_status": "700",
                "employee_name": "张三",
                "employee_phone": "17301329703",
                "department_name": "工部",
                "department_hierarchy": "北京分贝金服科技有限公司/尚书省/工部",
                "customer_name": "陈丞",
                "customer_phone": "15010817288",
                "customer_dept": "礼部",
                "customer_hierarchy_dept": "北京分贝金服科技有限公司/尚书省/礼部",
                "trip_type": null,
                "trip_info": null,
                "flight_no": null,
                "departure_name": "东大桥路",
                "from_station_name": null,
                "arrival_name": "银河SOHO",
                "to_station_name": null,
                "departure_time": null,
                "back_departure_time": null,
                "discount": null,
                "sale_type": null,
                "seal_location": null,
                "number_of_nights": null,
                "sale_price": null,
                "airport_fee": null,
                "fuel_fee": null,
                "taxes": null,
                "taxi_price": 8.00,
                "insurance_price": 0.00,
                "endorse_diff_fee": null,
                "change_fee": null,
                "upgrate_fee": null,
                "refund_ext_fee": null,
                "coupon_amount": -2.00,
                "total_price": null,
                "service_fee_reduction": 0.00,
                "company_pay_price": null,
                "service_fee": 0.00,
                "total_amount": 0.00,
                "red_coupon": 0.00,
                "personal_pay_price": 0.00
            }
        ]
    },
    "request_id": "CjPa2St1ebyOUtOC"
}
```



