2.3.1 火车车站列表

####接口说明
- 1.**最新接口**
- 2.查询火车订单列表接口


请求方式|请求地址
----|---
POST|/open/api/train/stationList


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|
data.source| 订单来源|string |Y|A企业 JUNWEI000001




请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":     {
                "orderno": "5bab55d22798633d548179cb",
            "status":1,
          "bdate":"2018-09-20",
          "edate":"2018-09-27",
                "supplier": "分贝通",
                "page":1,
                "pagesize":10,
                "source":"JUNWEI000001"
            }
}


```





















```
{
"request_id": "qHu4Z8CywhbTcSJsS2XJ",
"code": 0,
"type": 0,
"msg": "success",
"data": {
"data": [
{
"StationName": "兰州东",
"StationShortName": "lzd",
"StationCode": "LVJ",
"Id": 1,
"StationFullName": "lanzhoudong"
},
{
"StationName": "长春",
"StationShortName": "cc",
"StationCode": "CCT",
"Id": 1,
"StationFullName": "changchun"
},
{
"StationName": "上海",
"StationShortName": "sh",
"StationCode": "SHH",
"Id": 1,
"StationFullName": "shanghai"
},
{
"StationName": "昆明",
"StationShortName": "km",
"StationCode": "KMM",
"Id": 1,
"StationFullName": "kunming"
},

```















