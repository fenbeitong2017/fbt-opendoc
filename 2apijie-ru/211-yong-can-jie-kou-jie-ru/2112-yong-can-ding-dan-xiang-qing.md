请求方式|请求地址
----|---
POST|/open/api/dinner/order/list


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonobject |Y|
data.order_id| 订单ID|string |Y|



请求示例：

```


{
"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":1,
"data":{
"order_id":"784396yhf832d78f23y8fh932"
}
}


```


响应数据：




```





{
    "request_id": "oYUSfi8Tk22zumb3AjIB",
    "code": 0,
    "msg": "success",
    "data": {
        "branch_shop_name": "5号便当(光华路soho店)",//门店名称
        "reason": "市场拓展",//用餐理由
        "status_tip": "",
        "contact_phone": "18601016943",//联系人手机号
        "logo_url": null,//门店图片地址
        "shop_addr": "光华路22号1层127",//地址
        "can_process": false, //是否可编辑
        "cost_attribution": "58c21a365f281a7e6f810ae6",//费用归属ID
        "voucher_start_time": "2018-04-13 00:00:00",//营业开始时间
        "request_price_str": "￥0.01",//申请额度字符串
        "total_price_str": "￥0.00", //订单销售金额字符串
        "attribution_name": "X部门",//部门名称
        "voucher_suit_time": [//企业券适用时段
            {
                "date": "2018-04-13",//日期
                "time": "00:00 - 次日00:00" // 时段
            }
        ],
        "product_id": "5ad09d39e4b0c3e0b0a70cea",
        "actual_price_str": "￥0.00",//支付券销售金额字符串
        "shop_mobile_no": "010-57265505",
        "person_count": 1,
        "ticket_price_str": "￥0.01", //企业支付券面额，字符串
        "imgs": [],
        "attribution_type": "部门",//费用归属类型
        "contact_name": "刘维中",
        "voucher_end_time": "2018-04-14 00:00:00",
        "create_time": "2018-04-13 20:06:17",
        "total_price": 0,
        "actual_price": 0,
        "ticket_price": 0.01,
        "shop_id": "278445",
        "request_price": 0.01,//申请额度 (企业最高支付)
        "employee_id": "58a3bf5c5f281a490f37918a",
        "koufu_shop_id": "2016060400077000000015863981",
        "order_id": "5ad09d39e4b0c3e0b0a70ce9",
        "status": {//订单状态
            "value": "已关闭",
            "key": 4710
        }
    }
}
```


