2.9.7 添加同行人获取国籍信息
####接口说明
- 1.最新接口

请求方式|请求地址
----|---
POST|/open/api/common/national


字段|名称|类型|必填|描述
----|----|---|---|---
access_token|鉴权Token|string|Y|xxx.lsie98wxje
sign|签名|string|Y|8e8ekjdewiu7843
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|分贝用户id或者第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据|jsonstring|Y|请求data数据


```
{
"access_token":"5747fbc10f0e60e0709d8d722",
"timestamp":124124325,
"sign":"oihfnlyeofdh98",
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":1,
"data":{
 }
}


```



返回结果

```
{
  "request_id": "WBfdNYTpS9qBFiE1WZQI",
  "code": 0,
  "type": 0,
  "msg": "success",
  "data": [
    {
      "code": "CN",
      "name": "中国"
    },
    {
      "code": "HK",
      "name": "中国香港"
    },
    {
      "code": "MO",
      "name": "中国澳门"
    },
    {
      "code": "TW",
      "name": "中国台湾"
    },
    {
      "code": "SJ",
      "name": "斯瓦尔巴群岛和扬马延岛"
    }
  ]
}
```

