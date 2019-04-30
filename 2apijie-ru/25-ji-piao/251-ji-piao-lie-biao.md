2.5.1 机票订单列表

####接口说明
- 1.**最新接口**
- 2.查询机票订单列表接口
  通过该接口可以查询企业使用分贝通APP下的机票订单信息
- 3.该接口一次最多可查询1000条数据，如订单数超过1000，则需要分页查询


| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/flight/order/list |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| timestamp | 时间戳 | long | Y | 13位时间戳 |
|  | sign | 签名 | string | Y |
| access\_token | token | string | Y | 登录 token |
| employee\_id | 操作人id | string | Y | 操作人id,调用接口人 id |
| employee\_type | 用户类型 | string | Y | 0为分贝用户，1为第三方用户 |
| data | 请求数据 | jsonobject | Y |请求数据|
| data.name\_or\_phone | 乘机人/下单人姓名/手机 | string | N | 如 老王/13800 |
| data.name\_or\_phone\_type | 乘机人/下单人姓名/手机号类型 | string | N | （0:全部\(默认值\) 1:乘机人 2:下单人） |
| data.search\_category | 搜索维度 | integer | N | 1:企业 2:个人 |
| data.state | 查询状态 | integer | N | 0:全部\(默认值\) 1:处理中 2:已完成 |
| data.order\_date\_begin | 下单开始日期 | string | N | 格式为 yyyy-MM-dd  2017-01-01 |
| data.order\_date\_end | 下单结束日期 | string | N | 格式为 yyyy-MM-dd 2017-05-01 |
| data.starting_city | 出发城市 | string | N | 北京|
| data.arrived_city | 目的城市 | string | N |上海|
| data.page\_index | 页码 | integer | N | 1\(默认值\) |
| data.page\_size | 每页显示条数 | integer | N | 10\(默认值\) |

请求示例：

```
    "access_token":"5747fbc10f0e60e0709d8d722",
    "sign":"oihfnlyeofdh98",
    "timestamp":124124325,
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{
        "state":0,

    }

```

响应结果：

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| order\_id | 订单ID | string | Y | 5aaa513d279863768e83ff3b |
| create\_time | 创建时间 | string | Y | 2018-04-01 00:00:00 |
| total\_price | 订单价格 | double | Y | 负数为退票状态，退票返回金额 |
| passenger\_list | 乘客信息 | jsonarray | Y |  |
| status | 订单状态信息 | jsonobject | Y |  |
| status.key | 订单状态 | integer | Y | 详情参照状态码 |
| status.value | 订单详细信息 | string | Y | 订单详细信息 |
| segment\_info | 航班信息 | jsonobject | Y |  |
| segment\_info.flight\_no | 航班号 | string | Y | MU5126 |
| segment\_info.airline\_name | 航班名称 | string | Y | 上海航空 |
| segment\_info.starting\_code | 出发城市编码 | string | Y | PEK |
| segment\_info.starting\_city | 出发城市名称 | string | Y | 北京市 |
| segment\_info.destination\_code | 目的地城市编码 | string | Y | PVG |
| segment\_info.destination\_city | 目的地城市名称 | string | Y | 上海市 |
| segment\_info.departure\_timestamp | 出发时间 | integer | Y | 1522580110000 |
| segment\_info.arrived\_timestamp | 到达时间 | integer | Y | 1522587319000 |
| segment\_info.seat_msg | 仓位信息 | string | Y | 商务舱(头等舱),经济舱 |
| can\_process | 是否可以查看订单详情 | boolean | Y | 分为企业订单和个人名单，个人不能查看企业订单详情 |
| is\_external\_order | 是否外采订单 | integer | Y | 0:非外采,1:外采 |
| total\_price\_str | 订单金额字符串 | string | Y | "￥660.00" |
| employee_name | 下单人姓名 | string | Y | 张三|
| employee_id | 下单人id | string | Y | uejk8489u78437893uuhd|




```
{"request_id": "Ml4VL4moJ6VtKbG2vE83",

 "code": 0,

   "msg": "success",

  "data": {


    "results": [{
            "order_id": "5aba358627986345c41943b4",
            "remote_order_id": "9972987412701479279",
            "create_time": "2018-04-27 00:00:00",
            "total_price": 52,
            "passenger_list": ["强仔"],
            "status": {
                "key": 1900,
                "value": "有退改签"
            },
            "segment_info": {
                "flight_no": "212312",
                "airline_name": "南方航空",
                "starting_code": "HAK",
                "starting_city": "海口市",
                "destination_code": "PEK",
                "destination_city": "北京市",
                "seat_msg":"商务舱",
                "departure_timestamp": 1522152779328,
                "arrived_timestamp": 1522163570507
            },
            "can_process": false,
            "employee_name":"张三",
            "employee_id":"56768798765645",
            "is_external_order": 1,
            "total_price_str": "￥52.00"
        }, {
            "order_id": "5aaa513d279863768e83ff3b",
            "remote_order_id": "323",
            "create_time": "2018-04-01 00:00:00",
            "total_price": 100,
            "passenger_list": ["王健"],
            "status": {
                "key": 1821,
                "value": "改签成功"
            },
            "segment_info": {
                "flight_no": "123",
                "airline_name": "上海航空",
                "starting_code": "PEK",
                "starting_city": "北京市",
                "destination_code": "PVG",
                "seat_msg":"商务舱",
                "destination_city": "上海市",
                "departure_timestamp": 1522580110000,
                "arrived_timestamp": 1522587319000
            },
            "can_process": false,
            "employee_name":"张三",
            "employee_id":"56768798765645",
            "is_external_order": 1,
            "total_price_str": "￥100.00"
        }, {
            "order_id": "5abb5f3127986354622e6b21",
            "remote_order_id": "",
            "create_time": "2018-03-28 17:24:07",
            "total_price": 56,
            "passenger_list": ["韩美美"],
            "status": {
                "key": 1700,
                "value": "出票中"
            },
            "segment_info": {
                "flight_no": "CZ6105",
                "airline_name": "南方航空",
                "starting_code": "SHE",
                "starting_city": "沈阳",
                "seat_msg":"商务舱",
                "destination_code": "PEK",
                "destination_city": "北京",
                "departure_timestamp": 1524208800000,
                "arrived_timestamp": 1524215100000
            },
            "can_process": false,
            "employee_name":"张三",
            "employee_id":"56768798765645",
            "is_external_order": 0,
            "total_price_str": "￥56.00"
        }  
 }
}
```



