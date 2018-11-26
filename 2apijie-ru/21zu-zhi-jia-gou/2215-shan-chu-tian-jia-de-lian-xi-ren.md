2.2.15 删除添加的乘车(机)，入住人
####接口说明
- 1.**最新接口**
- 2.支持批量删除


请求方式|请求地址
----|---
POST|/open/api/third/frequent/del


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
data.id_list|第三方联系人ID| jsonarray |Y|需要删除的ID
data.company_id|公司ID| string |Y|58734b2e5f281a41b304181f
data.owner_id|当前登录人| string |Y|为第三方用户ID

 请求示例:
 
 ```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": { "type" :2, 
"frequent_id_type":2, 
"company_id":"5747fbc10f0e60e0709d8d7d",  
"owner_id":"zhangsan-dev",    
"id_list":["40iojr576we7654"]
}

}
```

返回结果

```
{
    "request_id": "bua8KJDZdBpJOHB5zWjL",
    "code": 0,
    "type": 0,
    "msg": "success"
}


{
    "request_id": "GffkdAlTOVlXnMEuwb1A",
    "code": 600,
    "msg": "员工ID数据有误，请检查参数"
}
```
