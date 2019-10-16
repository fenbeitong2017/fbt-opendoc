2.2.6.3.根据公司ID查询公司授权负责人信息
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/company/admin


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|4ergfdsawesf
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|请求数据
data.company_id|公司ID|string|Y|5747fbc10f0e60e0709d8d7d


 请求示例:
 
 ```

  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": "12345678",
  "employee_type":"0",
  "sign": "jifejfwojelajflejf",
  "data": {"company_id":"5cc1598623445f612c73b27a"}

```

返回结果

```
{
  "request_id": "QdMXjd1ilI3ZOdSI85w8",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": {
    "employee": {
      "id": "59bf74f423445f31bd64bc5c",
      "thirdEmployeeId": "manager_third",
      "name": "张三",
      "email": "san.zhang@fenbeitong.com",
      "phone_num": "17710385317",
      "role": 6,
      "status": 1,
      "birth_date": "1997-05-23 00:00:00",
      "gender": 1,
      "pinyin": "zhang san",
      "org_unit_id": "5cc1598623445f612c73b27a",
      "third_org_id": "dingecf942c070fe83f435c2f4657eb6378f",
      "org_unit_name": "分贝通科技有限公司",
      "org_name": "分贝通科技有限公司",
      "employee_number": ""
    },
    "employeeCertificateBeans": [
      {
        "cert_type": 2,
        "cert_no": "22222222222"
      }
    ],
    "air_policy": {
      "air_priv_flag": true,
      "air_other_flag": false,
      "air_verify_flag": false,
      "air_rule_limit_flag": false,
      "unemployee_air": false,
      "exceed_buy_type": 1,
      "oneself_limit": 0,
      "air_priv_type": 1,
      "switch_flag": true
    },
    "intl_air_policy": {
      "air_priv_flag": true,
      "air_other_flag": true,
      "air_verify_flag": false,
      "air_rule_limit_flag": false,
      "unemployee_air": false,
      "exceed_buy_type": 1,
      "oneself_limit": 0,
      "air_priv_type": 2,
      "switch_flag": true
    },
    "hotel_policy": {
      "hotel_priv_flag": true,
      "hotel_other_flag": true,
      "hotel_verify_flag": false,
      "hotel_rule_limit_flag": true,
      "hotel_rule_id": "5ce60d6a23445f3985ca2666",
      "unemployee_hotel": true,
      "exceed_buy_type": 2,
      "oneself_limit": 0,
      "hotel_priv_type": 3,
      "switch_flag": true,
      "hotel_rule_name": "测试酒店规则",
      "personal_pay": false
    },
    "train_policy": {
      "train_priv_flag": true,
      "train_other_flag": true,
      "train_verify_flag": false,
      "train_rule_limit_flag": false,
      "unemployee_train": false,
      "exceed_buy_type": 1,
      "oneself_limit": 0,
      "train_priv_type": 2,
      "switch_flag": true
    },
    "car_policy": {
      "car_priv_flag": true,
      "rule_limit_flag": false,
      "exceed_buy_flag": false,
      "exceed_buy_type": 1,
      "personal_pay": false,
      "rule_infos": [
        {
          "type": {
            "key": 1,
            "value": "用车"
          },
          "rule_info": []
        },
        {
          "type": {
            "key": 2,
            "value": "申请用车"
          },
          "rule_info": []
        }
      ],
      "oldVersion": false
    },
    "mall_policy": {
      "mall_priv_flag": true,
      "rule_limit_flag": true,
      "rule_id": "5d08954e23445f65e153bcb0",
      "exceed_buy_flag": true,
      "mall_rule_name": "测试采购规则"
    },
    "dinner_policy": {
      "dinner_priv_flag": false,
      "rule_limit_flag": false,
      "exceed_buy_flag": 1
    },
    "takeaway_policy": {
      "takeaway_priv_flag": true,
      "takeaway_other_flag": false,
      "unemployee_takeaway": false,
      "takeaway_rule_limit_flag": true,
      "takeaway_rule_id": 151,
      "exceed_buy_type": 2,
      "personal_pay": false,
      "takeaway_order_verify_flag": false
    },
    "dinners_policy": {
      "rule_priv_flag": false,
      "rule_limit_flag": false,
      "dinner_policy": {
        "dinner_priv_flag": false,
        "rule_limit_flag": false,
        "exceed_buy_flag": 1
      },
      "meishi_policy": {
        "meishi_priv_flag": false,
        "rule_limit_flag": false,
        "exceed_buy_type": 1,
        "meishi_rule": 1,
        "company_id": "5cc1598623445f612c73b27a",
        "personal_pay": false
      }
    },
    "shansong_policy": {
      "shansong_priv_flag": false
    }
  }
}


```
