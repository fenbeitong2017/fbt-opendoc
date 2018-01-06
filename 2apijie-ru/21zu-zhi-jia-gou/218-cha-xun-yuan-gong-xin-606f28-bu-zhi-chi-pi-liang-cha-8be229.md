2.2.8 查询员工信息(不支持批量查询)

请求方式|请求地址
----|---
POST|/open/api/third/employees/info


字段|名称|类型|必填|描述
-----|-----|----|----|----
access_token|api鉴权Token|string|Y|
sign|签名|string|Y||
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring|Y||
data. employee\_id|需要查询人的id | string |Y|需要查询人员对应的ID|


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
