2.10.2 撤销审批单
####接口说明
- 1.**最新接口**
- 2.**接口说明:**

```
该接口可以根据审批单ID进行撤销审批单，该接口可以根据第三方审批单ID撤销，也可以根据分贝通审批单ID撤销(创建审批单成功后会返回分贝通审批单ID)。分贝通审批单创建规则中分为用车审批和差旅审批，若在公司内，两种审批使用一张审批单，那么在创建时可能会出现一个第三方审批单ID对应两个分贝通审批单ID。如果再撤销时使用第三方审批单，那么会把多个审批单都撤销，如果使用分贝通审批单进行撤销，可以单独撤销用车或者差旅申请。

```


 请求方式|请求地址 
 ---|--- 
POST|/open/api/approve/cancel 



 字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 access\_token | 鉴权Token | string | Y |5747fbc10f0e60e0709d8d722 
 sign | 签名 | string | Y | oihfnlyeofdh98 
 timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 
 employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID
 employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 
 data |  请求数据 | jsonobject | Y |请求数据
 data.apply_id | 申请单内容 | string | Y|申请单id
 data.third_type| 申请单业务类型 | integer | Y | 审批单类型 1:分贝通审批单 2:第三方审批单


请求示例：

```
{
    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":1,
    "data":{            
     "apply_id" : "1i7d94f3ij783je8u383jd",
     "third_type" : 1 
}
}
```

响应结果：

```
{
    "request_id": "xUolOnJHWhIO4YP8MozO",
    "code": 0,
    "msg": "success",
    "data": {      
    }
}
code为0代表成功，其他均为失败。失败情况msg为具体的错误信息

```



