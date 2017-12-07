请求方式|请求地址
----|---
POST|/open/api/approve/create


字段|名称|类型|必填|描述
----|---|---|---|---
access_token|鉴权Token|String|Y|5747fbc10f0e60e0709d8d722
sign|签名|String|Y| oihfnlyeofdh98
timestamp |时间戳|long|Y| 13位时间戳  1241243250000
employee\_id|用户ID|String|Y|分贝用户id或者第三方用户id
employee\_type|用户类型 |String|Y|类型，0为分贝用户，1为第三方用户
data |请求数据|jsonstring|Y|
data.apply |申请单内容| jsonstring |Y|
data.apply.third_id |申请单id|String|Y|
data.apply.type| 申请单业务类型| String |Y|
data.apply.state| 审批状态|String|N|保留字段
data.apply.apply\_reason |申请单申请事由| String |Y|
data.apply.apply\_reason\_desc |事由描述|String|N|
data.trip\_list| 行程列表| array |Y|
data.trip\_list.type| 业务类型|String|Y|
data.trip\_list.start\_city\_id| 出发城市ID| String |Y|
data.trip\_list.start\_time|出发时间 |String|Y|
data.trip\_list.arrival\_city\_id| 目的地城市|String|Y|
data.trip\_list.end\_time|结束时间|String|N|
data.guest\_list| array |同行人|N|
data.guest\_list.is\_employee|是否来自组织架构  |String|N|
data.guest\_list.name |同行人姓名 | String | N |
data.guest\_list.phone |同行人手机号 |String| N |





请求示例：


```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"timestamp":124124325,
	"sign":"oihfnlyeofdh98",
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
				{
		  "apply":{
		           "id":"58baa2866819481560f013ac",
		           "type":1,
		           "state":1,
		           "apply_reason":"因公出差",
		           "apply_reason_desc":"不是出去玩"
		            },
		   "trip_list":[{
		           "type":1,  
		             "start_city_id":"1000001",        
		           "start_time":"2017-2-27",
		           "arrival_city_id":"2000002",
		            "end_time":"2017-02-28"
		            }],
		  "guest_list":[
		         {
		            "is_employee": false,
		           "name": "韩美美",
		           "phone": "18518270668"
		           }
		      ]
		}
		

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
        "id": "58baa2866819481560f013ac"
    }
}



```

