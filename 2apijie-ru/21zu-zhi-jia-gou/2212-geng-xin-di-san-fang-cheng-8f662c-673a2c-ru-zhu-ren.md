 2.2.12 更新第三方乘车，机，入住人
####接口说明
- 1.**最新接口**
- 2.不支持批量添加


请求方式|请求地址
----|---
POST|/open/api/third/frequent/update


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
data.frequent_id_type|第三方联系人ID类型|integer |Y|1:使用分贝联系人ID 2:第三方联系人ID
data.id|第三方联系人ID|integer |Y|58734b2e5f281a41b304181f，添加时返回的为分贝通ID;添加时添加字段third_frequent_id为第三方ID
data.name|姓名| string |Y|张三
data.gender|性别| string |Y|1:男2:女 当idType为1时不需要传递，其他类型需要传递
data.birth_date|出生年月| string |N|1990-02-02 当id_type为1时不需要传递，其他类型需要传递
data.email|邮箱| string |N|san.zhang@fenbeitong.com
data.phone_num|手机号| string |Y|17089078090
data.employee_flag|是否为企业员工| string |N|如果是从组织架构入口进入则为true,反之则为false
data.selected_employee_id|实际选择的人|string |Y|//同行人在组织架构的id ，employee_flag为false,不传递。为false时是从非组织架构选择添加的人员
data.id_number|身份证件号| string |Y|57689098
data.id_type|证件类型| string |integer|1.身份证 2.护照 3.回乡证 4.台胞证 5.港澳通行证 6.大陆居民往来台湾通行证
data.category|业务类型| integer |N|当frequent_type为1时，酒店:11,其它:0,当frequentType为2时，国际机票传:40,不进行实际业务处理
data.family_name|英文名| string |N|frequent_type=2时必填，必须使用拼音或者英文
data.given_name|英文姓| string |N|frequent_type=2时必填，必须使用拼音或者英文
data.cert_valid_date|证件有效期| string |N|2017-02-01 frequent_type=2时必填
data.nationality|国籍|string |N|CN 根据获取国家列表接口查询
data.nationality_name|国籍名称| string |N|中国  根据获取国家列表接口查询
data.frequent_type|场景类型| string |Y|1:国内 2:国际 国际机票使用2
data.company_id|公司ID| string |Y|58734b2e5f281a41b304181f
data.owner_id|当前登录人| string |Y|为第三方用户ID
data.use_type|因公因私标识| integer |Y|1：因公



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
    "request_id": "9CRe5SOw2yQCaIBdxDyr",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "id": "5bfb899c23445f2558d934b8"
    }
}


{
    "request_id": "cbXe80VZJvbIH3PQnsJ8",
    "code": 600,
    "msg": "该联系人信息已存在！40iojr576we7654"
}


{
    "request_id": "6SAgFcefCXMh2GpqAYNw",
    "code": 600,
    "msg": "国内机票联系人类型错误！"
}

```
