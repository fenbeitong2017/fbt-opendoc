2.2.5.3 更新项目状态
####接口说明
- 1.**最新接口**
- 2.不支持批量更新


请求方式|请求地址
----|---
POST|/open/api/third/project/updateState


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|4ergfdsawesf
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.company_id|公司ID|string|Y|5747fbc10f0e60e0709d8d7d
data.third_cost_id|第三方项目ID|string |Y|35368734574343UDJKF8
data.state|项目状态| integer |Y| 1启用 0停用



 请求示例:
 
 ```
{
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": 12345678,
  "sign": "hdi8492j828j37264q0dj8sh",
  "data": {
  "company_id": "5747fbc10f0e60e0709d8d7d",
  "third_cost_id": "35368734574343UDJKF8",
  "state": 1
}
}
```

返回结果

```
{
    "request_id": "ArsRnhC1jA70eMXg78ry",
    "code": 0,
    "type": 0,
    "msg": "success"
}
```
