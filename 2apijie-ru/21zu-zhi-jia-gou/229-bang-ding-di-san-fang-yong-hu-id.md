请求方式|请求地址
----|---
POST|/open/api/third/employees/bind


请求参数

 字段 | 名称 | 类型 | 必填 | 描述 |
 --- | --- | --- | --- | --- |
access_token|api鉴权Token|string|Y|
sign|签名|string|Y||
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
 data| 请求数据 | jsonobject | Y | |
 data.bind_employee_list | 需要绑定的员工信息 | jsonarray | Y ||
 data.bind_employee_list.phone | 员工手机号 | string | Y |16090190901|
 data.bind_employee_list.third\_employee\_id | 第三方员工ID | string | Y ||

请求示例

```
{ "access_token": "xxx.xxx.xxx",
"timestamp": 123456789,
"data":
{\
"bind_employee_list":[
{
"phone":"13718432812",
"third_employee_id":"57ab054c2528226a805bd5e1"
},
{
"phone":"13718432000",
"third_employee_id":"26a80557ab054c25e1282bd5"
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


{
    "request_id": "95trbeihk0QlwlrF0gds",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "reason": "第三方id已经被其它用户绑定",
                "code": 600,
                "thirdEmployeeId": "26a80557ab054c25e1282bd5"
            }
        ]
    }
}



{
    "request_id": "h8G7qEzpDxjDPqUTPl55",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "reason": "第三方id已经被其它用户绑定",
                "code": 600,
                "thirdEmployeeId": "test-66600"
            },
            {
                "reason": "用户手机号不存在",
                "code": 600,
                "thirdEmployeeId": "test773"
            }
        ]
    }
}


```