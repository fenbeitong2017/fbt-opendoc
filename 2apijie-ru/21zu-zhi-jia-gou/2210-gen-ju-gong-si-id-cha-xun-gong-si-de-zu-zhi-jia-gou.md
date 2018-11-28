2.2.3.5 根据公司ID查询公司的组织架构
####接口说明
- 1.**最新接口**
- 2.根据公司ID查询组织架构详情


请求方式|请求地址
----|---
POST|open/api/third/departments/query

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|argfewfsvre345eg
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.company\_id|公司ID|string|Y|jl83j9ej873j38dje83jd9ee




请求示例:
```
{
"access_token": "xxx.xxx.xxx",
"timestamp": 123456789,
"employee_id":12345678,
"sign": "jifejfwojelajflejf",
"data": {
"company_id":"5747fbc10f0e60e0709d8d7d",
}
}
```

返回结果

```
{
"request_id": "s1qaMDROYvS3UsBjA6Ko",
"code": 0,
"msg": "success",
"data": [
        {
            "employeeCount": 0,
            "orgUnitFullName": "北京分贝通科技有限公司",
            "orgUnitId": "5747fbc10f0e60e0709d8d7d",
            "orgUnitName": "北京分贝通科技有限公司",
            "orgUnitParentFullName": "",
            "orgUnitParentId": null,
            "orgUnitParentName": ""
        },
        {
            "employeeCount": 0,
            "orgUnitFullName": "北京分贝通科技有限公司/财务部",
            "orgUnitId": "5abdf19e27986373488a010f",
            "orgUnitName": "财务部",
            "orgUnitParentFullName": "北京分贝通科技有限公司",
            "orgUnitParentId": "5747fbc10f0e60e0709d8d7d",
            "orgUnitParentName": "北京分贝通科技有限公司"
        },
        {
            "employeeCount": 0,
            "orgUnitFullName":"北京分贝通科技有限公司/财务部/财务一部",
            "orgUnitId": "59e9bcc4279863398a0672eb",
            "orgUnitName": "财务一部",
            "orgUnitParentFullName": "北京分贝通科技有限公司/财务部",
            "orgUnitParentId": "5abdf19e27986373488a010f",
            "orgUnitParentName": "财务部"
        }
    ]
}



```


