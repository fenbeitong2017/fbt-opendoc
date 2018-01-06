2.9.1 根据城市获取机票机场列表和火车站列表

请求方式|请求地址
----|---
POST|/open/api/common/city-list



字段|名称|类型|必填|描述
----|----|---|---|---
access_token|api鉴权Token|string|Y|
sign|签名|string|Y|
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据|jsonstring|Y|
data.type|业务类型 | string |Y|1.火车，2，机票
data.city\_key|城市关键字 |string|Y|北京
请求示例：

```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"timestamp":124124325,
	"sign":"oihfnlyeofdh98",
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"type":"2",
		"city_key":"上海"
	}
}



```




返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
area\_info\_list |地区信息| array|Y| 
area\_info\_list.area\_id |地区ID	| string | Y | 2000002 
area\_info\_list.area\_name |地区名称	| string | Y| 上海市
train\_station\_list |火车站列表信息| array |Y| 
train\_station\_list.en\_name |车站英文名| string|Y| sha
train\_station\_list.ch\_name |车站中文名|string|Y| 上海
train\_station\_list.station\_code |车站三字码|string|Y| SHH
train\_station\_list.station\_spell |车站全拼|string|Y| shanghai
train\_station\_list.station\_simple\_spell |车站简拼|string|Y| sh
train\_station\_list.station\_no |车站编号|string|Y| 10



```


{
    "request_id": "xUolOnJHWhIO4YP8MozO",
    "code": 0,
    "msg": "success",
    "data": {
        "area_info_list": [
            {
                "area_id": "2000002",
                "area_name": "上海市"
            }
        ],
        "train_station_list": [
            {
                "en_name": "sha",
                "ch_name": "上海",
                "station_code": "SHH",
                "station_spell": "shanghai",
                "station_simple_spell": "sh",
                "station_no": "10"
            },
            {
                "en_name": "shn",
                "ch_name": "上海南",
                "station_code": "SNH",
                "station_spell": "shanghainan",
                "station_simple_spell": "shn",
                "station_no": "11"
            },
            {
                "en_name": "shq",
                "ch_name": "上海虹桥",
                "station_code": "AOH",
              "station_spell":"shanghaihongqiao",
                "station_simple_spell": "shhq",
                "station_no": "12"
            },
            {
                "en_name": "shx",
                "ch_name": "上海西",
                "station_code": "SXH",
                "station_spell": "shanghaixi",
                "station_simple_spell": "shx",
                "station_no": "13"
            }
        ]
    }
}



```

