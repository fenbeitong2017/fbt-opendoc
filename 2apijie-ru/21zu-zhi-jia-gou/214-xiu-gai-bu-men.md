修改企业部门
请求方式|请求地址
----|---
POST|/open/api/third/departments/update

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|请求数据
data.company\_id|公司ID|string|Y|分贝通
data.org\_unit\_name|部门名称|string |Y|审计部
data.third\_parent\_id|直属部门id| string |Y|第三方直属部门ID
data.third\_org\_id|部门id| string |Y|第三方机构部门ID









请求示例:
 
 ```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": {
  "company_id": "07ab0579u252456ya805bd567",
  "org_unit_name": "审计部",
  "third_parent_id": "第三方直属部门ID",
  "third_org_id": "第三方机构部门ID",
  "operator_id": "57ab054c2528226a805bd523(当前用户id)"
}

}
```

返回结果

```


{"request_id": "LaZNvBntsBD20nJ7ekgn",  
 "code": 0,   
 "msg": "success" 
}


{"request_id":"JBf1zsdKYCjUoEuQMEKN",
"code":200002,
"msg":"当前第三方部门ID已经存在"
}


```
