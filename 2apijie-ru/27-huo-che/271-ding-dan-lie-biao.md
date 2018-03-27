根据企业app_id/app_key等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/api/train/order/list


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.state| 查询状态|integer |Y|0全部，1正处理，2已完成
data.name\_or\_phone|乘客/下单人姓名/手机号 |string |N|
data.name\_or\_phone\_type|乘客/下单人姓名/手机号类型 |string | N |
data.search\_category |搜索维度| integer | N |
data.order\_date\_begin |下单开始日期|string | N |yyyy-MM-dd
data.order\_date\_end|下单结束日期 |string | N |yyyy-MM-dd
data.page\_index |页码| integer |  N |1(默认值)
data.page\_size|每页显示条数| integer|  N |10(默认值)


请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
	  "state":0
	}
}


```


响应数据：



```

{
    "request_id": "WvhdVHK5vl4PbWtje0wW",
    "code": 0,
    "msg": "success",
    "data": {
        "results": [
            {
                "order_id": "5aab90ac279863130a86296f",
                "is_grab_order": false,
                "status": {
                    "key": 3101,
                    "value": "已取消"
                },
                "departure_time": 1523227380000,
                "arrival_time": 1523248740000,
                "train_code": "G101",
                "passenger_names": [
                    "滚滚滚"
                ],
                "from_station_name": "北京南",
                "to_station_name": "上海虹桥",
                "total_price": 563,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥563.00"
            },
            {
                "order_id": "5aab7b852798637d05ff3695",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522191180000,
                "arrival_time": 1522207440000,
                "train_code": "G89",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "北京西",
                "to_station_name": "西安北",
                "total_price": 515.5,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥515.50"
            },
            {
                "order_id": "5aa88e332798634316002512",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522128300000,
                "arrival_time": 1522132860000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥3.00"
            },
            {
                "order_id": "5aa889ee27986343160024d9",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1521586380000,
                "arrival_time": 1521602640000,
                "train_code": "G89",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "北京西",
                "to_station_name": "西安北",
                "total_price": 1627.5,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥1627.50"
            },
            {
                "order_id": "5aa8859527986343160024a7",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522128300000,
                "arrival_time": 1522132860000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥3.00"
            },
            {
                "order_id": "5aa7be342798634316002483",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522128300000,
                "arrival_time": 1522132860000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥3.00"
            },
            {
                "order_id": "5aa7bbd7279863431600247d",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1520944800000,
                "arrival_time": 1520987460000,
                "train_code": "Z19",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "北京西",
                "to_station_name": "西安",
                "total_price": 765.5,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥765.50"
            },
            {
                "order_id": "5aa78ee52798633851e1e4a1",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522128300000,
                "arrival_time": 1522132860000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥3.00"
            },
            {
                "order_id": "5aa78a2a2798633851e1e45c",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1522191180000,
                "arrival_time": 1522207440000,
                "train_code": "G89",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "北京西",
                "to_station_name": "西安北",
                "total_price": 515.5,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥515.50"
            },
            {
                "order_id": "5aa37c1927986357fd851324",
                "is_grab_order": false,
                "status": {
                    "key": 3102,
                    "value": "已关闭"
                },
                "departure_time": 1521619200000,
                "arrival_time": 1521640200000,
                "train_code": "G665",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "北京西",
                "to_station_name": "西安北",
                "total_price": 1627.5,
                "can_process": true,
                "is_external_order": 0,
                "total_price_str": "￥1627.50"
            }
        ],
        "total_count": 47
    }
}


```

