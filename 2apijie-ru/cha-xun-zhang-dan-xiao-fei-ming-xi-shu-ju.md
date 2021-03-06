2.15.2 查询账单消费明细

#### 接口说明

* 1.**新接口**
* 2.根据账单单号查询账单消费明细数据

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
| data.order\_category | 业务类型 | integer | Y |  业务类型，3:用车;7:机票;11:酒店;15:火车;20:采购;30:口碑用餐;40:机票;50:外卖;60:美团点评;126:分贝通虚拟卡;131:快递;130:闪送;911:其他订单 |
| data.page\_index | 页码 | integer | N | 默认值1 |
|  data.page\_size | 条数 | integer | N | 默认值500,最大值500 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
"bill_no":"76161437520190710",
"type":7,
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
| list.company\_id | 企业id | string | Y | 企业id |
| list.bill\_name | 账单周期 | string | Y | 账单周期 |
| list.service\_rate | 服务费率 | double | Y | 服务费率 |
| list.verify\_email | 对账邮箱 | string | Y | 对账邮箱 |
| list.order\_category | 业务类型 | integer | Y | 业务类型，3:用车;7:机票;11:酒店;15:火车;20:采购;30:口碑用餐;40:机票;50:外卖;60:美团点评;126:分贝通虚拟卡;131:快递;130:闪送;911:其他订单 |
| list.invoice\_tax\_amount | 应付发票税点 | double | Y | 应付发票税点 |
| list.order\_price | 账单金额 | double | Y | 账单金额 |
| list.personal\_pay\_price | 员工支付金额 | double | Y | 员工支付金额 |
| list.red\_coupon | 红包支付金额 | double | Y | 红包支付金额 |
| list.adjustment\_amount | 本期调整金额 | double | Y | 本期调整金额 |
| list.total\_amount | 本期账单总额 | double | Y | 本期账单总额 |
| list.bank\_account\_name | 户名 | string | Y | 户名 |
| list.bank\_account | 银行账号 | string | Y | 银行账号 |
| list.open\_bank\_name | 开户行 | string | Y | 开户行 |
| list.remark | 打款备注 | string | Y | 打款备注 |

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
            "total_size": 4
        },
        "list": [
            {
                "company_id": "5d232e1b23445f75406ed26a",
                "bill_name": "20190610-20190709",
                "service_rate": 0.0000,
                "verify_email": "billing@fenbeitong.com",
                "order_category": 7,
                "invoice_tax_amount": 0.00,
                "order_price": 260.00,
                "personal_pay_price": 0.00,
                "red_coupon": 0.0,
                "adjustment_amount": 0.00,
                "total_amount": 260.00,
                "bank_account_name": "北京分贝通科技有限公司",
                "bank_account": "11050163720000000082",
                "open_bank_name": "涛皮儿",
                "remark": "账单测试企业III+分贝通消费款"
            },
            {
                "company_id": "5d232e1b23445f75406ed26a",
                "bill_name": "20190610-20190709",
                "service_rate": 0.0000,
                "verify_email": "billing@fenbeitong.com",
                "order_category": 7,
                "invoice_tax_amount": 0.00,
                "order_price": 260.00,
                "personal_pay_price": 0.00,
                "red_coupon": 0.0,
                "adjustment_amount": 0.00,
                "total_amount": 260.00,
                "bank_account_name": "北京分贝通科技有限公司",
                "bank_account": "11050163720000000082",
                "open_bank_name": "涛皮儿",
                "remark": "账单测试企业III+分贝通消费款"
            },
            {
                "company_id": "5d232e1b23445f75406ed26a",
                "bill_name": "20190610-20190709",
                "service_rate": 0.0000,
                "verify_email": "billing@fenbeitong.com",
                "order_category": 7,
                "invoice_tax_amount": 0.00,
                "order_price": 260.00,
                "personal_pay_price": 0.00,
                "red_coupon": 0.0,
                "adjustment_amount": 0.00,
                "total_amount": 260.00,
                "bank_account_name": "北京分贝通科技有限公司",
                "bank_account": "11050163720000000082",
                "open_bank_name": "涛皮儿",
                "remark": "账单测试企业III+分贝通消费款"
            },
            {
                "company_id": "5d232e1b23445f75406ed26a",
                "bill_name": "20190610-20190709",
                "service_rate": 0.0000,
                "verify_email": "billing@fenbeitong.com",
                "order_category": 7,
                "invoice_tax_amount": 0.00,
                "order_price": 260.00,
                "personal_pay_price": 0.00,
                "red_coupon": 0.0,
                "adjustment_amount": 0.00,
                "total_amount": 260.00,
                "bank_account_name": "北京分贝通科技有限公司",
                "bank_account": "11050163720000000082",
                "open_bank_name": "涛皮儿",
                "remark": "账单测试企业III+分贝通消费款"
            }
        ]
    },
    "request_id": "xVJUbmkMyAnCE38s"
}
```



