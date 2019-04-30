2.2.3.4 查询第三方部门信息
####接口说明
- 1.**最新接口**
- 2.不支持批量查询
- 3.根据部门ID查询部门的详细信息

请求方式|请求地址
----|---
POST|/open/api/third/departments/detail

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|argfewfsvre345eg
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.company\_id|公司ID|string|Y|分贝通
data.third\_org\_id|部门id| string |Y|第三方部门ID
data.type|部门类型| string |Y|部门类型，1:分贝部门ID 2:第三方部门ID






请求示例:
```

    "access_token": "xxx.xxx.xxx",
    "timestamp": 123456789,
    "employee_id":"12345678",
    "sign": "jifejfwojelajflejf",
    "data": {
        "company_id":"5747fbc10f0e60e0709d8d7d",
        "type":"1",
        "third_org_id":"5af424cb827986333fb1388b3"
        }
    
```

返回结果

```
{
    "request_id": "s1qaMDROYvS3UsBjA6Ko",
    "code": 0,
    "msg": "success",
    "data": {
        "employee_count": 0,
        "company_id": "5747fbc10f0e60e0709d8d7d",
        "level": 1,
        "name": "业务一部",
        "third_org_id": "234565",
        "parent_org_unit_id": "580f188c5f281a037c4b326c",
        "rank": 27,
        "id": "5af424cb27986333fb1388b3"
    }
}

{
    "request_id": "Uuu7pOW796xt8hCHeiuc",
    "code": 200001,
    "msg": "部门信息参数不正确"
}


```






