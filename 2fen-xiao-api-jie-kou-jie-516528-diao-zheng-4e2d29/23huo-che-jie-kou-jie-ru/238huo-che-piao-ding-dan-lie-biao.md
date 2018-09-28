2.3.8 火车订单列表

####接口说明
- 1.**最新接口**
- 2.查询火车订单列表接口


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
data |请求数据| jsonobject |Y|
data.bdate|开始日期|string  |Y|2018-09-20
data.edate| 结束日期|string |Y|2018-09-20
data.orderno| 订单号|string |N|Jljsfo98w8eoiewnlsdo
data.status| 状态|string |Y|1
data.page| 首页|integer |Y|1
data.pagesize| 显示个数|integer |Y|20
data.supplier| 供应商|string |Y|分贝通
data.source| 订单来源|string |Y|A企业




请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":     {
                "orderno": "5bab55d22798633d548179cb",
            "status":1,
          "bdate":"2018-09-20",
          "edate":"2018-09-27",
                "supplier": "分贝通",
                "page":1,
                "pagesize":10,
                "source":"JUNWEI000001"
            }
}


```






```
{
    "request_id": "2pCUaTGMOqttib5ymAmS",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "data": [
            {
                "ContactMobile": "韩树起",
                "OrderStatus": 8,
                "OrderNumber": "5ba319762798633c0ae85162",
                "Id": 1,
                "ContactName": "韩树起",
                "TotalPayPrice": 162.5,
                "intrecordcount": 1
            }
        ],
        "supplier": "分贝通",
        "source": "JUNWEI000001",
        "successcode": "T"
    }
}


```

