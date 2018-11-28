2.2.5.2 更新第三方项目中心
####接口说明
- 1.**最新接口**
- 2.不支持批量更新


请求方式|请求地址
----|---
POST|/open/api/third/project/update


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
data.user_id|添加人ID|string |Y|hanbing
data.type|人员和部门类型| integer |Y|1:分贝部门ID;  2:第三方ID
data.third_cost_id|第三方项目ID| string |Y|35hfdd43UDJKF8 不可重复，唯一标识
data.code|项目编号| string |Y|项目标号，不可重复
data.name|项目名称|string |Y|国航项目
data.description|项目描述| string |Y|项目描述
data.begin_date|项目开始时间| string |Y|2019-04-20 10:00:00
data.end_date|项目结束时间| string |Y|2019-04-21 10:00:00
data.expired_state|是否过期自动停用| integer |Y|过期后是否自动停用 1：不停用 2：停
data.usable_range|使用范围是否限制|integer |Y| 1不限2限制
data.state|项目状态| integer |Y|项目状态  1启用 0停用
data.manager|项目负责人| jsonarray |Y|项目负责人信息，项目负责人默认会是项目成员
data.manager.member_id|项目负责人人员ID| string |Y|third-hanbing
data.manager.is_manager|是否为负责人| boolean |Y|true,false
data.manager.member_type|员工部门标识| integer |Y|2:是部门3:是员工
data.member|项目成员信息| jsonarray |Y|项目成员信息
data.member.member_id|项目人员ID| string |Y|third-hanbing
data.member.is_manager|是否为负责人| boolean |Y|true,false
data.member|项目成员信息| jsonarray |N|项目成员信息
data.member.member_id|项目人员ID| string |N|third-hanbing
data.member.is_manager|是否为负责人| boolean |N|true,false
data.member_dept|项目部门信息| jsonarray |N|项目部门信息
data.member_dept.member_id|项目部门ID| string |N|third-dep-no
data.member_dept.is_manager|是否为负责人| boolean |N|true,false




 请求示例:
 
 ```
{
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": 12345678,
  "sign": "jifejfwojelajflejf",
  "data": {
    "company_id": "5747fbc10f0e60e0709d8d7d",
    "user_id": "hanbing",
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
        "member_id": "third-hanbing",
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
        "member_id": "third-dep-no",
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
