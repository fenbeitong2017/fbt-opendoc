2.12.7.查询预算进度

#### 接口说明
- 1.**最新接口**
- 2.**查询预算进度**


请求方式|请求地址
----|---
POST|/open/api/third/budget/progress

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|lw8osdfj983uh4
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.budget_type|业务类型|integer |Y|业务类型
data.employee_id|人员ID|string |N|人员ID
data.cost_center_id|项目中心ID|string |N|  项目中心ID
data.department_id|部门ID|string |N|部门ID
data.company_id|公司ID|string |Y|公司ID
data.type|类型|integer |Y|  1:使用分贝ID，2使用第三方ID


请求示例：

```

{
"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":1,
"data":{
  "budget_type": 3,
  "cost_center_id": "35h3346563UDJKF8",
  "type":2,
  "company_id": "5747fbc10f0e60e0709d8d7d"
}
}


```

响应数据：

```
{
  "request_id": "z8t44CMWLIFpEBpvR1mg",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "exist": 1,
    "warn_percent2": 80,
    "budget_name": "第三方项目中心预算测试",
    "warn_percent1": 20,
    "manager_msg_warn": 1,
    "itemList": [
      {
        "typeList": [
          {
            "biz_type": 20,
            "sort": 1
          },
          {
            "biz_type": 7,
            "sort": 2
          }
        ],
        "amount_limit": 1000,
        "over_limit_control": 1,
        "amount_use": 0,
        "sort": 1,
        "over_color": false
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
        "amount_use": 0,
        "sort": 2,
        "over_color": false
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
            "biz_type": 3,
            "sort": 5
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
    "id": 258,
    "execution_cycle": 1,
    "budget_type": 3
  }
}


```














