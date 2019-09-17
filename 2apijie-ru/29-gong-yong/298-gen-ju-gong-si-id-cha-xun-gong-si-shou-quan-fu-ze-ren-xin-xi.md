2.9.8 根据公司ID查询公司授权负责人信息
####接口说明
- 1.**最新接口**
- 2.根据公司ID查询公司授权负责人相关信息


| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/third/company/admin |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id |
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y ||
| data.company_id | 公司ID | string | Y |公司ID


请求示例：

```

"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
"company_id":"5747fbc10f0e60e0709d8d7d"
}

```

响应结果：

```
{
    "request_id": "jpG9zlwrGY72dFAXCEaC",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "employee": {
            "id": "59b8acf023445f70c3eaef80",
            "thirdEmployeeId": "third_jianren",
            "name": "谷大侠",
            "email": "daxia.gu@fenbeitong.com",
            "phone_num": "13911381353",
            "avatar_url": "http://image.fenbeitong.com/employee/2019/03/18/59b8acf023445f70c3eaef80/5c8f504a979d960e2008f3c3.",
            "role": 6,
            "status": 1,
            "birth_date": "1984-12-24 00:00:00",
            "gender": 1,
            "pinyin": "gu jian bo",
            "org_unit_id": "5bf2651123445f5335612351",
            "third_org_id": "third_privilege_test",
            "org_unit_name": "北京分贝金服科技有限公司/蛋部门",
            "org_name": "蛋部门",
            "employee_number": ""
        },
        "employeeCertificateBeans": [
            {
                "cert_type": 1,
                "cert_no": "110101198512222019"
            }
        ],
        "air_policy": {
            "air_priv_flag": true,
            "air_other_flag": true,
            "air_verify_flag": false,
            "air_rule_limit_flag": true,
            "air_rule_id": "5a967a1923445f638e570522",
            "unemployee_air": true,
            "exceed_buy_type": 3,
            "air_rule_name": "蛋",
            "oneself_limit": 0,
            "air_priv_type": 3,
            "switch_flag": true
        },
        "intl_air_policy": {
            "air_priv_flag": true,
            "air_other_flag": true,
            "air_verify_flag": false,
            "air_rule_limit_flag": false,
            "unemployee_air": true,
            "exceed_buy_type": 1,
            "oneself_limit": 0,
            "air_priv_type": 3,
            "switch_flag": true
        },
        "hotel_policy": {
            "hotel_priv_flag": true,
            "hotel_other_flag": false,
            "hotel_verify_flag": true,
            "hotel_rule_limit_flag": false,
            "unemployee_hotel": false,
            "exceed_buy_type": 1,
            "oneself_limit": 1,
            "hotel_priv_type": 1,
            "switch_flag": true,
            "personal_pay": false
        },
        "train_policy": {
            "train_priv_flag": true,
            "train_other_flag": true,
            "train_verify_flag": false,
            "train_rule_limit_flag": false,
            "unemployee_train": true,
            "exceed_buy_type": 1,
            "oneself_limit": 0,
            "train_priv_type": 3,
            "switch_flag": true
        },
        "car_policy": {
            "car_priv_flag": true,
            "rule_limit_flag": true,
            "rule_id": 211,
            "exceed_buy_flag": false,
            "exceed_buy_type": 1,
            "taxi_rule_name": "宋宋用车",
            "personal_pay": false,
            "rule_infos": [
                {
                    "type": {
                        "key": 2,
                        "value": "申请用车"
                    },
                    "rule_info": [
                        {
                            "rule_id": "990",
                            "rule_name": "吴冰测试用车的"
                        }
                    ]
                },
                {
                    "type": {
                        "key": 1,
                        "value": "用车"
                    },
                    "rule_info": [
                        {
                            "rule_id": "211",
                            "rule_name": "宋宋用车"
                        }
                    ]
                }
            ],
            "oldVersion": false
        },
        "mall_policy": {
            "mall_priv_flag": true,
            "rule_limit_flag": true,
            "rule_id": "5b023e1923445f162fbf9b8f",
            "exceed_buy_flag": true,
            "mall_rule_name": "测试自营商品"
        },
        "dinner_policy": {
            "dinner_priv_flag": true,
            "rule_limit_flag": false,
            "exceed_buy_flag": 1
        },
        "takeaway_policy": {
            "takeaway_priv_flag": true,
            "takeaway_other_flag": false,
            "unemployee_takeaway": false,
            "takeaway_rule_limit_flag": true,
            "takeaway_rule_id": 94,
            "exceed_buy_type": 1,
            "personal_pay": false,
            "takeaway_order_verify_flag": false
        },
        "dinners_policy": {
            "rule_priv_flag": true,
            "rule_limit_flag": false,
            "dinner_policy": {
                "dinner_priv_flag": true,
                "rule_limit_flag": false,
                "exceed_buy_flag": 1
            },
            "meishi_policy": {
                "meishi_priv_flag": true,
                "rule_limit_flag": false,
                "exceed_buy_type": 1,
                "meishi_rule": 2,
                "company_id": "5747fbc10f0e60e0709d8d7d",
                "personal_pay": false
            }
        },
        "shansong_policy": {
            "shansong_priv_flag": true
        }
    }
}


```









