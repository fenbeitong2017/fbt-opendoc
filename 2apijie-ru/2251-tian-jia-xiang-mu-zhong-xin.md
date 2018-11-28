2.2.11 添加第三方乘车，机，入住人
####接口说明
- 1.**最新接口**
- 2.不支持批量添加


请求方式|请求地址
----|---
POST|/open/api/third/project/create


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|4ergfdsawesf
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.company_id|公司ID|string|Y|
data.third_frequent_id|第三方联系人ID|string |Y|不可重复，更新/查询/删除操作使用
data.name|姓名| string |Y|张三
data.gender|性别| string |N|1:男2:女 当id_type为1时不需要传递，其他类型需要传递
data.birth_date|出生年月| string |N|1990-02-02 当id_type为1时不需要传递，其他类型需要传递


 请求示例:
 
 ```
{
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": 12345678,
  "sign": "jifejfwojelajflejf",
  "data": {
    "company_id": "5747fbc10f0e60e0709d8d7d",
    "user_id": "hanshuqi-H5-dev",
    "type": 2,
    "third_cost_id": "35hfdd43UDJKF8",
    "code": "36576232texce4694",
    "name": "国航项目",
    "description": "国航项目很好",
    "begin_date": "2019-04-20 10:00:00",
    "end_date": "2019-04-21 10:00:00",
    "expired_state": 2,
    "usable_range": 2,
    "state": 1,
    "manager": [
      {
        "member_id": "third-fanqian",
        "is_manager": true,
        "member_type": 3
      }
    ],
    "member": [
      {
        "member_id": "hanshuqi-H5-dev",
        "is_manager": false
      }
    ],
    "member_dept": [
      {
        "member_id": "000666",
        "is_manager": true
      }
    ]
  }
}
```

返回结果

```
{
    "request_id": "xSm0lDkBo87t2x3nb3UP",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "id": "5bfdf24e23445f3863c1e66f"
    }
}

```
