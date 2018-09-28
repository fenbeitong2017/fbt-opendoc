2.3.2 火车车票查询

####接口说明
- 1.**最新接口**
- 2.查询火车订单列表接口


请求方式|请求地址
----|---
POST|/open/api/train/getTrainList


字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|
data.date|开始日期|string  |Y|2018-09-20
data.fromcity| 出发城市code|string |N|JJG
data.tocity| 目的城市code|string |Y|WXN
data.sign| 签名|string |N|k88uewu98u382o8dssd32t43
data.source| 订单来源|string |Y|A企业




请求示例：

```


{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":      {
                "date": "2018-10-23",
                "fromcity": "JJG",
                "tocity": "WXN",
                "sign": "890389ui392",
                "source":"JUNWEI000001"
            }
}


```






```

{
"request_id": "KRuaqq6ckrvVHF40sP8g",
"code": 0,
"type": 0,
"msg": "success",
"data": {
"data": [
{
"RZ_YP": "-1",
"EndTime": "13:02",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "53",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 21,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "K876",
"YZ_YP": 21,
"StartTime": "12:09",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 21
},
{
"RZ_YP": "-1",
"EndTime": "13:55",
"OverNight": "0",
"WZ_YP": 21,
"RZ": "-",
"CostTime": "1:12",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 0,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": 11,
"TrainCode": "K244",
"YZ_YP": 0,
"StartTime": "12:43",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 0
},
{
"RZ_YP": "-1",
"EndTime": "14:35",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "1:10",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": "-1",
"GW_YP": "-1",
"TrainType": "P",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 3,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "6026",
"YZ_YP": 21,
"StartTime": "13:25",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": "-",
"StartCity": "九江",
"RWX": "-",
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": "-",
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": "-",
"YWZ": "-",
"RW_YP": "-1"
},
{
"RZ_YP": "-1",
"EndTime": "18:26",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "49",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 21,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "K754",
"YZ_YP": 10,
"StartTime": "17:37",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 4
},
{
"RZ_YP": "-1",
"EndTime": "19:12",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "59",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 21,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "K1454",
"YZ_YP": 21,
"StartTime": "18:13",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 0
},
{
"RZ_YP": "-1",
"EndTime": "21:49",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "1:15",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 14,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "K570",
"YZ_YP": 21,
"StartTime": "20:34",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 0
},
{
"RZ_YP": "-1",
"EndTime": "22:21",
"OverNight": "0",
"WZ_YP": "-1",
"RZ": "-",
"CostTime": "1:0",
"RZ1_YP": "-1",
"SWZ_YP": "-1",
"YW_YP": 0,
"GW_YP": "-1",
"TrainType": "K",
"ID": 1,
"Distance": "0",
"BeginStation": "九江",
"YZ": 11,
"EndCity": "武穴",
"GWS": "-",
"WZ": "-",
"TrainCode": "K446",
"YZ_YP": 21,
"StartTime": "21:21",
"RZ1": "-",
"GWX": "-",
"RZ2": "-",
"TDZ": "-",
"RWS": 86.5,
"StartCity": "九江",
"RWX": 131.5,
"TDZ_YP": "-1",
"EndStation": "武穴",
"YWS": 57,
"RZ2_YP": "-1",
"SWZ": "-",
"YWX": 102,
"YWZ": 0,
"RW_YP": 0
}
],
"supplier": "分贝通",
"source": "JUNWEI000001",
"successcode": "T"
}
}

```




