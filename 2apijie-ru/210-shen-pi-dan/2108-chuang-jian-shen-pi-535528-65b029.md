2.10.8 创建审批单\(新版\)

#### 接口说明

* 1.**新接口**
* 2.如果有审批业务，则需要进行通过该接口创建审批单，在下单时可以选择创建的相应审批单
* 3.如果审批单中包含相应的规则信息，则可以创建相应的规则,如果审批单不使用规则相关信息，则不需要传递
* 4.增加国际机票审批

| 名称 | 描述 |
| --- | --- |
| 沙箱环境地址 | [https://open-plus-test.fenbeijinfu.com](https://open-plus-test.fenbeijinfu.com) |
| 生产环境地址 | [https://open-plus.fenbeitong.com](https://open-plus.fenbeitong.com) |
| HTTP方法 | POST |
| Content-Type | application/x-www-form-urlencoded |
| method | /openapi/func/approve/create |

| 字段 | 名称 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- | --- |
| access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 |
| sign | 签名 | string | Y | oihfnlyeofdh98 |
| timestamp | 时间戳 | long | Y | 13位时间戳 1241243250000 |
| employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id,为创建人的ID |
| employee\_type | 用户类型 | string | Y | 类型，0为分贝用户，1为第三方用户 |
| data | 请求数据 | jsonobject | Y | 请求数据 |
| data.apply | 申请单内容 | jsonobject | Y | 申请单详细内容 |
| data.apply.type | 申请单业务类型 | integer | Y | 1.差旅\(对应trip\_list下的type值为7、11、15\) 3.采购 |
| data.apply.flow\_type | 审批类型 | integer | Y | 固定为4 |
| data.apply.third\_id | 申请单id | string | Y | 第三方审批单id |
| data.apply.third\_remark | 第三方备注 | string | Y | 详细备注信息 |
| data.apply.budget | 申请单预算 | integer | Y | 预算总额\(为trip\_list中estimated\_amount的总和 \) |
| data.apply.apply\_reason\_desc | 申请事由补充说明 | string | N | 补充事由说明，小于500 |
| data.apply.cost\_attribution\_id | 费用归属id | string | N | 部门ID或项目ID |
| data.apply.cost\_attribution\_name | 费用归属name | string | N | 部门名称或项目名称 |
| data.apply.cost\_attribution\_category | 费用归属类型 | integer | N | 1.部门 2.项目 |
| data.guest\_list | 出行联系人信息 | jsonarray | N | 出行联系人信息 |
| data.guest\_list.id | 出行联系人id | string | N | 出行联系人id\(分贝用户ID\)，当is\_employee为false时，不需要传递id，为true时必传 |
| data.guest\_list.is\_employee | 是否是企业员工 | boolean | N | true,false |
| data.guest\_list.name | 出行联系人姓名 | string | N | 张三 |
| data.guest\_list.phone\_num | 出行联系人手机号 | string | N | 17080151667 |
| data.custom\_fields | 自定义字段列表 | jsonarray | N | 自定义字段列表\(自定义字段传递时需把字段值告知分贝通，分贝通进行相应配置后，在后台导出审批单时会导出相应字段，否则字段传递值无效\) |
| data.trip\_list | 行程列表 | jsonarray | Y | 行程列表 |
| data.trip\_list.type | 业务类型 | integer | Y | 行程类型 7.机票 11.酒店 15.火车 40.国际机票 |
| data.trip\_list.start\_city\_id | 出发城市ID | string | Y | 在酒店业务中，start\_city\_id和arrival\_city\_id都传入目的地城市ID |
| data.trip\_list.start\_time | 出发时间 | string | Y | 行程开始日期 2017-12-13 |
| data.trip\_list.arrival\_city\_id | 目的地城市 | string | Y | 行程到达城市ID |
| data.trip\_list.end\_time | 结束时间 | string | Y | 行程结束日期 2017-12-29（在分贝通企业管理后台需开启出发日期配置成时间范围后，可创建时间段审批单） |
| data.trip\_list.estimated\_amount | 预估价格 | integer | Y | 100,单位分 |
| data.trip\_list.back\_start\_time | 返程开始日期 | string | N | 返程开始日期 行程为国际机票且航程为返程类型则必填 |
| data.trip\_list.back\_end\_time | 返程结束日期 | string | N | 返程结束日期 行程为国际机票且航程为返程类型则必填 |
| data.trip\_list.trip\_type | 航程类型 | integer | N | 航程类型 1单程 2往返 行程为国际机票则必填 |
| air\_rule\_info.air\_type | 舱位等级 | array | N | 1:商务舱\(头等舱\), 3:经济舱 |
| air\_rule\_info.price | 价格限制 | double | N | 100 单位元 |
| intl\_air\_rule\_info.air\_type | 国际机票舱位等级 | array | N | 1:商务舱\(头等舱\), 3:经济舱 |
| intl\_air\_rule\_info.price | 国际机票价格限制 | double | N | 100 单位元 |
| hotel\_rule\_info.level | 星级 | array | N | 0.二星及以下 1.三星 2.四星 3.五星 |
| hotel\_rule\_info.price | 平均每晚的上限 | double | N | 100,单位元 |
| train\_rule\_info.common\_train\_seat\_type | 普通列车席别限制 | array | N | 11.高级软卧 12.软卧 13.硬卧 14.软座 15.硬座 16.无座 |
| train\_rule\_info.highspeed\_train\_seat\_type | 高铁席别限制 | array | N | 1.商务座 2.特等座 3.一等座 4.二等座 5.软卧 6.高铁无座 7.高级软卧 8.动卧 9.硬卧 |
| train\_rule\_info.price | 价格限制 | double | N | 100,单位元 |

请求示例：

```json
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{
"apply":{
"type":1,
"flow_type":4,
"budget":1,
"third_id":"59dc7fe62798635263b8414a",
"third_remark":"approve-openapi-test2",
"apply_reason_desc":"不是出去玩",
"cost_attribution_id":"682984729i982489",
"cost_attribution_name":"测试费用归属",
"cost_attribution_category":1
},
"guest_list":[
{
"id":"58dca3035f281a5c225c4d84",
"is_employee":false,
"name":"韩美美",
"phone_num":"18518270668"
}
],
"custom_fields":[
{
"type":"cost_attribution",
"value":"loiewo98498du3j498jder"
}
],
"trip_list":[
{
"type":7,
"start_city_id":"2000002",
"start_time":"2017-12-13",
"arrival_city_id":"1000001",
"end_time":"2017-12-13",
"estimated_amount":1
},
{
"type":7,
"start_city_id":"2000002",
"start_time":"2017-12-14",
"arrival_city_id":"1000001",
"end_time":"2017-12-14",
"estimated_amount":1
}
],
"air_rule_info":[
{
"type":"air_type",
"value":[
1
]
},
{
"type":"price",
"value":100
}
],
"intl_air_rule_info":[
{
"type":"air_type",
"value":[
1
]
},
{
"type":"price",
"value":100
}
],
"hotel_rule_info":[
{
"type":"level",
"value":[
1
]
},
{
"type":"price",
"value":100
}
],
"train_rule_info":[
{
"type":"common_train_seat_type",
"value":[
1
]
},
{
"type":"highspeed_train_seat_type",
"value":[
1
]
},
{
"type":"price",
"value":100
}
]
}
```

响应结果：

```json
{
"request_id": "xUolOnJHWhIO4YP8MozO",
"code": 0,
"msg": "success",
"data": {
"id": "58baa2866819481560f013ac"
}
}
```



