2.2.4.3 查询乘车，机，入住人详细信息
####接口说明
- 1.**最新接口**
- 2.不支持批量查询


请求方式|请求地址
----|---
POST|/open/api/third/frequent/get


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|4ergfdsawesf
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.type|公司类型|integer|Y|1:代表分贝公司, 2:代表第三方企业
data.frequent_id_type|第三方联系人ID类型|integer |Y| 1: 分贝 2：第三方
data.frequent_id|第三方联系人ID| string |Y|第三方用户ID
data.company_id|公司ID| string |Y|58734b2e5f281a41b304181f
data.owner_id|当前登录人| string |Y|为第三方用户ID

 请求示例:
 
 ```
"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":"12345678","sign": "jifejfwojelajflejf","data": { "type" :2, 
"frequent_id_type":2, 
"company_id":"5747fbc10f0e60e0709d8d7d",  
"owner_id":"zhangsan-dev",    
"frequent_id":"zhangsan-dev"
}


```

返回结果

```
{
    "request_id": "sY252dO01Hbr7APzValC",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "gender": 1,
        "frequentType": 2,
        "unitName": "测试部门",
        "orgnazationFlag": false,
        "givenName": "hansins",
        "nationalityName": "中国",
        "selectedEmployeeId": "59bf74f423445f31bd64bc5c",
        "phoneNum": "17800089999",
        "ownerId": "59bf74f423445f31bd64bc5c",
        "idNumber": "2305009876434",
        "useType": 1,
        "birthDate": "1990-02-02",
        "employeeFlag": true,
        "thirdFrequentId": "40iojr576we7654",
        "nationality": "CN",
        "useNum": 0,
        "familyName": "dave",
        "name": "张三",
        "idTypeEntity": {
            "value": "护照",
            "key": 2
        },
        "certValidDate": "2117-02-01",
        "id": "5bfb899c23445f2558d934b8",
        "category": 40,
        "email": ""
    }
}


{
    "request_id": "NlJISjtZzEzADoYMT45H",
    "code": 600,
    "msg": "该联系人信息不存在:40iojr576we7654"
}


{
    "request_id": "6SAgFcefCXMh2GpqAYNw",
    "code": 600,
    "msg": "国内机票联系人类型错误！"
}

```
