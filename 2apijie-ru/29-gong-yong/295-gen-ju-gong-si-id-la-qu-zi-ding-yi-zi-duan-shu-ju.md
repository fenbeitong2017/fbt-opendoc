2.9.5 根据公司ID拉取公司自定义字段
####接口说明
- 1.**最新接口**
- 2.根据公司ID拉取公司下单时需要的自定义字段内容



| 请求方式 | 请求地址 |
| --- | --- |
| POST | |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id |
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y |请求数据
| data.company_id |公司ID| string | Y |
| data.business |业务场景| string | Y |
| data.third_employee_id |员工ID| string | N |









请求示例：

```


{
    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":1,
    "data":{            
     }
}


```

响应结果：

```



{
    "request_id": "M5NrqkfNe4ifAni4dLlC",
    "code": 0,
    "msg": "success",
    "data": {
       "airRuleList": [
            {
                "ruleId": "5926531f2798635d37d803a6",
                "ruleName": "机票折扣"
            },
            {
                "ruleId": "58c15ae25f281a2893a3c1a6",
                "ruleName": "测试陈引"
            }
        ],
        "dinnerRuleList": [
            {
                "ruleId": "59f2ad6923445f260057c464",
                "ruleName": "345"
            },
            {
                "ruleId": "59f08d0923445f4d896f53f5",
                "ruleName": "rr00"
            }
        ],
        "hotelRuleList": [
            {
                "ruleId": "58e614da5f281a15c9e08d2e",
                "ruleName": "测试10"
            },
            {
                "ruleId": "58bcf97f5f281a2f8c782d3e",
                "ruleName": "wangchao"
            }
        ],
        "mallRuleList": [
            {
                "ruleId": "59e833e123445f0e751ff0b2",
                "ruleName": "看见了"
            },
            {
                "ruleId": "5926945e23445f3a42ee9e2e",
                "ruleName": "sdfsdf"
            }
        ],
        "taxiRuleList": [
            {
                "ruleId": "145",
                "ruleName": "ERIC"
            },
            {
                "ruleId": "176",
                "ruleName": "bwh测试"
            }
        ],
        "trainRuleList": [
            {
                "ruleId": "57e0e6b7dec24c54de0b5484",
                "ruleName": "机票只允许订经济舱"
            },
            {
                "ruleId": "58c268565f281a67a8324d82",
                "ruleName": "大饼"
            }
        ]
    }
}




```



