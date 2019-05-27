2.2.3.6 绑定第三方部门ID
####接口说明
- 1.**最新接口**
- 2.2.3.6 绑定第三方部门ID


请求方式|请求地址
----|---
POST|/open/api/third/departments/bind

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|argfewfsvre345eg
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.companyId|公司ID|string|Y|354657j9ej873j30987654
data.thirdOrgId|第三方机构部门ID|string|N|jl83j9ej873j38dje83jd9ee
data.operatorId|操作人ID|string|Y|dje83jd9ee345678，同employee_id
data.type|绑定类型|integer|Y|1:根据分贝部门id绑定 2:根据部门全名称绑定
data.orgId|分贝部门ID|string|Y|3456ej873j38dj
data.orgNameList|部门集合|string|N|按照部门名称从当前部门到公司顺序




请求示例:
```

"access_token": "xxx.xxx.xxx",
"timestamp": 123456789,
"employee_id":"third_jianyuan",
"type":1,
"sign": "09676i3j7d994783ujd893",
"data": {
  "thirdOrgId": "third_jianyuanceshi",
  "type": 1,
  "companyId": "5747fbc10f0e60e0709d8d7d",
  "orgId": "5b2112752798634dccdb09e0",
  "operatorId": "third_jianyuan"
}


{
  "type": 2,
  "orgNameList": ["技术发展司","技术委员会","研发部","北京分贝金服科技有限公司"],
 
}

```

返回结果

```
{
    "request_id": "MbbPPJyDqZEFoqljiuBJ",
    "code": 0,
    "type": 0,
    "msg": "success"
}


{
    "msg": "当前第三方部门ID已经存在",
    "code": 200002,
    "request_id": "wvyR8OZVzwbqylChPfFg"
}


{
    "msg": "部门信息参数不正确",
    "code": 200001,
    "request_id": "k6bF6U0BUM4ULZUaOgXx"
}
```


