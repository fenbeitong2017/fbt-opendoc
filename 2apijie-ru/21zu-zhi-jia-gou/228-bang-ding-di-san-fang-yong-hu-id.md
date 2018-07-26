2.2.8 绑定第三方用户ID
####接口说明
- 1.**最新接口**
- 2.支持批量绑定
- 3.如果员工信息已经在组织架构中(通过管理后台导入)，但是没有绑定第三方用户ID，则进行该接口的调用.若通过接口同步组织架构和人员信息，则不需要调用此接口

请求方式|请求地址
----|---
POST|/open/api/third/employees/bind

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|9joljoifj
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.phone|手机号|string|Y
data.third\_employee\_id|部门id| string |Y|第三方人员ID







请求示例:
```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": {
    "bind_employee_list":
    [
      {
      "phone":"13131313131",
      "third_employee_id":"test_60000"
      }
    ]
  }
}

```

返回结果

```


{"request_id": "LaZNvBntsBD20nJ7ekgn",  
 "code": 0,   
 "msg": "success" 
}


{"request_id":"JBf1zsdKYCjUoEuQMEKN",
"code":200002,
"msg":"当前第三方用户手机号不存在"
}


```






