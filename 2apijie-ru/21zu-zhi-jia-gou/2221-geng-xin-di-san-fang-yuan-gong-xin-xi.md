2.2.2.2 更新第三方员工

####接口说明
- 1.**最新接口**
- 2.支持批量更新,该接口可以对用户的权限和规则进行更新
- 3.字段说明:air_rule_id:当air_priv_flag和air_rule_limit_flag为true时,air_rule_id必须指定规则ID,进行绑定相应的规则。当air_priv_flag为false时，代表业务权限关闭，其他字段都设置为相应的不可用状态即可。其他业务线字段设置相同，参照机票权限规则即可



请求方式|请求地址
----|---
POST|/open/api/third/employees/v2/update


请求参数

字段 | 名称 | 类型 | 必填 | 描述 |
--- | --- | --- | --- | --- |
access_token|api鉴权Token|string|Y|
sign|签名|string|Y|907943uf
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data| 请求数据 | jsonstring | Y | 请求数据
data.employee\_list | 员工信息 | jsonarray | Y |员工请求数据
data.employee\_list.name | 员工姓名 | string | Y |张三
data.employee\_list.phone | 员工手机号 | string | Y |16090190901
data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y |34567
data.employee\_list.third\_org\_unit\_id | 部门ID| string | Y |员工部门ID,874890934ghgdytuyjg
data.employee\_list.org\_unit\_name | 部门名称| string | N |员工部门名称，分贝通科技有限公司/研发部/后端服务(可以不填)
| data.employee\_list.employee_number | 员工工号 | string | Y | fbttest00001 |
data.employee\_list.role |员工权限| integer | N |员工权限,2:普通管理员 3:普通员工(如果不填则默认为管理后台的权限)
employee\_list.air_policy | 飞机权限 | jsonobject | N |飞机请求数据(如果不填则默认为管理后台的权限)
air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean | N |false
air_policy.air_priv_flag | 是否允许订机票| boolean | N |false
air_policy.air_verify_flag | 是否需要审批| boolean | N |false
air_policy.air_rule_limit_flag | 是否限制规则| boolean | N |true
air_policy.air_rule_id |规则id| string | N |575263e982f880a6d686ce11
air_policy.exceed_buy_type | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作) 2:超规填写理由下单(当有规则限制时，如果超出规则 的规定可以需下单,但是需要填写超规下单的理由) 3:超规需要提交费用审批(如果有审批的概念)
employee\_list.intl_air_policy | 国际飞机权限 | jsonobject | N |国际机票请求数据(如果不填则默认为管理后台的权限)
intl_air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean |N|false
intl_air_policy.air_priv_flag | 是否允许订机票| boolean | N |false
intl_air_policy.air_verify_flag | 是否需要审批| boolean | N |false
intl_air_policy.air_rule_limit_flag | 是否限制规则| boolean | N |true
intl_air_policy.air_rule_id |规则id| string | N |575263e982f80987654321
intl_air_policy.exceed_buy_type | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作)2:超规填写理由下单(当有规则限制时,如果超出规则 的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)
employee\_list.hotel_policy | 酒店权限 | jsonobject | N |酒店请求数据 (如果不填则默认为管理后台的权限)
hotel_policy.unemployee_hotel | 限制非企业员工预定酒店标识| boolean | N |false
hotel_policy.hotel_priv_flag | 是否允许订酒店| boolean | N |false
hotel_policy.hotel_verify_flag |是否需要审批| boolean | N |false
hotel_policy.hotel_rule_limit_flag | 是否限制规则| boolean | N |false
hotel_policy.hotel_rule_id | 规则id| string | N |575263e982f880a6d686ce11
hotel_policy.exceed_buy_type | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作) 2:超规填写理由下单(当有规则限制时,如果超出规则 的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)
employee\_list.train_policy | 火车权限| jsonobject | N |火车|火车请求数据 (如果不填则默认为管理后台的权限)
train_policy.unemployee_train | 限制非企业员工预定火车标识| boolean | N |false
train_policy.train_priv_flag | 是否允许订火车票| boolean | N |false
train_policy.train_verify_flag | 是否需要审批| boolean | N |false
train_policy.train_rule_limit_flag |是否限制规则| boolean | N |false
train_policy.train_rule_id | 规则id| string | N |575263e982f882134567
train_policy.exceed_buy_type | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作)2:超规填写理由下单(当有规则限制时,如果超出规则的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)
employee\_list.car_policy | 用车权限| jsonobject | N |用车请求数据  (如果不填则默认为管理后台的权限)
car_policy.car_priv_flag | 限制非企业员工用车权限标识| boolean | N |false
car_policy.rule_limit_flag | 是否允许打车| boolean | N |false
car_policy.rule_id | 规则id| integer | N |2
car_policy.allowShuttle | 用车接送机权限| boolean | N |false
car_policy.exceed_buy_type | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作)2:超规填写理由下单(当有规则限制时,如果超出规则 的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)
employee\_list.mall_policy | 采购权限| jsonobject | N |采购请求数据  (如果不填则默认为管理后台的权限)
mall_policy.mall_priv_flag | 限制非企业员工采购标识| boolean | N |false
mall_policy.rule_limit_flag | 是否允许采购| boolean | N |false
mall_policy.rule_id | 规则id| string | N |ofaijwf
mall_policy.exceed_buy_flag | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作)2:超规填写理由下单(当有规则限制时,如果超出规则 的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)
employee\_list.dinner_policy | 用餐权限| jsonobject | N |用餐请求数据 (如果不填则默认为管理后台的权限)
dinner_policy.dinner_priv_flag | 限制非企业员工用餐标识| boolean | N |false
dinner_policy.rule_limit_flag | 是否允许用餐| boolean | N |false
dinner_policy.rule_id | 规则id| string | N |ofai9876787
dinner_policy.exceed_buy_flag | 超规则下单| integer | N |1:禁止(如果超出规则,则不允许下单操作)2:超规填写理由下单(当有规则限制时,如果超出规则 的规定可以需下单,但是需要填写超规下单的理由)3:超规需要提交费用审批(如果有审批的概念)










