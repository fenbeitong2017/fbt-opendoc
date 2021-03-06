2.15.4查询账单明细列表

#### 接口说明

* 1.**新接口**
* 2.查询账单明细列表

| 名称 | 描述 |
| --- | --- |
| 沙箱环境地址 | [https://open-plus-test.fenbeijinfu.com](https://open-plus-test.fenbeijinfu.com) |
| 生产环境地址 | [https://open-plus.fenbeitong.com](https://open-plus.fenbeitong.com) |
| HTTP方法 | POST |
| Content-Type | application/x-www-form-urlencoded |
| method | /openapi/func/approve/create |

字段

|  | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳 1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID |
| employee\_type | 用户类型 | string | Y | 类型，0为分贝用户，1为第三方用户 |
| data | 请求数据 | jsonobject | Y | 请求数据 |
| data.bill\_no | 账单编号 | string | Y | 账单编号 |
| data.order\_category | 业务线 | integer | Y | 业务线，3:用车;7:机票;11:酒店;15:火车;20:采购;30:口碑用餐;40:机票;50:外卖;60:美团点评;126:分贝通虚拟卡;131:快递;130:闪送;911:其他订单 |
| data.page\_index | 页码 | integer | N | 默认值1 |
|  data.page\_size | 条数 | integer | N | 默认值20 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
{"bill_no":"6666682400000000",
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
| list | 数据列表 | jsonarray | Y |  |
| list.order\_category | 业务线 | string | Y | 业务线 |
| list.order\_id | 订单号 | string | Y | 订单号 |
| list.source\_order\_id | 主订单号 | string | Y | 主订单号 |
| list.coupon\_amount | 优惠券/折扣 | double | Y | 优惠券/折扣 |
| list.order\_price | 销售总价/本次企业最高支付/订单实付 | double | Y | 销售总价/本次企业最高支付/订单实付 |
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
            "total_size": 2
        },
        "list": [
            {
                "order_category": "7",
                "order_id": "5bdd73cd2798636116481696",
                "source_order_id": "5bdd73cd2798636116481696",
                "coupon_amount": null,
                "order_price": 301.00,
                "service_fee_reduction": 0.00,
                "company_pay_price": 301.00,
                "service_fee": 0.00,
                "total_amount": 301.00,
                "red_coupon": null,
                "personal_pay_price": 0.00
            },
            {
                "order_category": "7",
                "order_id": "5bdd743d279863611648169b",
                "source_order_id": "5bdd73cd2798636116481696",
                "coupon_amount": null,
                "order_price": 20.00,
                "service_fee_reduction": 0.00,
                "company_pay_price": 20.00,
                "service_fee": 0.00,
                "total_amount": 20.00,
                "red_coupon": null,
                "personal_pay_price": 0.00
            }
        ]
    },
    "request_id": "fTHDZIb07KULcyFt"
}
```



