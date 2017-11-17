根据企业ID添加员工信息请求方式|请求地址
----|---
POST|/open/api/org/employees/create

请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee_id| 三方员工id|string|Y| 三方员工id  
 data.employee.phone| 手机号| string | Y| 13988987443
 data.employee.name|姓名 | string | Y| 张三
 data.employee.gender| 性别| string | Y|  1 
 data.employee.birth\_date| 生日| string | Y| yyyymmdd
 data.employee.employee\_id |员工 id| string | Y| 
 data.org\_unit_ids|  所属部门|string| |Y| 
data.cert\_list|证件 | array|Y| 
 data.cert\_list.cert\_type|证件类型 | string |Y| 
 data.cert\_list.cert\_no| 证件号| string |Y| 2211239012r28351
data.role|角色|string|Y| 
data.biz\_trip_policy||jsonstring |Y| 
data.biz\_trip\_policy.air\_priv\_flag|机票是否需要审批|boolean|Y| 机票权限
data.biz\_trip\_policy.air\_verify\_flag| |boolean|Y|
data.biz\_trip\_policy.hotel\_priv\_flag|酒店权限 |boolean|Y| 
data.biz\_trip\_policy.hotel\_verify\_flag|酒店是否需要审批 |boolean|Y| 
data.biz\_trip\_policy.train\_priv\_flag |火车权限 |boolean|Y|
data.biz\_trip\_policy.train\_verify\_flag| 火车是否需要审批|boolean|Y| 
data.biz\_trip\_policy.rule\_limit\_flag| 是否限制差旅规 |boolean|Y|
data.biz\_trip\_policy.rule\_id|差旅规则 |boolean|Y|  
data.biz\_trip\_policy.exceed\_buy\_flag|允许超标 |boolean|Y| 
data.car_policy| | jsonstring|N| 
data.car_policy.car\_priv\_flag| | boolean |N| 
data.car_policy.rule\_limit\_flag| | boolean |N| 
data.car_policy.rule\_id| | boolean |N| 
data.car_policy.exceed\_buy\_flag| | boolean |N| 
data.mall_policy|jsonstring| | N ||
data.mall_policy.mall\_priv\_flag| | boolean |N|
data.mall_policy.rule\_limit\_flag| | boolean |N| 
data.mall_policy.rule\_id| | boolean |N|  
data.mall_policy.exceed\_buy\_flag| | boolean |N|

  
 请求示例:``` 

{
 "access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data":{    "third_employee_id":"xxxx",    "employee": {        "phone": "13988987443",        "name": "hello",        "gender": 1,        "birth_date": "yyyymmdd",        "status": 1    },    "org_unit_ids": [        "abc",        "def"    ],I    "cert_list": [        {            "cert_type": 1,            "cert_no": "2211239012r28351"        }    ],    "role": 1,    "biz_trip_policy": {        "air_priv_flag": false,        "air_verify_flag": true,        "hotel_priv_flag": true,        "hotel_verify_flag": false,        "train_priv_flag": true,        "train_verify_flag": false,        "rule_limit_flag": true,        "rule_id": "575263e982f880a6d686ce11",        "exceed_buy_flag": false    },    "car_policy": {        "car_priv_flag": true,        "rule_limit_flag": true,        "rule_id": 2,        "exceed_buy_flag": false    },    "mall_policy": {        "mall_priv_flag": true,        "rule_limit_flag": true,        "rule_id": "ofaijwf",        "exceed_buy_flag": false    }}}

```

返回结果

```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}

```
