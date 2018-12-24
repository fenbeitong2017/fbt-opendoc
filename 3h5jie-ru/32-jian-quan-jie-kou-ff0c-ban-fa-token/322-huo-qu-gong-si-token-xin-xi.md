# 3.2.1 鉴权接口，颁发Token

* ## 请求参数，统一以application/x-www-form-urlencoded传递

| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/auth/v1/dispense |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| app\_id | 企业ID | string | Y |  |
| app\_key | 企业key | string | Y |  |
| app\_type | 类型 | string | N | 预留字段 |

请求示例：

```
{
    "app_id":"5747fbc10f0e60e0709d8d722",
    "app_key":"59b74c1323445f2d54dd07922"
}
```

返回结果：

```
    "request_id": "RqnwAR3En48ZbaMfa6Ub",
    "code": 0,
    "msg": "success",
    "data":{"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ0b2tlbiIsImFwcElkIjoiNTc0N2ZiYzEwZjBlNjBlMDcwOWQ4ZDdkIiwiaXNzIjoiYXBpIiwiZXhwIjoxNTA3NTE1ODQ5LCJqdGkiOiI1OWNkYWVjOTIyZTlmMTRlNmI0YTkwNTIifQ.oPgr-a_95RxyZqMj2pzeOBb4vfMCz0ACED2L-fWIdnU"}
}
```



