2.2.6.1.批量授权角色和设置部门主管
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/company/role/auth


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
data.operator_id|操作ID|string |Y|third_hanbing
data.operator_role|人员类型| integer |Y|固定值6
data.source|来源|string |Y|固定值 openapi
data.empower_type|授权类型| integer |Y|1:授权部门主管角色,2:授权其他角色
data.type|人员类型|string |Y|1:分贝ID, 2:第三方ID
data.delete_history|项目信息| boolean |Y|是否要删除原数据(历史角色中人员/原部门主管)
data.role_ids|角色列表|jsonarray |Y|角色信息
data.role_ids.user_ids|员工ID|jsonarray |Y|323232323223
data.role_ids.org_unit_id|部门ID| string |N| empower_type =1时  不可为空(可使用分贝和第三方部门ID)
data.role_ids.role_id|角色ID | string |N| empower_type =2时 不可为空(只能使用分贝角色ID


 请求示例:
 
 ```

  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": "12345678",
  "employee_type":"0",
  "sign": "jifejfwojelajflejf",
  "data": {
  "company_id": "5cc1598623445f612c73b27a",
  "operator_id": "59bf74f423445f31bd64bc5c",
  "operator_role": 6,
  "source": "openApi",
  "empower_type": 2,
  "type": 1,
  "delete_history": true,
  "role_ids": [
    {
      "user_ids": [
        "5d037e8d23445f429efe0a1d",
        "5ce60a5523445f15f135f9f8",
        "5d0b774c23445f0635a1c36f",
        "5d75f63523445f08e043593f"
      ],
      "role_id": "5c983e9023445f1c7d8275bf"
    }
  ]
}

```

返回结果

```

 成功：
{
    "request_id": "W0e9h44H2EZq4xlJRoRv",
    "code": 0,
    "type": 0,
    "msg": "success"
  }
  
  失败：
  {
    "request_id": "GAlmtLbzm68HoNTsw02T",
    "code": 100004,
    "msg": "没有权限进行此操作"
  }


```
