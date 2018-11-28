2.2.5.7查询项目详情
####接口说明
- 1.**最新接口**

请求方式|请求地址
----|---
POST|/open/api/third/project/get

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
data.third_cost_id|第三方项目ID| string |Y|9843894927943

 请求示例:
 
 ```
{
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": 12345678,
  "sign": "jifejfwojelajflejf",
  "data": {
  "company_id": "5747fbc10f0e60e0709d8d7d",
  "third_cost_id": "35hfdd46563UDJKF8"
 }
}
```

返回结果

```
{
    "request_id": "Dk8mmyp2FySVLj7AWbkC",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "beginDate": "2019-04-20 10:00:00",
        "code": "3657623562texce4694",
        "manager": [
            {
                "deptName": "北京分贝金服科技有限公司",
                "companyId": "5747fbc10f0e60e0709d8d7d",
                "memberName": "范法法",
                "memberId": "5b07b3b723445f587fa7d548"
            }
        ],
        "endDate": "2019-04-21 10:00:00",
        "usableRange": {
            "value": "不限制",
            "key": 1
        },
        "memberDept": [
            {
                "memberName": "X部门",
                "memberId": "58c21a365f281a7e6f810ae6"
            }
        ],
        "name": "项目名称-7",
        "expiredState": {
            "value": "过期自动停用",
            "key": 2
        },
        "member": [
            {
                "deptName": "测试1部门",
                "companyId": "5747fbc10f0e60e0709d8d7d",
                "memberName": "韩冰",
                "memberId": "59bf74f423445f31bd64bc5c"
            },
            {
                "deptName": "北京分贝金服科技有限公司",
                "companyId": "5747fbc10f0e60e0709d8d7d",
                "memberName": "范法法",
                "memberId": "5b07b3b723445f587fa7d548"
            }
        ],
        "description": "哎呦，不错o-7",
        "state": {
            "value": "启用",
            "key": 1
        }
    }
}


```
