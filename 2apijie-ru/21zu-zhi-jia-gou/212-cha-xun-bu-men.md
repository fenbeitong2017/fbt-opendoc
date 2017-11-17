请求方式|请求地址
----|---
POST|/open/api/org/departments/detail

请求参数
字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.org_ unit_id|部门ID |string |Y|部门ID
 
请求示例

```
{ "access_token": "xxx.xxx.xxx",  "timestamp": 123456789,  "employee_id":12345678,  "sign": "jifejfwojelajflejf",  "data":  {   "org_unit_id":"综合部" }
}
```
返回结果
```
{   "request_id": "LaZNvBntsBD20nJ7ekgn",   "code": 0,   "msg": "success",   "data": {           }}
```
