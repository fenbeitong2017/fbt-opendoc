2.2.3.7 批量查询部门详情
####接口说明
- 1.**最新接口**
- 2.支持批量查询
- 3.根据部门ID集合查询部门的详细信息

请求方式|请求地址
----|---
POST|/open/api/third/departments/detail/by_ids

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
data.ids|部门id集合| jsonarray |Y|现只支持通过分贝部门ID查询，不支持第三方部门ID







请求示例:
```

    "access_token": "xxx.xxx.xxx",
    "timestamp": 123456789,
    "employee_id":"12345678",
    "sign": "jifejfwojelajflejf",
    "data": 
     {
    "company_id":"5d1b1d2f23445f4dca76304b",
    "ids":["5d3580df23445f72cea02447","5d3adf0e23445f7622ed5de2"]
    }    
```

返回结果

```
{
    "request_id": "As70McLhXB1T9j0u",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": [
        {
            "id": "5d3580df23445f72cea02447",//分贝部门ID
            "company_id": "5d1b1d2f23445f4dca76304b",//公司ID
            "name": "测试部门01",//部门名称
            "parent_org_unit_id": "5d1b1d2f23445f4dca76304b",//父部门ID
            "level": 1,
            "rank": 8,
            "employee_count": 0,
            "third_org_id": "37"//第三方部门ID
        },
        {
            "id": "5d3adf0e23445f7622ed5de2",
            "company_id": "5d1b1d2f23445f4dca76304b",
            "name": "测试部门001",
            "parent_org_unit_id": "5d1b1d2f23445f4dca76304b",
            "level": 1,
            "rank": 10,
            "employee_count": 0,
            "third_org_id": "39"
        }
    ]
}


```






