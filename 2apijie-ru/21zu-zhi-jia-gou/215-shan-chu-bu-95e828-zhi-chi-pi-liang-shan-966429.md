根据企业ID删除部门请求方式|请求地址
----|---
POST|/open/api/third/departments/delete

请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求
data.company\_id| 部门id|string |Y|公司ID
data.third\_org\_id| 部门id|string |Y|第三方机构部门ID


 
 请求示例
```
{"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf",	"data":	{	
 "company_id":"2436574546343",
"third_org_id":"345467787564"	 
 }
}
```



返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",  
  "code": 0,   
 "msg": "success", 
   "data": {     
       }
}
```
