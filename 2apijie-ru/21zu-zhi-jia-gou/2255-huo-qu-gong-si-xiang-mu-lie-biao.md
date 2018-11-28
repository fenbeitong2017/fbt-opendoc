2.2.5.5 获取公司项目列表
####接口说明
- 1.**最新接口**

请求方式|请求地址
----|---
POST|/open/api/third/project/list


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
data.page_size|数每页条数|integer |N|1
data.state|项目状态| integer |N| 1启用 0停用
data.member_name|项目负责人名称| string |N| 张三
data.name|项目名称| string |N| 国航项目
data.page_index|页数| integer |N| 1
data.code|项目code| string |N| j93jkd983jjker



 请求示例:
 
 ```
{
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": 12345678,
  "sign": "hdi8492j828j37264q0dj8sh",
  "data": {
  "company_id": "5747fbc10f0e60e0709d8d7d",
  "page_size": 100
  }
}
```

返回结果

```
{"request_id": "oAb3dlB0KZLzihXXNKXX",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "pSize": 100,
    "data": [
      {
        "beginDate": "2019-04-20 10:00:00",
        "code": "36576232texce4694",
        "endDate": "2019-04-21 10:00:00",
        "usableRange": {
          "value": "仅限项目成员",
          "key": 2
        },
        "name": "项目名称-5",
        "memberName": "范法法",
        "id": "5bfdf24e23445f3863c1e66f",
        "state": {
          "value": "启用",
          "key": 1
        },
        "thirdCostId": "35hfdd43UDJKF8"
      },
      {
        "beginDate": "2019-04-26 10:00:00",
        "code": "3657623234560984694",
        "endDate": "2019-04-27 10:00:00",
        "usableRange": {
          "value": "不限制",
          "key": 1
        },
        "name": "项目名称-4",
        "memberName": "韩树起",
        "id": "5bfd199123445f10a33e1bb8",
        "state": {
          "value": "启用",
          "key": 1
        },
        "thirdCostId": "35368734574343UDJKF8"
      },
      {
        "beginDate": "2019-04-20 10:00:00",
        "code": "36576560984694",
        "endDate": "2019-04-21 10:00:00",
        "usableRange": {
          "value": "仅限项目成员",
          "key": 2
        },
        "name": "项目名称-3",
        "memberName": "范法法",
        "id": "5bfd196323445f10a33e1bb7",
        "state": {
          "value": "停用",
          "key": 0
        },
        "thirdCostId": "35468234574343UDJKF8"
      },
      {
        "beginDate": "2018-04-20 00:00:00",
        "code": "365335d560984694",
        "endDate": "2018-04-21 23:59:59",
        "usableRange": {
          "value": "仅限项目成员",
          "key": 2
        },
        "name": "项目名称-2",
        "memberName": "范法法",
        "id": "5bfd17b123445f10a33e1bb3",
        "state": {
          "value": "启用",
          "key": 1
        },
        "thirdCostId": "354682336574343UDJKF8"
      },
      {
        "beginDate": "2018-04-20 10:00:00",
        "code": "35erd560984694",
        "endDate": "2018-04-21 10:00:00",
        "usableRange": {
          "value": "仅限项目成员",
          "key": 2
        },
        "name": "项目名称-1",
        "memberName": "范法法",
        "id": "5bfd16c323445f10a33e1bb1",
        "state": {
          "value": "停用",
          "key": 0
        },
        "thirdCostId": "882336574343UDJKF8"
      },
      {
        "beginDate": "1970-01-01 00:00:00",
        "code": "test0511",
        "endDate": "1970-01-01 00:00:00",
        "usableRange": {
          "value": "不限制",
          "key": 1
        },
        "name": "测试流程",
        "memberName": "梁禹",
        "id": "5af55cca23445f6f54be89c5",
        "state": {
          "value": "启用",
          "key": 1
        }
      }
    ],
    "count": 454,
    "page": 1
  }
  
}
```
