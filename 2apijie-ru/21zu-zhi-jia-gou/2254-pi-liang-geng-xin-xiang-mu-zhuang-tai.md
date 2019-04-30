2.2.5.4 批量更新项目状态
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/project/updateStateBatch


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
data.type|第三方项目ID类型|integer |Y|分贝通项目IDI:1,第三方项目ID:2
data.state|项目状态| integer |Y| 1启用 0停用
data.id_list|项目ID集合| jsonarray |Y| 项目ID集合


 请求示例:
 
 ```

  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": "12345678",
  "employee_type":"0",
  "sign": "hdi8492j828j37264q0dj8sh",
  "data": {
  "state": 0, 
  "type":2,
"company_id":"5747fbc10f0e60e0709d8d7d",
  "id_list": [
    "35hfdd4698943f63UDJKF8",
    "35hfd6dgd469345672DJKF8"
  ]
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
