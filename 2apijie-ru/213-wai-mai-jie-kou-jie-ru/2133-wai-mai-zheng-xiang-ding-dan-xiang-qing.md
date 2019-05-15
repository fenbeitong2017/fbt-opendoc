2.13.3 外卖正向订单详情

####接口说明
- 1.**最新接口**
- 2.查询外卖正向订单详情
  通过该接口可以查询企业使用分贝通产生的外卖正向订单详情信息


请求方式|请求地址
----|---
POST|/open/api/takeaway/order/forward/detail


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|ggsdgerdgd
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.orderId|订单ID |string |Y|OTA201904291434309446349




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
createTime|下单时间 |string |Y|2019-04-29 14:34:31
orderStatus|订单状态| jsonobject| Y |订单状态信息
orderStatus.key|状态码| integer | Y |80
orderStatus.value|订单状态名称| string| Y |已完成
userInfo|用户信息 |jsonobject | Y |张三
paymentInfo |价格信息| jsonobject | Y |价格信息
restaurantInfo|餐馆信息| jsonobject| Y |鹿角巷
consigneeInfo |收货人信息| jsonobject | Y | 收货人信息
bookingPersonInfo|预订人信息|jsonobject|Y|预订人信息
saasInfo|管控信息|jsonobject|Y|管控信息
remark|备注信息|jsonobject|Y|备注信息
exceedReason|超标理由|jsonobject|Y|超标理由
isExceed|是否超标|boolean|Y|true,false
thirdCostAttributionId|第三方费用归属ID|string|Y|第三方费用归属ID
thirdCostAttributionType|第三方费用归属ID类型|integer|Y|1:部门,2:项目


```
{
    "request_id": "48VOwpNm6JOPdEnX3Zqc",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "restaurantInfo": {
            "restaurantName": "鹿角巷TheAlley(SOHO尚都店)",
            "restaurantTel": "18601338060"
        },
        "thirdCostAttributionId": "third_privilege_test",
        "thirdCostAttributionType": 1,
        "orderId": "OTA201904291434309446349",
        "createTime": "2019-04-29 14:34:31",
        "consigneeInfo": {
            "consigneeName": "韩美美",
            "consigneePhone": "177****2750",
            "consigneeAddr": "润诚中心211"
        },
        "orderStatus": {
            "key": 80,
            "value": "已完成"
        },
        "paymentInfo": {
            "totalPrice": 13.4,
            "companyTotalPay": 13.4,
            "payTime": "2019-04-29 14:34:40"
        },
        "bookingPersonInfo": {
            "username": "迪米特里",
            "userPhone": "18010181062",
            "userUnitName": "北京分贝金服科技有限公司"
        },
        "saasInfo": {
            "costAttributionName": "权限测试(勿删)",
            "costAttributionId": "5bf2651123445f5335612351",
            "remark": {
                "remark": "其他",
                "remark_detail": "其他"
            },
            "isExceed": false,
            "exceedReason": {
                "exceed_reason": "",
                "exceed_reason_comment": ""
            },
            "costAttributionCategory": "部门"
        }
    }
}
```


