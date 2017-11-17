请求方式|请求地址
----|---
POST|/open/api/auth/third/user/create

请求参数

-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.employee\_list|员工信息 |array |Y|
data.employee\_list.name |员工信息 |string |Y|
data.employee\_list.phone |员工信息 | string |Y|
data.employee\_list.org\_unit\_id |员工信息 | string |Y|
data.employee\_list.third\_employee\_id |员工信息 | string |Y|



请求示例

```

    "employeeList":[
      {
        "name":"张5s",
        "phone":"13718432812",
        "org_unit_id":"5747fbc10f0e60e0709d8d7d",
       "third_employee_id":"57ab054c2528226a805bd5e1"
      }
    ]  
}



返回结果



