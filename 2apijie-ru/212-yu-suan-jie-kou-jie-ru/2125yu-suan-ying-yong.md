2.12.5.预算应用

####接口说明
- 1.**最新接口**
- 2.**预算应用**


请求方式|请求地址
----|---
POST|/open/api/third/budget/apply/save

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|lw8osdfj983uh4
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.budget_id|预算ID|integer |Y|预算ID
data.budget_type|业务类型|integer |Y|业务类型
data.item_list|人员ID，部门ID，项目ID|string |Y|必须为同类型
data.item_list_type|类型|string |Y|  1：分贝ID，2：第三方ID
data.id|预算ID|string |Y|预算ID

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
  "budget_id": 258,
  "item_list": [
    "5bffe02623445f013c8567b7"
  ],
"item_list_type":2
}
}



响应数据：

{
  "code": 0,
  "msg": "success",
  "data": {}
}

```


