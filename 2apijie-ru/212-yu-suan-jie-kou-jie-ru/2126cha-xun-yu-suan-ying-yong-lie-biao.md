2.12.6.查询预算应用列表

####接口说明
- 1.**最新接口**
- 2.**查询预算应用列表**


请求方式|请求地址
----|---
POST|/open/api/third/budget/list

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|lw8osdfj983uh4
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.budget_type|业务类型|integer |Y|业务类型

请求示例：

```


{
"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":1,
"data":{
  "budget_type": 1,
  "page_index": 1,
  "page_size": 20
}
}



响应数据：
{
  "request_id": "QmCULz7FjVAyCPJ1uBOX",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "total": 68,
    "data": [
      {
        "warn_percent2": 60,
        "budget_thrid_id": "09876754679878657687898",
        "budget_name": "预算测试2",
        "warn_percent1": 30,
        "company_id": "5747fbc10f0e60e0709d8d7d",
        "budget_use_count": 1,
        "no_budget_limit": "国际机票+酒店+火车票+外卖+采购",
        "manager_msg_warn": 0,
        "itemList": [
          {
            "typeList": [
              {
                "biz_type": 3,
                "sort": 1
              },
              {
                "biz_type": 7,
                "sort": 2
              }
            ],
            "amount_limit": 2000,
            "over_limit_control": 1,
            "sort": 1
          },
          {
            "typeList": [
              {
                "biz_type": 7,
                "sort": 1
              },
              {
                "biz_type": 30,
                "sort": 2
              }
            ],
            "amount_limit": 5000,
            "over_limit_control": 1,
            "sort": 2
          },
          {
            "typeList": [
              {
                "biz_type": 11,
                "sort": 3
              },
              {
                "biz_type": 15,
                "sort": 4
              },
              {
                "biz_type": 20,
                "sort": 8
              },
              {
                "biz_type": 40,
                "sort": 2
              },
              {
                "biz_type": 50,
                "sort": 7
              }
            ],
            "amount_limit": -1,
            "over_limit_control": 1,
            "amount_use": 0,
            "sort": 100,
            "over_color": false
          }
        ],
        "id": 256,
        "execution_cycle": 1,
        "budget_type": 1
      },
      {
        "warn_percent2": 60,
        "budget_thrid_id": "9812672342436567u75674356786",
        "budget_name": "预算测试1",
        "warn_percent1": 30,
        "company_id": "5747fbc10f0e60e0709d8d7d",
        "budget_use_count": 1,
        "no_budget_limit": "国际机票+酒店+火车票+外卖+采购",
        "manager_msg_warn": 0,
        "itemList": [
          {
            "typeList": [
              {
                "biz_type": 3,
                "sort": 1
              },
              {
                "biz_type": 7,
                "sort": 2
              }
            ],
            "amount_limit": 1000,
            "over_limit_control": 1,
            "sort": 1
          },
          {
            "typeList": [
              {
                "biz_type": 7,
                "sort": 1
              },
              {
                "biz_type": 30,
                "sort": 2
              }
            ],
            "amount_limit": 4000,
            "over_limit_control": 1,
            "sort": 2
          },
          {
            "typeList": [
              {
                "biz_type": 11,
                "sort": 3
              },
              {
                "biz_type": 15,
                "sort": 4
              },
              {
                "biz_type": 20,
                "sort": 8
              },
              {
                "biz_type": 40,
                "sort": 2
              },
              {
                "biz_type": 50,
                "sort": 7
              }
            ],
            "amount_limit": -1,
            "over_limit_control": 1,
            "amount_use": 0,
            "sort": 100,
            "over_color": false
          }
        ],
        "id": 255,
        "execution_cycle": 1,
        "budget_type": 1
      },
      {
        "warn_percent2": 80,
        "budget_name": "LNN-外卖个人预算-勿删",
        "warn_percent1": 50,
        "company_id": "5747fbc10f0e60e0709d8d7d",
        "budget_use_count": 1,
        "no_budget_limit": "国内机票+国际机票+酒店+火车票+用车+用餐+采购",
        "manager_msg_warn": 0,
        "itemList": [
          {
            "typeList": [
              {
                "biz_type": 50,
                "sort": 7
              }
            ],
            "amount_limit": 1000,
            "over_limit_control": 1,
            "sort": 1
          },
          {
            "typeList": [
              {
                "biz_type": 7,
                "sort": 1
              },
              {
                "biz_type": 11,
                "sort": 3
              },
              {
                "biz_type": 15,
                "sort": 4
              },
              {
                "biz_type": 3,
                "sort": 5
              },
              {
                "biz_type": 20,
                "sort": 8
              },
              {
                "biz_type": 30,
                "sort": 6
              },
              {
                "biz_type": 40,
                "sort": 2
              }
            ],
            "amount_limit": -1,
            "over_limit_control": 1,
            "sort": 100,
            "amount_use": 0,
            "over_color": false
          }
        ],
        "id": 240,
        "execution_cycle": 1,
        "budget_type": 1
      },
      {
        "warn_percent2": -1,
        "budget_name": "哦哦",
        "warn_percent1": -1,
        "company_id": "5747fbc10f0e60e0709d8d7d",
        "budget_use_count": 0,
        "no_budget_limit": "国际机票",
        "manager_msg_warn": 0,
        "itemList": [
          {
            "typeList": [
              {
                "biz_type": 3,
                "sort": 5
              }
            ],
            "amount_limit": 100,
            "over_limit_control": 2,
            "sort": 1
          },
          {
            "typeList": [
              {
                "biz_type": 30,
                "sort": 6
              }
            ],
            "amount_limit": 100,
            "over_limit_control": 2,
            "sort": 2
          },
          {
            "typeList": [
              {
                "biz_type": 20,
                "sort": 7
              }
            ],
            "amount_limit": 100,
            "over_limit_control": 2,
            "sort": 3
          },
          {
            "typeList": [
              {
                "biz_type": 7,
                "sort": 1
              }
            ],
            "amount_limit": 800,
            "over_limit_control": 1,
            "sort": 4
          },
          {
            "typeList": [
              {
                "biz_type": 11,
                "sort": 3
              },
              {
                "biz_type": 15,
                "sort": 4
              }
            ],
            "amount_limit": 800,
            "over_limit_control": 1,
            "sort": 5
          },
          {
            "typeList": [
              {
                "biz_type": 50,
                "sort": 7
              }
            ],
            "amount_limit": 300,
            "over_limit_control": 1,
            "sort": 6
          },
          {
            "typeList": [
              {
                "biz_type": 40,
                "sort": 2
              }
            ],
            "amount_limit": -1,
            "over_limit_control": 1,
            "amount_use": 0,
            "sort": 100,
            "over_color": false
          }
        ],
        "id": 203,
        "execution_cycle": 2,
        "budget_type": 1
      }
    ],
    "page_index": 1,
    "page_size": 20
  }
}


```














