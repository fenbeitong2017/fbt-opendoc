根据企业ID删除部门请求方式|请求地址
----|---
POST|/open/api/org/departments/delete

请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data部门id |请求数据| jsonstring |Y|
data.org\_ unit\_ids| 部门id|array |Y|部门id
 
 请求示例
```
{"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf",	"data":	{	 "org_unit_ids":["idexample",”idslfiaesj”]	 	}
}
```

返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```
