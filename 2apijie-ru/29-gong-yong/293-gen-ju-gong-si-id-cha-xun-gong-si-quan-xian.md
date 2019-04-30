2.9.4 根据公司ID查询公司规则
####接口说明
- 1.**最新接口**
- 2.根据公司ID查询公司相应的规则，在同步人员信息的时，把相应的规则ID取出，然后进行字段赋值



| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/third/company/rule |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id |
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y |请求数据  {}


请求示例：

```



    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{            
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
                "ruleName": "高管机票规则"
            }
        ],
        "dinnerRuleList": [
            {
                "ruleId": "59f2ad6923445f260057c464",
                "ruleName": "商务宴请规则"
            },
            {
                "ruleId": "59f08d0923445f4d896f53f5",
                "ruleName": "部门团建规则"
            }
        ],
        "hotelRuleList": [
            {
                "ruleId": "58e614da5f281a15c9e08d2e",
                "ruleName": "一线城市规则"
            },
            {
                "ruleId": "58bcf97f5f281a2f8c782d3e",
                "ruleName": "高管酒店预订规则"
            }
        ],
        "mallRuleList": [
            {
                "ruleId": "59e833e123445f0e751ff0b2",
                "ruleName": "集中采购规则"
            },
            {
                "ruleId": "5926945e23445f3a42ee9e2e",
                "ruleName": "公司设备采购规则"
            }
        ],
        "taxiRuleList": [
            {
                "ruleId": "145",
                "ruleName": "加班打车规则"
            },
            {
                "ruleId": "176",
                "ruleName": "为客户打车规则"
            }
        ],
        "trainRuleList": [
            {
                "ruleId": "57e0e6b7dec24c54de0b5484",
                "ruleName": "高管出差规则"
            },
            {
                "ruleId": "58c268565f281a67a8324d82",
                "ruleName": "普通员工出差规则"
            }
        ]
    }
}




```



