2.2.1.2 添加第三方员工
####接口说明
- 1.**最新接口**
- 2.如果存在部门概念，保存到部门下面,采用部门ID进行添加
- 3.添加时可以根据不同的需求进行权限的开关操作(包括机票，用车，火车，酒店，采购，用餐权限，可以进行差异化的权限分配

| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/auth/third/user/batch/org_save 


请求参数

 字段 | 名称 | 类型 | 必填 | 描述 |
 --- | --- | --- | --- | --- |
 timestamp | 时间戳 | long | Y | 13位时间戳 
 access\_token | token | string | Y | 登录 token 
 employee\_id | 操作人id | string | N | 操作人id,调用接口人 id 
 data | 请求数据 | jsonstring | Y 
 data.employee\_list | 员工信息 | jsonarray | Y 
 data.employee\_list.name | 员工姓名 | string | Y |张三
 data.employee\_list.phone | 员工手机号 | string | Y |17902029298
 data.employee\_list.third_org_unit_id | 员工组织ID，需要与公司ID一样  |string | Y |lk98eow9jisdj87
 data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y |jskngla87j7ei9ej
 employee\_list.air_policy | 飞机权限 | jsonobject | Y 
air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean | Y |false
air_policy.air_priv_flag | 是否允许订机票| boolean | Y |false
air_policy.air_verify_flag | 是否需要审批| boolean | Y |false
air_policy.air_rule_limit_flag | 是否限制规则| boolean | Y |当为true时，规则ID为空。当为false时，规则ID空串
air_policy.air_rule_id |规则id| string | Y |false
air_policy.exceed_buy_type | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.intl_air_policy | 国际飞机权限 | jsonobject | Y 
intl_air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean |Y|false
intl_air_policy.air_priv_flag | 是否允许订机票| boolean | Y |false
intl_air_policy.air_verify_flag | 是否需要审批| boolean | Y |false
intl_air_policy.air_rule_limit_flag | 是否限制规则| boolean | Y |当为true时，规则ID为空。当为false时，规则ID空串
intl_air_policy.air_rule_id |规则id| string | Y |false
intl_air_policy.exceed_buy_type | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.hotel_policy | 酒店权限 | jsonobject | Y 
hotel_policy.unemployee_hotel | 限制非企业员工预定酒店标识| boolean | Y |false
hotel_policy.hotel_priv_flag | 是否允许订酒店| boolean | Y |false
hotel_policy.hotel_verify_flag |是否需要审批| boolean | Y |false
hotel_policy.hotel_rule_limit_flag | 是否限制规则| boolean | Y |false
hotel_policy.hotel_rule_id | 规则id| string | Y |575263e982f880a6d686ce11
hotel_policy.exceed_buy_type | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)|
employee\_list.train_policy | 火车权限| jsonobject | Y 
train_policy.unemployee_train | 限制非企业员工预定火车标识| boolean | Y |false
train_policy.train_priv_flag | 是否允许订火车票| boolean | Y |false
train_policy.train_verify_flag | 是否需要审批| boolean | Y |false
train_policy.train_rule_limit_flag |是否限制规则| boolean | Y |false
train_policy.train_rule_id | 规则id| string | Y |false
train_policy.exceed_buy_type | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.car_policy | 用车权限| jsonobject | Y 
car_policy.car_priv_flag | 限制非企业员工用车权限标识| boolean | Y |false
car_policy.rule_limit_flag | 是否允许打车| boolean | Y |false
car_policy.rule_id | 规则id| integer | Y |45
car_policy.allowShuttle | 用车接送机权限| boolean | Y |false
car_policy.exceed_buy_type | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.mall_policy | 采购权限| jsonobject | Y 
mall_policy.mall_priv_flag | 限制非企业员工采购标识| boolean | Y |false
mall_policy.rule_limit_flag | 是否允许采购| boolean | Y |false
mall_policy.rule_id | 规则id| string | Y |false
mall_policy.exceed_buy_flag | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.dinner_policy | 用餐权限| jsonobject | Y 
dinner_policy.dinner_priv_flag | 限制非企业员工用餐标识| boolean | Y |false
dinner_policy.rule_limit_flag | 是否允许用餐| boolean | Y |false
dinner_policy.rule_id | 规则id| string | Y |false
dinner_policy.exceed_buy_flag | 超规则下单| integer | Y |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)








请求示例

