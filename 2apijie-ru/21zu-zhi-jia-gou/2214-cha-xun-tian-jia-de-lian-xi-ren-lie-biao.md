2.2.14 查询添加的乘车(机)，入住人列表
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/frequent/list


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
data.selected_employee_id|实际选择的人|string |Y|同行人在组织架构的id ，employee_flag为false,不传递。为false时是从非组织架构选择添加的人员
data.frequent_type|场景类型| integer |Y|1:国内 2:国际 国际机票使用2
data.company_id|公司ID| string |Y|58734b2e5f281a41b304181f
data.owner_id|当前登录人| string |Y|为第三方用户ID




 请求示例:
 
 ```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": { "type" :2, 
"third_frequent_id": "40iojr576we7654" , 
"name":"张三",
"gender":1 ,
"birth_date":"1990-02-02",
"email":"san.zhang@fenbeitong.com",
"phone_num":"17800089098", 
"employee_flag":true, 
"selected_employee_id":"zhangsan-dev", 
"id_number":"2305434", 
"idType":2,
"category":40, 
"family_name":"dave",
"given_name":"hansins", 
"cert_valid_date":"2117-02-01",
"nationality":"CN",
"nationality_name":"中国",
"frequent_type":2, 
"company_id":"5747fbc10f0e60e0709d8d7d",  
"owner_id":"zhangsan-dev",    
"use_type":1 
}

}
```

返回结果

```
{
    "request_id": "vDcAlstUljL941zBUqQt",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": [
        {
            "gender": 1,
            "frequentType": 2,
            "unitName": "测试1部门",
            "orgnazationFlag": false,
            "givenName": "hansins",
            "nationalityName": "中国",
            "selectedEmployeeId": "zhangsan-dev",
            "phoneNum": "17809089098",
            "ownerId": "zhangsan-dev",
            "idNumber": "2305434",
            "useType": 1,
            "birthDate": "1990-02-02",
            "employeeFlag": true,
            "thirdFrequentId": "23456787",
            "nationality": "CN",
            "useNum": 0,
            "familyName": "dave",
            "name": "张三",
            "idTypeEntity": {
                "value": "护照",
                "key": 2
            },
            "certValidDate": "2117-02-01",
            "id": "5bf3ffee23445f6657232050",
            "category": 11,
            "email": ""
        },
        {
            "gender": 1,
            "frequentType": 2,
            "unitName": "测试1部门",
            "orgnazationFlag": false,
            "givenName": "hansins",
            "nationalityName": "中国",
            "selectedEmployeeId": "zhangsan-dev",
            "phoneNum": "17809089098",
            "ownerId": "zhangsan-dev",
            "idNumber": "2305434",
            "useType": 1,
            "birthDate": "1990-02-02",
            "employeeFlag": true,
            "thirdFrequentId": "2345647787",
            "nationality": "CN",
            "useNum": 0,
            "familyName": "dave",
            "name": "张三1",
            "idTypeEntity": {
                "value": "护照",
                "key": 2
            },
            "certValidDate": "2117-02-01",
            "id": "5bf4019023445f6657232052",
            "category": 11,
            "email": ""
        }, 
        {
            "gender": 1,
            "frequentType": 2,
            "unitName": "测试1部门",
            "orgnazationFlag": false,
            "givenName": "hansins",
            "nationalityName": "中国",
            "selectedEmployeeId": "zhangsan-dev",
            "phoneNum": "17800089098",
            "ownerId": "zhangsan-dev",
            "idNumber": "2305434",
            "useType": 1,
            "birthDate": "1990-02-02",
            "employeeFlag": true,
            "thirdFrequentId": "40iojr576we7654",
            "nationality": "CN",
            "useNum": 0,
            "familyName": "dave",
            "name": "张三2",
            "idTypeEntity": {
                "value": "护照",
                "key": 2
            },
            "certValidDate": "2117-02-01",
            "id": "5bfbb3d123445f2558d934d4",
            "category": 40,
            "email": ""
        }
    ]
}
```
