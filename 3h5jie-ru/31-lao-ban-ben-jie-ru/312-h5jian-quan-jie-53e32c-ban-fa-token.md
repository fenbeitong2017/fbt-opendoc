##请求参数，以application/json传递


根据企业app_id/app_key等参数请求鉴权接口，返回请求token

请求方式|请求地址
----|---
POST|/open/web/auth/v1/dispense



字段|名称|类型|必填|描述
--|----|---|---|---
app\_id|企业ID|string|Y|企业ID
app\_key |企业key|string|Y|企业key
tp_user_id|第三方用户ID |string|Y|第三方系统中用户唯一身份标识（必填）, 是第三方本地用户信息的唯一标识，可以理解为第三方用户信息数据库表的id。此id为在同步组织架构信息中的third_employee_id字段
tp_mobile |手机号码|string|Y|18080179901

请求示例：

```
{
	"app_id":"5747fbc10f0e60e0709d8d722",
	"app_key":"59b74c1323445f2d54dd07922",
	"tp_user_id":"123456",
	"tp_mobile":"18612667433"
}
```
返回结果：

```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": "{
			"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxLU9TcFZjYnhkOXc0SlFhK0FwaVRDbU5MbjVCRnNv"
    }"
}

```
