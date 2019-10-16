2.10.5 根据申请用车规则ID查询规则详情

####接口说明
- 1.**最新接口**


| 请求方式 | 请求地址 |
| --- | --- |
| POST |/open/api/approve/rule/info |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID|
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y |请求数据
| data.rule_id |  规则ID | integer | Y |998



请求示例：

```

    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{"rule_id":98}


```

响应结果：

```
{
    "request_id": "mawbjFlidyGmzkGs",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "id": 998,
        "name": "测试申请用车",
        "allowedTaxiTypeList": [//限制用车类型
            {
                "key": 600,
                "value": "经济型"
            },
            {
                "key": 50,
                "value": "出租车"
            },
            {
                "key": 900,
                "value": "优享型"
            },
            {
                "key": 100,
                "value": "舒适型"
            }
        ],
        "priceLimitFlag": 1,//用车费用限制（0:不限制 1:限制 2:员工填写）
        "priceLimit": 56,//单次
        "dayPriceLimit": 100,//单日
        "taxiSchedulingFee": 10,//调度费
        "allowSameCity": true,//同城限制
        "allowCalledForother": true,//为他人叫车
        "timesLimitFlag": 1,//用车次数限制（0:不限制 1:限制 2:员工填写）
        "timesLimit": 5,//次数
        "employeeCount": 2//应用员工数量
    }
}

```



