
2.2.9 删除员工（支持批量删除）

请求方式|请求地址
----|---
POST|/open/api/third/employees/delete


请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee_ids| 三方员工id|jsonarray|Y| 三方员工id 
 

 
 请求示例
 
 
 ``` 


{
 "access_token": "xxx.xxx.xxx",
 "timestamp":123456789,
 "employee_id":12345678,
 "sign": "jifejfwojelajflejf",
 "data":{
	"employee_ids":["12345678","dfghtuy6754"]   
```

返回结果
```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```
