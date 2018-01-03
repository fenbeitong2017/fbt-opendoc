
请求方式|请求地址
----|---
POST|/open/api/org/employees/detail

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|1位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data. employee\_id|操作人id | String |Y|


请求示例```
{
	"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf"	"data":	{    	employee_id:"faxxx12399004392293840274"	}}

```

返回结果```
{
    "request_id": "Htsv6gkEaewQ3Kk7L3el",
    "code": 0,
    "msg": "success",
    "data": {
        "user_role": 3,
        "user_email": "",
        "user_id": "59bf74f423445f31bd64bc5c",
        "user_name": "张三",
        "user_phone": "17080151667"
    }
}
```
