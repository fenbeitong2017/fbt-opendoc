2.15.1查询账单编号

#### 接口说明

* 1.**新接口**
* 2.按账单周期查询账单编号

| 名称 | 描述 |
| :--- | :--- |
| 沙箱环境地址 | [https://open-plus-test.fenbeijinfu.com](https://open-plus-test.fenbeijinfu.com) |
| 生产环境地址 | [https://open-plus.fenbeitong.com](https://open-plus.fenbeitong.com) |
| HTTP方法 | POST |
| Content-Type | application/x-www-form-urlencoded |
|  method |  /openapi/func/bill/queryBillNo |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳 1241243250000 |
| data | 请求数据 | jsonobject | Y | 请求数据 |
| data.start\_month | 账单开始时间 | string | Y | 账单开始年月，如201910 |
| data.end\_month | 账单结束时间 | string | Y | 账单结束年月，如201212 |
| data.page\_index | 页码 | integer | N | 默认值1 |
|  data.page\_size | 条数 | integer | N | 默认值20 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"data":{
"start_month":"201910",
"end_month":"201912",
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
| list.start\_month | 账单开始时间 | string | Y | 账单开始时间 |
| list.end\_month | 账单结束时间 | string | Y | 账单结束时间 |
| list.bill\_no | 账单编号 | string | Y | 账单编号 |

```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "page_info": {
            "page": 1,
            "page_size": 10,
            "current_page": 1,
            "total_pages": 1
        },
        "list": [
            {
                "company_id": "579f1a892528227973ddeb10",
                "start_month": "201911",
                "end_month": "201912",
                "bill_no": "0000020700000000"
            }
        ]
    },
    "request_id": "ljYiyFmHlj424PXW"
}
```



