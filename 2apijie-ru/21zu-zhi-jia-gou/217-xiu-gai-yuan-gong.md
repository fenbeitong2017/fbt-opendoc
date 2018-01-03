根据企业ID修改员工信息
请求方式|请求地址
----|---
POST|/open/api/third/org/employees/delete(同添加员工)


请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee_id| 三方员工id|string|Y| 三方员工id  
 data.employee. phone || string | Y| 手机号:13988987443
 data.employee. name| | string | Y| 姓名：张三
 data.employee. gender| | string | Y| 性别 1 
 data.employee. birth_date| | string | Y| 生日yyyymmdd
 data.employee. employee_id| | string | Y| 员工 id
 data.org_ unit_ids| | string|Y|  所属部门
data.cert_list|| array|Y| 证件 
 data.cert\_list. cert_type| | string |Y| 证件类型
 data.cert\_list. cert_no| | string |Y| 证件号2211239012r28351
data.role||string|Y| 角色
data.biz\_ trip_policy||jsonstring |Y| 
data.biz\_ trip\_policy. air\_priv\_flag| |boolean|Y| 机票权限
data.biz\_ trip\_policy. air\_verify\_flag| |boolean|Y| 机票是否需要审批
data.biz\_ trip\_policy. hotel\_priv\_flag| |boolean|Y| 酒店权限
data.biz\_ trip\_policy. hotel\_verify\_flag| |boolean|Y| 酒店是否需要审批
data.biz\_ trip\_policy. train\_priv\_flag| |boolean|Y|火车权限 
data.biz\_ trip\_policy.train\_verify\_flag| |boolean|Y| 火车是否需要审批
data.biz\_ trip\_policy. rule\_limit\_flag| |boolean|Y| 是否限制差旅规
data.biz\_ trip\_policy. rule_id| |boolean|Y|差旅规则  
data.biz\_ trip\_policy. exceed\_buy\_flag| |boolean|Y| 允许超标
data. car_policy| | jsonstring|N|
data. car_policy.exceed\_ buy\_flag| | boolean|N|
 data. mall_policy | |Object|N|
 data. mall_policy.mall\_ priv\_flag| | boolean |N|
 
 
 请求示例``` 

{
 "access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data":{
	"employee_id":"xxxxxx",    "employee": {        "phone": "13988987443",        "name": "hello",        "gender": 1,        "birth_date": "yyyymmdd",        "status": 1    },    "org_unit_ids": [        "abc",        "def"    ],I    "cert_list": [        {            "cert_type": 1,            "cert_no": "2211239012r28351"        }    ],    "role": 1,    "biz_trip_policy": {        "air_priv_flag": false,        "air_verify_flag": true,        "hotel_priv_flag": true,        "hotel_verify_flag": false,        "train_priv_flag": true,        "train_verify_flag": false,        "rule_limit_flag": true,        "rule_id": "575263e982f880a6d686ce11",        "exceed_buy_flag": false    },    "car_policy": {        "car_priv_flag": true,        "rule_limit_flag": true,        "rule_id": 2,        "exceed_buy_flag": false    },    "mall_policy": {        "mall_priv_flag": true,        "rule_limit_flag": true,        "rule_id": "ofaijwf",        "exceed_buy_flag": false    }}}

```

返回结果
```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```
