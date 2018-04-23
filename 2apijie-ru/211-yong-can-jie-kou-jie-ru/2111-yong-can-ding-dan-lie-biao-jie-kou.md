请求方式|请求地址
----|---
POST|/open/api/dinner/order/list


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data || jsonobject |Y|
data.state| 查询状态|integer |Y|0全部
data.search\_category |搜索维度| integer | N |1:企业，2:个人
data.page\_index |页码| integer | N |1(默认值)
data.page\_size|每页显示条数| integer| N |20(默认值)


请求示例：

```


{
"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":1,
"data":{
"state":0
}
}


```


响应数据：



```

{
    "request_id": "4mJOGYtaAwqkG2rGQATk",
    "code": 0,
    "msg": "success",
    "data": {
        "pageCount": 18,
        "data": [
            {
                "branch_shop_name": "5号便当(光华路soho店)",//门店名称
                "contact_name": "刘维中",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.01",//订单总价字符串
                "total_price": 0.01,//订单总价
                "create_time": "2018-02-27 10:15:41",//下单时间
                "logo_url": null,//门店图片地址
                "shop_addr": "光华路22号1层127",//门店地址
                "order_id": "5a94bf4de4b0d2bdb9c70578",//订单ID
                "prudoct_id": "5a94bf4de4b0d2bdb9c70579",
                "person_count": 1,//用餐人数
                "status": {//订单状态
                    "key": 4600,
                    "value": "已完成"
                }
            },
            {
                "branch_shop_name": "5号便当(光华路soho店)",
                "contact_name": "刘维中",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.01",
                "total_price": 0.01,
                "create_time": "2018-02-07 11:27:04",
                "logo_url": null,
                "shop_addr": "光华路22号1层127",
                "order_id": "5a7a7208e4b0d2bdb9c70571",
                "prudoct_id": "5a7a7208e4b0d2bdb9c70572",
                "person_count": 1,
                "status": {
                    "key": 4600,
                    "value": "已完成"
                }
            },
            {
                "branch_shop_name": "5号便当(光华路soho店)",
                "contact_name": "刘维中",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.01",
                "total_price": 0.01,
                "create_time": "2018-01-17 21:51:47",
                "logo_url": null,
                "shop_addr": "光华路22号1层127",
                "order_id": "5a5f54f3e4b0667cbe3dd777",
                "prudoct_id": "5a5f54f3e4b0667cbe3dd778",
                "person_count": 1,
                "status": {
                    "key": 4600,
                    "value": "已完成"
                }
            },
            {
                "branch_shop_name": "5号便当(光华路soho店)",
                "contact_name": "刘维中",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.01",
                "total_price": 0.01,
                "create_time": "2018-01-17 21:33:07",
                "logo_url": null,
                "shop_addr": "光华路22号1层127",
                "order_id": "5a5f5093e4b0c378df7be5c3",
                "prudoct_id": "5a5f5093e4b0c378df7be5c4",
                "person_count": 1,
                "status": {
                    "key": 4600,
                    "value": "已完成"
                }
            },
                 {
                "branch_shop_name": "独孤一盏灯(常营)",
                "contact_name": "贾斌",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.00",
                "total_price": 0,
                "create_time": "2018-02-05 15:41:07",
                "logo_url": null,
                "shop_addr": "朝阳区常营中路保利嘉园1号院底商1号",
                "order_id": "5a780a93e4b0d2bdb9c7056f",
                "prudoct_id": "5a780a93e4b0d2bdb9c70570",
                "person_count": 2,
                "status": {
                    "key": 4710,
                    "value": "已关闭"
                }
            },
            {
                "branch_shop_name": "丸龟制面(世贸天阶店)",
                "contact_name": "谷健波",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.00",
                "total_price": 0,
                "create_time": "2018-02-03 11:13:17",
                "logo_url": null,
                "shop_addr": "光华路世贸天阶B1楼B122",
                "order_id": "5a7528cde4b044794ab59117",
                "prudoct_id": "5a7528cde4b044794ab59118",
                "person_count": 1,
                "status": {
                    "key": 4710,
                    "value": "已关闭"
                }
            },
            
            {
                "branch_shop_name": "CALIFORKS(世贸天阶店)",
                "contact_name": "刘维中",
                "employee_id": "59ccbf2123445f570b8c83fe",//下单人ID
                "total_price_str": "￥0.01",
                "total_price": 0.01,
                "create_time": "2018-01-17 18:12:32",
                "logo_url": null,
                "shop_addr": "世茂天阶南街B131",
                "order_id": "5a5f2190e4b0c378df7be56c",
                "prudoct_id": "5a5f2190e4b0c378df7be56d",
                "person_count": 1,
                "status": {
                    "key": 4600,
                    "value": "已完成"
                }
            }
        ],
        "pageNo": 1,
        "totalCount": 18
    }
}

```


