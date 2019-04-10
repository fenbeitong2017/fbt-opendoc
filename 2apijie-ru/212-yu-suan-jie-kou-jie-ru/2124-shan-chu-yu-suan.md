2.12.4  删除预算

####接口说明
- 1.**最新接口**
- 2.**删除预算**


请求方式|请求地址
----|---
POST|/open/api/third/budget/delete

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|lw8osdfj983uh4
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
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
  "id": "09780089767567657687898"
 }
}



响应数据：

{
  "code": 0,
  "msg": "success",
  "data": {}
}

```














