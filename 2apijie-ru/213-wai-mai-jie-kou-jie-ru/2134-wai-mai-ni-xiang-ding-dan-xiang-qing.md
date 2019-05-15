2.13.4 外卖逆向订单详情

####接口说明
- 1.**最新接口**
- 2.查询外卖逆向订单详情
  通过该接口可以查询企业使用分贝通产生的外卖逆向订单详情信息


请求方式|请求地址
----|---
POST|/open/api/takeaway/order/reverse/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|ggsdgerdgd
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.orderId|订单ID |string |Y|OTA201901191535464529173




请求示例：

```



"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{"orderId":"OTA201904291434309446349"
}



```


响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
orderId| 订单ID|string |Y|订单ID
refundOrderId| 逆向订单ID|string |Y|订单ID
createTime|下单时间 |string |Y|2019-04-29 14:34:31
refundStatus|订单状态| jsonobject| Y |订单状态信息
refundStatus.key|状态码| integer | Y |80
refundStatus.value|订单状态名称| string| Y |已完成
userInfo|用户信息 |jsonobject | Y |张三
paymentInfo |价格信息| jsonobject | Y |价格信息
refundPaymentInfo |逆向价格信息| jsonobject | Y |逆向价格信息
restaurantInfo|餐馆信息| jsonobject| Y |鹿角巷
saasInfo|管控信息|jsonobject|Y|管控信息
thirdCostAttributionId|第三方费用归属ID|string|Y|第三方费用归属ID
thirdCostAttributionType|第三方费用归属ID类型|integer|Y|1:部门,2:项目


```
{
    "request_id": "sWemhqM9wwoqOxEQnqpU",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "refundOrderId": "OTA201901191535464529173",
        "restaurantInfo": {
            "restaurantName": "谭志刚蜂鸟送test1",
            "restaurantTel": "15459598868"
        },
        "userInfo": {
            "username": "测试环境蛋"
        },
        "thirdCostAttributionId": "",
        "thirdCostAttributionType": 2,
        "orderId": "OTA201901191515525150173",
        "createTime": "2019-01-19 15:35:46",
        "consigneeInfo": {},
        "refundStatus": {
            "key": 91,
            "value": ""
        },
        "refundPaymentInfo": {
            "refundAmount": 3.68
        },
        "paymentInfo": {
            "totalPrice": 3.68
        },
        "saasInfo": {
            "costAttributionName": "吃蛋蛋",
            "costAttributionId": "5b87632023445f0538eabe92",
            "costAttributionCategory": "项目"
        }
    }
}
```


