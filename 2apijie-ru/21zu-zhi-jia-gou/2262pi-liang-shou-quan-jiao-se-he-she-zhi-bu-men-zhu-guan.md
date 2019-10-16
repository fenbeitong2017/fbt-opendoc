2.2.6.2.根据公司ID查询公司角色信息
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/company/roles/get


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


 请求示例:
 
 ```

  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": "12345678",
  "employee_type":"0",
  "sign": "jifejfwojelajflejf",
  "data": {"company_id":"5cc1598623445f612c73b27a"}

```

返回结果

```
{
  "request_id": "V9wXB8srtYNox3aXh0aW",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": [
    {
      "id": "5bcf0aef23445f71695d10a7",
      "name": "部门主管",
      "count": 0,
      "role_code": "department_manager",
      "role_type": 1
    },
    {
      "id": "5bcf0b2723445f71695d10a9",
      "name": "报表查看",
      "count": 0,
      "role_code": "statement_configuration",
      "role_type": 1
    },
    {
      "id": "5c36fa1823445f5f755ad15c",
      "name": "福利管理",
      "count": 0,
      "role_code": "welfare_management",
      "role_type": 1
    },
    {
      "id": "5c983e9023445f1c7d8275bf",
      "name": "账户管理",
      "count": 0,
      "role_code": "account_management",
      "role_type": 1
    },
    {
      "id": "5cab1e3b23445f46fccbe894",
      "name": "发票管理",
      "count": 0,
      "role_code": "invoice_management",
      "role_type": 1
    },
    {
      "id": "5cebc2f240c185cf505c4a1a",
      "name": "节省奖励配置",
      "count": 0,
      "role_code": "rule_reward",
      "role_type": 1
    }
  ]
}


```
