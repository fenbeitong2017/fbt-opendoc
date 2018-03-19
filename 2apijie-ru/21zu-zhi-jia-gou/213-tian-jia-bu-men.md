请求方式|请求地址
----|---
POST|/open/api/third/departments/add


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|请求数据
data.companyId|部门名称|string|Y|部门名称
data.orgUnitName| 父部门 id|string |Y|父部门id
data.thirdParentId|部门 id| string |Y|部门 id
data.thirdParentId|部门 id| string |Y|部门 id
data.thirdParentId|部门 id| string |Y|部门 id


{
  "companyId": "公司ID",
  "orgUnitName": "部门名称信息",
  "thirdParentId": "第三方直属部门ID",
  "thirdOrgId": "第三方机构部门ID",
  "operatorId": "57ab054c2528226a805bd523(当前用户id)"
}
 
 请求示例:
 ```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": {   "org_unit_name":"综合部",   "org_unit_id":"xxxx",   "parent_id":"xxxxx" }
}
```

返回结果

```

{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```
