2.12.1 新增预算接口

####接口说明
- 1.**最新接口**
- 2.**新增预算接口可以添加不同类型的预算**


请求方式|请求地址
----|---
POST|/open/api/third/budget/create

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|lw8osdfj983uh4
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.budget_type|预算种类|integer |Y|1:个人预算 2:部门预算 3:项目中心预算
data.budget_name |预算名称| string | Y |不能重复
data.budget_thrid_id |第三方预算ID| string | Y |不能重复
data.warn_percent1 |预警百分比1| integer | Y |30，较低值
data.warn_percent2|预警百分比2| integer| Y |60，较高值
data.execution_cycle|执行周期|integer |Y|1:自然月 2:自然季 3:自然年 
data.manager_msg_warn |发送预警短信至部门主管/项目负责人| integer | Y |0-不发送 1-发送
data.itemList |预算项| list | Y |预算项集合
itemList.amount_limit|限制金额| integer| Y | -1：不限制，若限制，则填写具体数据
itemList.over_limit_control|超预算是否可提交|integer |Y|1:允许提交 2:禁止提交
itemList.sort |预算项显示排序| integer | Y |1,2,3
itemList.typeList |业务类型list| list | Y |业务类型集合
typeList.biz_type|业务类型 | integer| Y |3:用车 7:国内机票 11:酒店 15:火车票 20:采购 30:用餐 40:国际机票 50:外卖
typeList.sort|业务类型显示排序 | integer| Y |1，2，3





请求示例：

```



"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
  "budget_type": 3,
  "budget_name": "项目预算测试1",
  "warn_percent1": 30,
  "warn_percent2": 60,
  "execution_cycle": 1,
  "manager_msg_warn": 0,
  "item_list": [
    {
      "amount_limit": 2000,
      "over_limit_control": 1,
      "sort": 1,
      "type_list": [
        {
          "biz_type": 3,
          "sort": 1
        },{
          "biz_type": 7,
          "sort": 2
        }
      ]
    },
    {
      "amount_limit": 5000,
      "over_limit_control": 1,
      "sort": 2,
      "type_list": [
        {
          "biz_type": 7,
          "sort": 1
        },
        {
          "biz_type": 30,
          "sort": 2
        }
      ]
    }
  ],
  "budget_thrid_id": "09780089767567657687898"
 }




响应数据：

{
  "request_id": "gd4AQoHphtN9YXc1TNqK",
  "code": 0,
  "type": 0,
  "msg": "success"
}



```














