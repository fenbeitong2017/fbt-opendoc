2.2.5.6 批量添加项目
####接口说明
- 1.**最新接口**


请求方式|请求地址
----|---
POST|/open/api/third/project/createBatch


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
data.user_id|添加人ID|string |Y|third_hanbing
data.type|人员类型| integer |Y|1:分贝人员ID;  2:第三方ID
data.auto_flag|自动生成标识|integer |Y|2 固定值为2
data.project_info.code|项目code| string |Y|iu9834943u9834ur
data.project_info.name|项目名称|string |Y|国航项目
data.project_info|项目信息| jsonarray |Y|项目信息集合
data.project_info.code|项目code| string |Y|iu9834943u9834ur
data.project_info.name|项目名称|string |Y|国航项目
data.project_info.third_cost_id|第三方项目ID| string |Y|9843894927943

 请求示例:
 
 ```

  "access_token": "xxx.xxx.xxx",
  "timestamp": 123456789,
  "employee_id": "12345678",
  "employee_type":"0",
  "sign": "jifejfwojelajflejf",
  "data": {
  "type": 2,
  "company_id": "5747fbc10f0e60e0709d8d7d",
  "user_id": "hanbing",
  "auto_flag": 2,
  "project_info": [
    {
      "code": "23646533332564538235",
      "name": "测试批量创建项目-1",
      "third_cost_id": "123gr545hr864gf123"
    },
    {
      "code": "23648978673434242564236",
      "name": "测试批量创建项目-1",
      "third_cost_id": "1234t6453ef4rdgdged121"
    }
  ]
}

```

返回结果

```
{
  "request_id": "IqQMZJGG16Ns2EeUKi1J",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": [
      {
          "id":"5afa956523445f22dd04322",  //分贝ID
          "thirdCostId":"123123"           //三方ID
      },
       {
          "id":"5afa956523445f22dd0ww22",
          "thirdCostId":"1234121"
      }
      
      ]
      
  
}



```