请求示例

```
 "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id":"784kuf873jf9834uiy98e",
  "data":
  {  
    "employee_list":[
    {
      "name":"张5s",
      "phone":"13718432812",
      "third_org_unit_id":"5747fbc10f0e60e0709d8d7d",
      "third_employee_id":"57ab054c2528226a805bd5e1",
      "employee_number":"fbttest000001",
      "role":3,
      "air_policy": { //飞机权限
          "unemployee_air": false, //限制非企业员工预定机票标识
          "air_other_flag": false, //是否允许为其他员工订机票     // 2.0.1新增
          "air_priv_flag": false, //是否允许订机票
          "air_verify_flag": true, //是否需要审批
          "air_rule_limit_flag": true, //是否限制规则
          "air_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
      },
      "intl_air_policy": { //国际飞机权限
          "unemployee_air":false,   //限制非企业员工预定机票标识
          "air_other_flag": false, //是否允许为其他员工订机票     // 2.0.1新增
          "air_priv_flag": false, //是否允许订机票
          "air_verify_flag": true, //是否需要审批
          "air_rule_limit_flag": true, //是否限制规则
          "air_rule_id": "575263e982f880a6d686ce11", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "hotel_policy": { //酒店权限
      "unemployee_hotel": false, //限制非企业员工预定酒店标识
      "hotel_other_flag": true, //是否允许为其他员工预定酒店      // 2.0.1新增
      "hotel_priv_flag": true,
      "hotel_verify_flag": false,
      "hotel_rule_limit_flag": true, //是否限制规则
      "hotel_rule_id": "575263e982f880a6d686ce11", //规则id
      "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    },
    "train_policy": { //火车权限
        "unemployee_train": false, //限制非企业员工预定火车标识
        "train_other_flag": true, //是否允许为其他员工预定火车      // 2.0.1新增
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
          "personal_pay" : true //个人支付开关 2.1.0 新增
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
          "rule_id": "ofaisfasjwf", //规则id
          "exceed_buy_type": 1 //1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
    }
      }
    ]  
 }

```



返回结果


```
{
"request_id": "LaZNvBntsBD20nJ7ekgn",
"code": 0,
"msg": "success",
"data": {
}
}




{
"request_id": "LaZNvBntsBD20nJ7ekgn",
"code": 0,
"msg": "success",
"data": {
"result": [
{
"name": "张三(姓名)",
"phone": "13718432817（手机号）",
"companyId": "57ab054c2528226a805bd5e1(公司id)",
"thirdEmployeeId": "57ab054c2528226a805bd5e1(第三方用户id)",
"errorMsg": "手机号已存在"
}
]
}
}


{
    "request_id": "piVFVuQqyE0I9CFDWzY7",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "result": [
            {
                "companyId": "5747fbc10f0e60e0709d8d7d",
                "phone": "17080151666",
                "name": "谷健波",
                "thirdEmployeeId": "gujianbo-123",
                "errorMsg": "授权负责人手机号不能修改"
            }
        ]
    }
}


errorMsg详细说明:
会存在一下几种情况
1."手机号已存在"
2."用户不存在"
3."第三方ID不存在"
4."授权负责人手机号不能修改"
5."系统修改异常，请稍后重试！"
6."修改规则接口异常!"


```