```
{ "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id":784kuf873jf9834uiy98e"",
  "data":
  {  
    "employee_list":[
    {
      "name":"张5s",
      "phone":"13718432812",
      "third_org_unit_id":"5747fbc10f0e60e0709d8d7d",
      "third_employee_id":"57ab054c2528226a805bd5e1",
      "air_policy": { //飞机权限
          "unemployee_air": false, //限制非企业员工预定机票标识
          "air_priv_flag": false, //是否允许订机票
          "air_verify_flag": true, //是否需要审批
          "air_rule_limit_flag": true, //是否限制规则
          "air_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
      },
      "intl_air_policy": { //国际飞机权限
          "unemployee_air":false,   //限制非企业员工预定机票标识
          "air_priv_flag": false, //是否允许订机票
          "air_verify_flag": true, //是否需要审批
          "air_rule_limit_flag": true, //是否限制规则
          "air_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "hotel_policy": { //酒店权限
      "unemployee_hotel": false, //限制非企业员工预定酒店标识
      "hotel_priv_flag": true,
      "hotel_verify_flag": false,
      "hotel_rule_limit_flag": true, //是否限制规则
      "hotel_rule_id": "575263e982f880a6d686ce11", //规则id
      "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "train_policy": { //火车权限
        "unemployee_train": false, //限制非企业员工预定火车标识
        "train_priv_flag": true,
        "train_verify_flag": false,
        "train_rule_limit_flag": true, //是否限制规则
        "train_rule_id": "575263e982f880a6d686ce11", //规则id
        "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "car_policy": { //用车权限，APP端添加员工时不能上送该key,修改时续上送
        "car_priv_flag": true,
        "rule_limit_flag": true,
        "rule_id": 2, //规则id
        "exceed_buy_type": 1, //1：禁止 2：超规填写理由下单 3：超规个人支付
        "allowShuttle": false //用车接送机权限
    },
    "mall_policy": { //采购权限，APP端添加员工时不能上送该key,修改时续上送
          "mall_priv_flag": true,
          "rule_limit_flag": true,
          "rule_id": "ofaijwf", //规则id
          "exceed_buy_flag": false //是否可以超标下单
    },
    "dinner_policy": { //用餐权限，APP端添加员工时不能上送该key,修改时续上送
          "dinner_priv_flag": true,
          "rule_limit_flag": true,
          "rule_id": "ofaijwf", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    }
      },
      {
    "name":"张5",
    "phone":"13718432992",
    "org_unit_id":"5747fbc10f0e60e0709d8d7d",
    "third_employee_id":"57ab054c2528226a805bd500",
    "air_policy": { //飞机权限
          "unemployee_air": false, //限制非企业员工预定机票标识
          "air_priv_flag": false, //是否允许订机票
          "air_verify_flag": true, //是否需要审批
          "air_rule_limit_flag": true, //是否限制规则
          "air_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "intl_air_policy": { //国际飞机权限
        "unemployee_air":false,   //限制非企业员工预定机票标识
        "air_priv_flag": false, //是否允许订机票
        "air_verify_flag": true, //是否需要审批
        "air_rule_limit_flag": true, //是否限制规则
        "air_rule_id": "575263e982f880a6d686ce11", //规则id
        "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "hotel_policy": { //酒店权限
          "unemployee_hotel": false, //限制非企业员工预定酒店标识
          "hotel_priv_flag": true,
          "hotel_verify_flag": false,
          "hotel_rule_limit_flag": true, //是否限制规则
          "hotel_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "train_policy": { //火车权限
          "unemployee_train": false, //限制非企业员工预定火车标识
          "train_priv_flag": true,
          "train_verify_flag": false,
          "train_rule_limit_flag": true, //是否限制规则
          "train_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "car_policy": { //用车权限，APP端添加员工时不能上送该key,修改时续上送
          "car_priv_flag": true,
          "rule_limit_flag": true,
          "rule_id": 2, //规则id
          "exceed_buy_type": 1, //1：禁止 2：超规填写理由下单 3：超规个人支付
          "allowShuttle": false //用车接送机权限
    },
    "mall_policy": { //采购权限，APP端添加员工时不能上送该key,修改时续上送
          "mall_priv_flag": true,
          "rule_limit_flag": true,
          "rule_id": "ofaijwf", //规则id
          "exceed_buy_flag": false //是否可以超标下单
    },
    "dinner_policy": { //用餐权限，APP端添加员工时不能上送该key,修改时续上送
          "dinner_priv_flag": true,
          "rule_limit_flag": true,
          "rule_id": "ofaijwf", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    }
      }
    ]  
 }
}
```

返回结果

```
{
   "request_id": "LaZNvBntsBD20nJ7ekgn",
   "code": 0,
   "msg": "success"
}
```

```
{
    "request_id": "MzWkSvZ3sVC2FYg9bCLt",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "59ce56d02798633485e206a9",
                "phone": "17080151661",
                "name": "塞外-test",
                "thirdEmployeeId": "ddd-test-A",
                "errorMsg": "第三方用户ID已经被绑定"
            }
        ]
    }
}

```


```
{
    "request_id": "zgubWmjt4y9c5AWcOwgs",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "59df06662798635263b8414c",
                "phone": "25777059211",
                "name": "IDG-has888",
                "thirdEmployeeId": "IDG-888s0lll",
                "errorMsg": "手机号已经存在，请使用其他手机号"
            },
            {
                "companyId": "59df06662798635263b8414c",
                "phone": "18777198765",
                "name": "IDG-h999009",
                "thirdEmployeeId": "IDG-h99k4lll",
                "errorMsg": "手机号已经存在，请使用其他手机号"
            }
        ]
    }
}




{
    "request_id": "FqVKD698g0SdA7sr6O5i",
    "code": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "5747fbc10f0e60e0709d8d7d",
                "phone": "13146894449",
                "name": "杨六郎",
                "thirdEmployeeId": "100991",
                "errorMsg": "部门信息参数不正确"
            }
        ]
    }
}

```