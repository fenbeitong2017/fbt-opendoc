2.10.6 根据公司ID查询公司是否开启时间范围审批

####接口说明
- 1.**最新接口**
- 2.如果公司审批单可以是时间范围，则需要在创建审批单之前调用该接口查询公司是否在分贝通企业web后台设置成功，如果没有设置成功，则不会创建时间范围审批单。
- 3.设置步骤：登录分贝通企业web管理后台->管控审批->申请单配置->申请事由字段->出发日期配置， 设置为范围时间 




| 请求方式 | 请求地址 |
| --- | --- |
| POST |/open/api/approve/departure_date/type |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID|
| employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 |
| data |  请求数据 | jsonobject | Y |请求数据




请求示例：

```

    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{}


```

响应结果：

```
{
    "request_id": "RAiyTlJEqYvgR4Z5",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "apply_departure_date": 0,//0:精确时间（天） 1:范围时间
        "apply_pedestrians_control": 0,
        "apply_reason_bank_individual": 0,
        "apply_reason_chailv": 0,
        "apply_reason_chailv_change": 0,
        "apply_reason_coupon": 0,
        "apply_reason_desc": 0,
        "apply_reason_dinner": 0,
        "apply_reason_takeaway": 0,
        "apply_reason_taxi": 0,
        "whether_trip_apply_budget": 1
    }
}

```



