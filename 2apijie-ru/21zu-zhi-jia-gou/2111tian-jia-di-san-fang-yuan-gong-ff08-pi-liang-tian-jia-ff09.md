2.2.1.1.添加第三方员工

####接口说明
- 1.**最新接口**
- 2.批量添加到公司根目录下
  添加后的用户权限全部都为关闭状态(包括机票，用车，火车，酒店，采购，用餐)

| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/auth/third/user/batch/save |


请求参数

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| timestamp | 时间戳 | long | Y | 13位时间戳 
| access\_token | token | string | Y | 登录 token 
| employee\_id | 操作人id | string | N | 操作人id,调用接口人 id 
| data | 请求数据 | jsonstring | Y |请求数据
| data.employee\_list | 员工信息 | jsonarray | Y |员工请求数据
| data.employee\_list.name | 员工姓名 | string | Y |张三
| data.employee\_list.phone | 员工手机号 | string | Y |17902029298
| data.employee\_list.org\_unit\_id | 员工组织ID，需要与公司ID一样 | string | Y |lk98eow9jisdj87
 | data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y |jskngla87j7ei9ej

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
        "org_unit_id":"5747fbc10f0e60e0709d8d7d",
       "third_employee_id":"57ab054c2528226a805bd5e1"
      },
      {
        "name":"张5",
        "phone":"13718432992",
        "org_unit_id":"5747fbc10f0e60e0709d8d7d",
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
   "msg": "success"
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


```
{
    "request_id": "zgubWmjt4y9c5AWcOwgs",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "59df06662798635263b8414c",
                "phone": "25777059211",
                "name": "IDG-has888",
                "thirdEmployeeId": "IDG-888s0lll",
                "errorMsg": "手机号已经存在，请使用其他手机号"
            },
            {
                "companyId": "59df06662798635263b8414c",
                "phone": "18777198765",
                "name": "IDG-h999009",
                "thirdEmployeeId": "IDG-h99k4lll",
                "errorMsg": "手机号已经存在，请使用其他手机号"
            }
        ]
    }
}

```