2.2.3 删除员工
####接口说明
- 1.**最新接口**
- 2.支持批量删除


请求方式|请求地址
----|---
POST|/open/api/third/employees/delete


请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
access_token|api鉴权Token|string|Y|
sign|签名|string|Y||
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|请求数据
data.third\_employee\_ids| 三方员工id|jsonarray|Y| 三方员工id 
 

 
 请求示例
 
 
 ``` 


{
 "access_token": "xxx.xxx.xxx",
 "timestamp":123456789,
 "employee_id":12345678,
 "sign": "jifejfwojelajflejf",
 "data":{
	"third_employee_ids":["12345678","dfghtuy6754"]   
```

返回结果
```
{  
 "request_id": "LaZNvBntsBD20nJ7ekgn", 
  "code": 0,   
  "msg": "success",  
  "data": {   
     }
}

```
