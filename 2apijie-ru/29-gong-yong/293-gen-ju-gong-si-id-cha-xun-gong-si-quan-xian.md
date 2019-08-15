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
       "airRuleList": [ //国内机票
      {
        "ruleId": "5a4356b623445f2a5bc94181",
        "ruleName": "国内机票测试01"
      },
      {
        "ruleId": "5a4dccc823445f54b36d30c0",
        "ruleName": "国内机票测试02"
      }
    ],
    "hotelRuleList": [ //酒店
      {
        "ruleId": "58c285065f281a76b49ed510",
        "ruleName": "酒店测试01"
      },
      {
        "ruleId": "58bcf97f5f281a2f8c782d3e",
        "ruleName": "酒店测试02"
      }
    ],
    "intlAirRuleList": [ //国际机票
      {
        "ruleId": "5b6168a923445f071a7321d2",
        "ruleName": "国际机票测试01"
      },
      {
        "ruleId": "5b31a69423445f615ee56cc2",
        "ruleName": "国际机票测试02"
      }
    ],
    "mallRuleList": [ //采购
      {
        "ruleId": "59e833e123445f0e751ff0b2",
        "ruleName": "采购测试01"
      },
      {
        "ruleId": "5926945e23445f3a42ee9e2e",
        "ruleName": "采购测试02"
      }
    ],
    "takeawayRuleList": [ //外卖
      {
        "ruleId": "125",
        "ruleName": "外卖测试01"
      },
      {
        "ruleId": "44",
        "ruleName": "外卖测试02"
      }
    ],
    "taxiRuleList": [ //用车
      {
        "ruleId": "373",
        "ruleName": "用车测试01"
      },
      {
        "ruleId": "417",
        "ruleName": "用车测试02"
      }
    ],
    "dinnerRuleList": [//用餐
            {
                "ruleId": "5d492a7123445f227a77b830",
                "ruleName": "用餐测试01"
            }
        ],
    "trainRuleList": [ //火车
      {
        "ruleId": "5c7f9fd323445f744405665a",
        "ruleName": "火车测试01"
      },
      {
        "ruleId": "5c82537723445f22e5c84bd9",
        "ruleName": "火车测试02"
      }
    ],
    "taxiApproveRuleList": [ //申请用车规则
      {
        "ruleId": "770",
        "ruleName": "申请用车测试01"
      },
      {
        "ruleId": "742",
        "ruleName": "申请用车测试02"
      }
    ]
    }
}




```



