2.2.1.2 添加第三方员工
####接口说明
- 1.**最新接口**
- 2.如果存在部门概念，保存到部门下面,采用部门ID进行添加
- 3.支持批量添加，批量不能大于200，因添加人员会关联相关各场景权限信息，若数量过大会导致添加返回超时
- 4.添加时可以根据不同的需求进行权限的开关操作(包括国内机票，国际机票，用车，火车，酒店，采购，用餐,外卖权限，可以进行差异化的权限分配
- 5.字段说明:air_rule_id:当air_priv_flag和air_rule_limit_flag为true时,air_rule_id必须指定规则ID,进行绑定相应的规则。当air_priv_flag为false时，代表业务权限关闭，其他字段都设置为相应的不可用状态即可。其他业务线字段设置相同，参照机票权限规则即可

| 请求方式 | 请求地址 |
| --- | --- |
| POST | /open/api/auth/third/user/batch/org_save 


请求参数

 字段 | 名称 | 类型 | 必填 | 描述 |
 --- | --- | --- | --- | --- |
 timestamp | 时间戳 | long | Y | 13位时间戳 
 access\_token | token | string | Y | 登录 token 
 employee\_id | 操作人id | string | N | 操作人id,调用接口人 id 
 data | 请求数据 | jsonstring | Y |请求数据
 data.employee\_list | 员工信息 | jsonarray | Y |员工所有信息数据
 data.employee\_list.name | 员工姓名 | string | Y |张三
 data.employee\_list.phone | 员工手机号 | string | Y |17902029298
 data.employee\_list.role | 员工权限 | integer | N |员工权限,2:普通管理员 3:普通员工(若不填则默认为管理后台的普通员工权限)
 data.employee\_list.third_org_unit_id | 员工组织ID |string | N |部门ID,当部门为公司时，可以不填写。当为部门时则必填
 data.employee_list.org_unit_name|部门名称(公司名称)|string|N|当人员添加到公司下时必填，需填写公司名称
 data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y |确保唯一性，例如，员工工号，系统登录名
 employee\_list.air_policy | 飞机权限 | jsonobject | N |机票数据
air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean | N |false
air_policy.air_priv_flag | 是否允许订机票| boolean | N |false
air_policy.air_verify_flag | 是否需要审批| boolean | N |false
air_policy.air_other_flag | 是否允许为其他员工订机票| boolean | N |false
air_policy.air_rule_limit_flag | 是否限制规则| boolean | N |true
air_policy.refund_ticket_type | 退订控制| integer | N |0：不限制 1:填写原因 2:提交审批
air_policy.changes_ticket_type | 改签控制| integer | N |0：不限制 1:填写原因 2:提交审批
air_policy.air_rule_id |规则id| string | N |575263e982f880a6d686ce11
air_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.intl_air_policy | 国际飞机权限 | jsonobject | N |国际机票数据
intl_air_policy.unemployee_air | 限制非企业员工预定机票标识| boolean |N|false
intl_air_policy.air_priv_flag | 是否允许订机票| boolean | N |false
intl_air_policy.air_verify_flag | 是否需要审批| boolean | N |false
intl_air_policy.air_other_flag | 是否允许为其他员工订机票| boolean | N |false
intl_air_policy.air_rule_limit_flag | 是否限制规则| boolean | N |true
intl_air_policy.refund_ticket_type | 退订控制| integer | N |0：不限制 1:填写原因 2:提交审批
intl_air_policy.changes_ticket_type | 改签控制| integer | N |0：不限制 1:填写原因 2:提交审批
intl_air_policy.air_rule_id |规则id| string | N |575263e982f880a6d686ce11
intl_air_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.hotel_policy | 酒店权限 | jsonobject | N |酒店数据
hotel_policy.unemployee_hotel | 限制非企业员工预定酒店标识| boolean | N |false
hotel_policy.hotel_priv_flag | 是否允许订酒店| boolean | N |false
hotel_policy.hotel_verify_flag |是否需要审批| boolean | N |false
hotel_policy.hotel_other_flag | 是否允许为其他员工订酒店| boolean | N |false
hotel_policy.hotel_rule_limit_flag | 是否限制规则| boolean | N |false
hotel_policy.refund_ticket_type | 退订控制| integer | N |0：不限制 1:填写原因 2:提交审批
hotel_policy.hotel_rule_id | 规则id| string | N |575263e982f880a6d686ce11
hotel_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.train_policy | 火车权限| jsonobject | N |火车数据
train_policy.unemployee_train | 限制非企业员工预定火车标识| boolean | N |false
train_policy.train_priv_flag | 是否允许订火车票| boolean | N |false
train_policy.train_verify_flag | 是否需要审批| boolean | N |false
train_policy.train_other_flag | 是否允许为其他员工订火车| boolean | N |false
train_policy.train_rule_limit_flag |是否限制规则| boolean | N |false
train_policy.refund_ticket_type | 退订控制| integer | N |0：不限制 1:填写原因 2:提交审批
train_policy.changes_ticket_type | 改签控制| integer | N |0：不限制 1:填写原因 2:提交审批
train_policy.train_rule_id | 规则id| string | N|ssfl89u3487yihkre
train_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.car_policy | 用车权限| jsonobject | N |用车数据
car_policy.car_priv_flag | 是否允许员工用车权限标识| boolean | N |false
car_policy.rule_limit_flag | 是否允许打车| boolean | N |false
car_policy.rule_ids | 规则id集合| jsonarray | N |rule_limit_flag=true时 规则id不可为空,包括用车规则和审批用车规则ID
car_policy.allow_shuttle | 用车接送机权限| boolean | N |false
car_policy.personal_pay|个人支付开关  |boolean|N|false
car_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.mall_policy | 采购权限| jsonobject | N |采购数据
mall_policy.mall_priv_flag | 是否允许员工采购标识| boolean | N |false
mall_policy.rule_limit_flag | 是否允许采购| boolean | N |false
mall_policy.rule_id | 规则id| string | N |ofaijwf
mall_policy.exceed_buy_flag | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由） 3：超规需要提交费用审批(如果有审批的概念)
employee\_list.dinners_policy | 用餐权限| jsonobject | N|用餐数据 
dinners_policy.dinner_priv_flag | 限制非企业员工用餐标识| boolean | N |false
dinners_policy.rule_limit_flag | 是否限制规则| boolean | N |false
dinners_policy.rule_id | 规则id| string | N |ofaisfasjwf
dinners_policy.meishi_policy | 用餐权限信息| jsonobject | N |用餐权限信息
meishi_policy.exceed_buy_type | 超规则下单| integer | N |1：禁止（如果超出规则，则不允许下单操作） 2：超规填写理由下单（当有规则限制时，如果超出规则 的规定可以需下单，但是需要填写超规下单的理由）
meishi_policy.personal_pay | 个人支付开关| boolean | N |true,false
dinners_policy.dinner_policy | 用餐权限| jsonobject | N |用餐权限 固定值
dinner_policy.exceed_buy_flag | 超规则下单| integer | N |固定值1
employee\_list.takeaway_policy | 外卖权限| jsonobject | N |外卖数据
takeaway_policy.takeaway_priv_flag | 是否允许员工外卖标识| boolean | N |false
takeaway_policy.takeaway_rule_limit_flag | 是否限制规则| boolean | N |false
takeaway_policy.takeaway_rule_id | 规则id| integer | N |111
takeaway_policy.exceed_buy_type | 超规控制| integer | N | (1:禁止下单 2: 填写理由)
takeaway_policy.personal_pay | 个人支付开关| boolean | N | true,false




请求示例

```
  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id":784kuf873jf9834uiy98e"",
  "data":{
  "employee_list": [
    {
      "name": "张三",
      "phone": "17080151667",
      "third_org_unit_id": "5747fbc10f0e60e0709d8d7d",
      "third_employee_id": "57ab054c2528226a805bd5e1",
      "role": 3,
      "takeaway_policy": {//外卖权限
        "takeaway_priv_flag": true, //是否开启
        "takeaway_rule_limit_flag": true,//是否限制规则
        "takeaway_rule_id": 111, //规则ID
        "exceed_buy_type": 1,//超规控制 (1:禁止下单 2: 填写理由)
        "personal_pay": true//个人支付开关
      },
      "air_policy": {
        "unemployee_air": false,
        "air_priv_flag": false,
        "air_other_flag": false,//是否允许为其他员工订机票
        "air_verify_flag": true,
        "air_rule_limit_flag": true,
        "air_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,//1：禁止 2：超规填写理由下单 3：超规需要提交费用审批
        "refund_ticket_type": 1,//退订控制 0：不限制 1:填写原因 2:提交审批  230新增
        "changes_ticket_type": 1//改签控制 0：不限制 1:填写原因 2:提交审批   230新增
      },
      "intl_air_policy": {
        "unemployee_air": false,
        "air_priv_flag": false,
        "air_other_flag": false,
        "air_verify_flag": true,
        "air_rule_limit_flag": true,
        "air_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "air_order_verify_flag": false
      },
      "hotel_policy": {
        "unemployee_hotel": false,
        "hotel_priv_flag": true,
        "hotel_other_flag": true,
        "hotel_verify_flag": false,
        "hotel_rule_limit_flag": true,
        "hotel_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "personal_pay": true,
        "refund_ticket_type": 1
      },
      "train_policy": {
        "unemployee_train": false,
        "train_priv_flag": true,
        "train_other_flag": true,
        "train_verify_flag": false,
        "train_rule_limit_flag": true,
        "train_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "refund_ticket_type": 1,
        "changes_ticket_type": 1
      },
      "car_policy": {
        "car_priv_flag": true,
        "rule_limit_flag": true,
        "rule_ids": [
          {
            "rule_id": [
              111,
              2222
            ],
            "type": 1
          },
          {
            "type": 2,
            "rule_id": [
              5555,
              6666
            ]
          }
        ],
        "exceed_buy_type": 1,
        "allow_shuttle": false,
        "personal_pay": true
      },
      "mall_policy": {
        "mall_priv_flag": true,
        "rule_limit_flag": true,
        "rule_id": "ofaijwf",
        "exceed_buy_flag": false
      },
     "dinners_policy": {
        "rule_priv_flag": true,
        "rule_limit_flag": true,
        "rule_id": "5d492a7123445f227a77b830",
        "meishi_policy": {
          "exceed_buy_type": 1,
          "personal_pay": true
        },
        "dinner_policy": {
          "exceed_buy_flag": 1
        }
      }
    },
    {
      "name": "李四",
      "phone": "17080151667",
      "third_org_unit_id": "5747fbc10f0e60e0709d8d7d",
      "third_employee_id": "57ab054c2528226a805bd5e1",
      "role": 3,
      "takeaway_policy": {
        "takeaway_priv_flag": true,
        "takeaway_rule_limit_flag": true,
        "takeaway_rule_id": 111,
        "exceed_buy_type": 1,
        "personal_pay": true
      },
      "air_policy": {
        "unemployee_air": false,
        "air_priv_flag": false,
        "air_other_flag": false,
        "air_verify_flag": true,
        "air_rule_limit_flag": true,
        "air_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "refund_ticket_type": 1,
        "changes_ticket_type": 1
      },
      "intl_air_policy": {
        "unemployee_air": false,
        "air_priv_flag": false,
        "air_other_flag": false,
        "air_verify_flag": true,
        "air_rule_limit_flag": true,
        "air_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "air_order_verify_flag": false
      },
      "hotel_policy": {
        "unemployee_hotel": false,
        "hotel_priv_flag": true,
        "hotel_other_flag": true,
        "hotel_verify_flag": false,
        "hotel_rule_limit_flag": true,
        "hotel_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "personal_pay": true,
        "refund_ticket_type": 1
      },
      "train_policy": {
        "unemployee_train": false,
        "train_priv_flag": true,
        "train_other_flag": true,
        "train_verify_flag": false,
        "train_rule_limit_flag": true,
        "train_rule_id": "575263e982f880a6d686ce11",
        "exceed_buy_type": 1,
        "refund_ticket_type": 1,
        "changes_ticket_type": 1
      },
      "car_policy": {
        "car_priv_flag": true,
        "rule_limit_flag": true,
        "rule_ids": [
          {
            "rule_id": [
              111,
              2222
            ],
            "type": 1
          },
          {
            "type": 2,
            "rule_id": [
              555
            ]
          }
        ],
        "exceed_buy_type": 1,
        "allow_shuttle": false,
        "personal_pay": true
      },
      "mall_policy": {
        "mall_priv_flag": true,
        "rule_limit_flag": true,
        "rule_id": "ofaijwf",
        "exceed_buy_flag": false
      },
      "dinners_policy": {
        "rule_priv_flag": true,
        "rule_limit_flag": true,
        "rule_id": "5d492a7123445f227a77b830",
        "meishi_policy": {
          "exceed_buy_type": 1,
          "personal_pay": true
        },
        "dinner_policy": {
          "exceed_buy_flag": 1
        }
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
                "name": "李四",
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
                "phone": "17004531919",
                "name": "张三",
                "thirdEmployeeId": "888s0lll",
                "errorMsg": "手机号已经存在，请使用其他手机号"
            },
            {
                "companyId": "59df06662798635263b8414c",
                "phone": "17004531918",
                "name": "赵六",
                "thirdEmployeeId": "h99k4lll",
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
                "phone": "17004531917",
                "name": "王五",
                "thirdEmployeeId": "100991",
                "errorMsg": "部门信息参数不正确"
            }
        ]
    }
}


errorMsg详细说明:
会存在以下几种情况
1."手机号已经存在，请使用其他手机号"
2。"第三方ID已经被其它用户绑定"
3."部门信息参数不正确"
4."公司信息不存在，请使用正确参数"
5."保存规则接口异常!"
6."当前第三方部门ID不存在"

```