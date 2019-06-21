2.2.2.4 查询第三方员工信息

####接口说明
- 1.**最新接口**
- 2.不支持批量查询

请求方式|请求地址
----|---
POST|/open/api/third/employees/info


字段|名称|类型|必填|描述
-----|-----|----|----|----
access_token|api鉴权Token|string|Y|
sign|签名|string|Y|
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型 1:为第三方用户(需要使用第三方类型，不能使用分贝类型)
data |请求数据| jsonstring|Y|请求数据
data.employee\_id|需要查询人的id | string |Y|需要查询人员对应的ID
data.type|公司类型 | Integer |Y|公司类型,1:分贝公司ID 2:第三方公司ID（统一使用分贝公司ID，第三方公司ID暂未开放）





请求示例```

"access_token": "xxx.xxx.xxx",	
"timestamp": 123456789,
"employee_id":"12345678",
"employee_type":"1",
"sign": "jifejfwojelajflejf"
"data":	{
"employee_id":"faxxx12399004392293840274","type":1	
}

```

返回结果```
{
{
    "request_id": "BOWmahKWEgMfe7R017Kt",
    "code": 0,
    "msg": "success",
    "data": {
        "employee": {
            "id": "59bf74f423445f31bd64bc5c",//分贝ID
            "name": "张三",
            "email": "",
            "phone_num": "17080151667",
            "role": 2,
            "status": 1,
            "birth_date": "2016-10-20 00:00:00",
            "gender": 1,
            "pinyin": "zhang san ",
            "third_employee_id": "company_00003"//第三方用户ID
        },
        "air_policy": {//飞机权限
            "air_priv_flag": true,//是否允许订机票
            "air_verify_flag": false,//是否需要审批
            "air_rule_limit_flag": true,//是否限制规则
            "air_rule_id": "234567sfg",//规则id
            "unemployee_air": false,//限制非企业员工预定机票标识
            "exceed_buy_type": 2//1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
        },
        "hotel_policy": {//酒店权限权限

            "hotel_priv_flag": true,
            "hotel_verify_flag": false,
            "hotel_rule_limit_flag": false,
            "hotel_rule_id": "                        ",
            "unemployee_hotel": true,
            "exceed_buy_type": 2
        },
        "train_policy": {//火车权限

            "train_priv_flag": true,
            "train_verify_flag": false,
            "train_rule_limit_flag": false,
            "train_rule_id": "                        ",
            "unemployee_train": true,
            "exceed_buy_type": 1
        },
        "car_policy": {//用车权限

            "car_priv_flag": true,
            "rule_limit_flag": true,
            "rule_id": 138,
            "exceed_buy_flag": true,
            "exceed_buy_type": 1,//1：禁止 2：超规填写理由下单 3：超规个人支付
            "taxi_rule_name": "新建"
        },
        "mall_policy": {//采购权限

            "mall_priv_flag": true,
            "rule_limit_flag": true,
            "rule_id": "5a4b784323445f513ace5285",
            "exceed_buy_flag": false,是否可以超标下单
            "mall_rule_name": "18374"
        },
        "dinner_policy": {//用餐权限

            "dinner_priv_flag": true,
            "rule_limit_flag": false,
            "rule_id": "",
            "exceed_buy_flag": 1
        },
        "employee_certificate_beans": [//证件相关

            {
                "cert_type": 3,//证件类型1:身份证 2:护照 3:回乡证 4:台胞证
                "cert_no": "DHIWh4ncl5sod"
            }
        ]
    }
}
}
```
