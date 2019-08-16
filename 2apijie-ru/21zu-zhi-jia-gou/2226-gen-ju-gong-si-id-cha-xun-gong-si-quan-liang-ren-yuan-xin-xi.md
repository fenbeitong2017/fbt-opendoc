2.2.2.6 根据公司ID查询公司全量人员信息
####接口说明

- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/company/third/info

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|9joljoifj
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.companyId|公司ID|string|Y
data.type|公司类型| string |Y|固定值: 1







请求示例:
```

"access_token": "xxx.xxx.xxx",
"timestamp": 123456789,
"employee_id":"12345678",
"sign": "jifejfwojelajflejf",
"data":{"companyId":"5cc1598623445f612c73b27a","type":"1"}

```


返回字段说明:

字段|名称|类型|必填|描述
-----|-----|----|----|----
gender|性别|string |Y|0，1
phone|手机号|string |Y|13801000001
roleId|权限角色 | string |Y|2：普通管理员，3：普通员工，6：授权负责人
name| 姓名|string |Y|张三
deptId| 分贝部门ID|string|Y|分贝部门ID，可根据ID调用部门详情接口查询部门信息
id |分贝人员ID| string |Y|分贝人员ID
thirdEmployeeId|第三方人员ID|string|Y|第三方人员ID
dept|部门名称|string |Y|审计部
status|人员状态| string |Y|1:正常，2:停用




返回结果

```
{
  "request_id": "7dbjQ04KbOAepp5QnuOs",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "thirdEmployeeList": [
      {
        "manager": false,
        "gender": 1,
        "phone": "17080151667",
        "roleId": "6",
        "name": "dave.han",
        "deptId": "5cc1598623445f612c73b27a",
        "id": "59bf74f423445f31bd64bc5c",
        "thirdEmployeeId": "manager4242",
        "dept": "测试企业",
        "status": 1
      },
      {
        "manager": false,
        "gender": 1,
        "phone": "19089009890",
        "roleId": "3",
        "name": "测试韩001",
        "deptId": "5cc179b723445f0a316e2e95",
        "id": "5cc17a0823445f0a316e2ea9",
        "thirdEmployeeId": "27321946242009231506",
        "dept": "测试一级部门2",
        "status": 1
      }
    ]
  }
}

```






