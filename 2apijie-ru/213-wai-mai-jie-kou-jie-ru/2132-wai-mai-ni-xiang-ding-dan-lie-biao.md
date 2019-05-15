2.13.2 外卖逆向订单列表

####接口说明
- 1.**最新接口**
- 2.查询外卖逆向订单列表
  通过该接口可以查询企业使用分贝通产生的外卖逆向订单信息
- 3.该接口一次最多可查询1000条数据，如订单数超过1000，则需要分页查询


请求方式|请求地址
----|---
POST|/open/api/takeaway/order/reverse/list


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|
data.company_id|公司ID |string |Y|99o8878pw902436748
data.page\_index |页码| integer | Y |1(默认值)
data.page\_size|每页显示条数| integer| Y |10(默认值)
data.create_time_begin|开始时间|string | N |2018-04-05
data.create_time_end |结束时间| string | N |2019-05-29
data.order_status|订单状态| integer| N |90，详细状态码参照外卖状态码



请求示例：

```



"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{"company_id":"5747fbc10f0e60e0709d8d7d","page_size":1000,"page_index":1,"create_time_begin":"2018-04-05","create_time_end":"2019-05-29","order_status":80}



```


响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
orderId| 订单ID|string |Y|OTA201901191515525150173
refundOrderId|逆向单订单号|string|Y|OTA201901191535464529173
createTime|下单时间 |string |Y|2019-04-29 14:34:31
orderStatus|订单状态| jsonobject| Y |订单状态信息
orderStatus.key|状态码| integer | Y |80
orderStatus.value|订单状态名称| string| Y |已完成
userInfo|用户信息 |jsonobject | Y |张三
paymentInfo |价格信息| jsonobject | Y |
restaurantInfo|餐馆信息| jsonobject| Y |鹿角巷




```
{
    "request_id": "8rXMu3GYcq7nBSDVjJzK",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "currentPage": 1,
        "pageSize": 1000,
        "totalPages": 1,
        "totalSize": 11,
        "content": [
            {
                "orderId": "OTA201901191515525150173",
                "refundOrderId": "OTA201901191535464529173",
                "createTime": "2019-01-19 15:35:46",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "测试环境",
                    "userPhone": "15601247725"
                },
                "paymentInfo": {
                    "companyTotalPay": 3.68
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181707245019190",
                "refundOrderId": "OTA201901182020341436390",
                "createTime": "2019-01-18 20:20:34",
                "orderStatus": {
                    "key": 90,
                    "value": "退款处理中"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 6.08
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181522113508073",
                "refundOrderId": "OTA201901181546041892873",
                "createTime": "2019-01-18 15:46:04",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "测试环境",
                    "userPhone": "15601247725"
                },
                "paymentInfo": {
                    "companyTotalPay": 3.68
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181155443961290",
                "refundOrderId": "OTA201901181510341413090",
                "createTime": "2019-01-18 15:10:34",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 2
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181124110454790",
                "refundOrderId": "OTA201901181440341448490",
                "createTime": "2019-01-18 14:40:34",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 2
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181116169670290",
                "refundOrderId": "OTA201901181430341148590",
                "createTime": "2019-01-18 14:30:34",
                "orderStatus": {
                    "key": 92,
                    "value": "退款完成"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 2
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901181043171774490",
                "refundOrderId": "OTA201901181355343675490",
                "createTime": "2019-01-18 13:55:34",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 11.58
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901161758236922632",
                "refundOrderId": "OTA201901162110342768332",
                "createTime": "2019-01-16 21:10:34",
                "orderStatus": {
                    "key": 91,
                    "value": "退款成功"
                },
                "userInfo": {
                    "username": "李南南",
                    "userPhone": "15122197573"
                },
                "paymentInfo": {
                    "companyTotalPay": 1
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901151943504685773",
                "refundOrderId": "OTA201901152006137058273",
                "createTime": "2019-01-15 20:06:14",
                "orderStatus": {
                    "key": 90,
                    "value": "退款处理中"
                },
                "userInfo": {
                    "username": "测试环境",
                    "userPhone": "15601247725"
                },
                "paymentInfo": {
                    "companyTotalPay": 3.5
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901151158374200990",
                "refundOrderId": "OTA201901151510343631090",
                "createTime": "2019-01-15 15:10:34",
                "orderStatus": {
                    "key": 90,
                    "value": "退款处理中"
                },
                "userInfo": {
                    "username": "强崽",
                    "userPhone": "18310480640"
                },
                "paymentInfo": {
                    "companyTotalPay": 6.28
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            },
            {
                "orderId": "OTA201901111924276465818",
                "refundOrderId": "OTA201901111947315652918",
                "createTime": "2019-01-11 19:47:32",
                "orderStatus": {
                    "key": 90,
                    "value": "退款处理中"
                },
                "userInfo": {
                    "username": "张天实",
                    "userPhone": "18500196797"
                },
                "paymentInfo": {
                    "companyTotalPay": 0.43
                },
                "restaurantInfo": {
                    "restaurantName": "谭志刚蜂鸟送test1"
                }
            }
        ]
    }
}
```


