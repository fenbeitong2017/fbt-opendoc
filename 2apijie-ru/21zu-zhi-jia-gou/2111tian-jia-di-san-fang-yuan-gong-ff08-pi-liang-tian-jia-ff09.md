2.2.1.1.添加第三方员工（批量添加到公司根目录下）

| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/auth/third/user/batch/save |

请求参数，以application/x-www-form-urlencoded传递：

请求参数

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| timestamp | 时间戳 | long | Y | 13位时间戳 |
| access\_token | token | string | Y | 登录 token |
| employee\_id | 操作人id | string | N | 操作人id,调用接口人 id |
| data | 请求数据 | jsonstring | Y ||
| data.employee\_list | 员工信息 | array | Y ||
| data.employee\_list.name | 员工姓名 | string | Y ||
| data.employee\_list.phone | 员工手机号 | string | Y ||
| data.employee\_list.org\_unit\_id | 员工组织ID，需要与公司ID一样 | string | Y ||
 | data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y ||

请求示例

```
{ "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "data":
  {  
    "employee_list":[
      {
        "name":"张5s",
        "phone":"13718432812",
        "org_unit_name":"5747fbc10f0e60e0709d8d7d",
       "third_employee_id":"57ab054c2528226a805bd5e1"
      },
      {
        "name":"张5",
        "phone":"13718432992",
        "org_unit_name":"5747fbc10f0e60e0709d8d7d",
       "third_employee_id":"57ab054c2528226a805bd500"
      }

    ]  
 }
}
```

返回结果

```
{
   "request_id": "LaZNvBntsBD20nJ7ekgn",
   "code": 0,
   "msg": "success",
   "data": {

   }
}
```

```
{
    "request_id": "MzWkSvZ3sVC2FYg9bCLt",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "59ce56d02798633485e206a9",
                "phone": "17080151661",
                "name": "塞外-test",
                "thirdEmployeeId": "ddd-test-A",
                "errorMsg": "第三方用户ID已经被绑定"
            }
        ]
    }
}
```



