| 字段 | 名称 | 类型 | 必填 | 详情 |
| --- | --- | --- | --- | --- |
| company\_id | 公司id | string | Y | 5747fbc10f0e60e0709d8d89 |
| company\_name | 公司名称 | string | Y | 分贝通 |
| type\_pame | 订单类型名称 | string | Y | 机票 |
| type | 订单类型 | integer | Y | 机票:1 |
| status | 订单状态 | integer | Y | 出票中:1700，出票成功:1800 |
| apply\_name | 申请人姓名 | string | Y | 张三 |
| contact\_phone | 联系电话 | string | Y |
|contact_name|联系人姓名|string |Y|李四（申请人和联系人和使用人可以是同一人，也可以是不同的人）
|phone|联系人电话|string|Y|18090180901
|use_name|使用人姓名|string |Y|王五
|use_phone|使用人联系电话|string|Y|18767909349
| dept\_name | 部门名称 | string | Y | 事业部 |
| monetary\_unit | 货币单位 | string | Y | 人民币 |
| third\_remark | 出差事由备注 | string | Y | 出差 |
| order\_id | 订单id | string | Y | 9884hhkhfsk |
| total\_price | 总价 | double | Y | 388.00 |
|begin_time|航班起飞时间|string |Y|2018-01-01 10:04:30|
|end_time|航班到达时间|string|Y|2018-01-01 10:55:30|
| budget\_money | 预估费用总计 | double | Y | 单位：分 |
| estimated\_amount | 预估费用 | double | Y | 单位：分 |
| refund\_amount | 金额 | double | Y | 供应商退给我们的钱 |
| refund\_fee | 手续费 | double | Y | 退票产生的手续费 |
| third\_approve\_id | 申请单ID | string | Y ||

数据格式:

```
{
    "company_id":"5747fbc10f0e60e0709d8d89",
    "company_name":"分贝通"
    "type_name":"机票",
    "type":1,
    "status":1700,
    "apply_name":"张三",
        "contact_phone":"13080899009",
        "dept_name":"人事部",
    "monetary_unit":人民币,
    "third_remark":"搜索",
    "order_id":"hksf83ho93lsbvnos145",
    "total_price": 302,
    "budget_money":787.80,
    "departure_place": "北京",
    "destination_place":"上海",
    "begin_time":"2018-01-01",
    "end_time":"2018-01-01",
    "third_approve_id":"hksf83ho93lsbvnos145",







}
```



