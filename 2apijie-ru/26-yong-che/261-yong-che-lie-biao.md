2.6.1 用车订单列表

####接口说明
- 1.**最新接口**
- 2.查询用车订单列表接口
  通过该接口可以查询企业使用分贝通APP下的机票订单信息
- 3.该接口一次最多可查询1000条数据，如订单数超过1000，则需要分页查询





请求方式|请求地址
----|---
POST|/open/api/car/order/list

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|string|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|请求数据
data.search\_category|搜索维度| integer | N | 1:企业 2:个人
data.state|查询状态|integer|N|  0:全部(默认值) 1:处理中 2:已完成
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| integer | N | 1(默认值)
data.page\_size|每页显示条数| integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":0
	}
}
```



响应结果示例：


 字段|名称|类型|必填|描述
-----|-----|----|----|----
data.results.order_id|	订单id|string|Y|48dfjlad984j8ssf 
data.results.can_process|否有查看权限|boolean|Y|判断当前登录用户是否有查看权限	 
data.results.vorder_id	|供应商id|string	|Y |注意：供应商id，不是供应商类型id		 
data.results.departure_name|出发地名称|string|Y| 国贸
data.results.departure_lng|出发地经度|double| Y|123.99
data.results.departure_lat|出发地纬度|double |Y	|56.00 
data.results.status|订单状态|integer |Y|700
data.results.status_info|订单状态描述|string|Y|	显示订单状态最好使用此字段，避免增加状态类型等不兼容问题 
data.results.price|金额	|double	 |Y|45.99	 
data.results.order_time|下单时间|string	|Y| 格式：MM-dd HH:mm:ss
data.results.schedule_time|用车时间|string|Y| 格式：yyyy-MM-dd HH:mm:ss
data.results.spec|用车类型信息|	jsonobject| Y|	 
data.results.spec.id|用车类型id|integer|Y| 100:舒适型；400：七座商务；200：豪华型；600:快车
data.results.spec.name	|用车类型名称|string|Y| 舒适型、七座商务、豪华型、快车	 
data.results.vendor_id	|供应商类型id|integer|Y | 1：滴滴；2：神州（注意：供应商类型id，不要与vorder_id弄混）
data.results.vendor_name|供应商名|string|Y|   展示供应商名字的地方使用此字段
data.results.type|用车类型|Integer|Y|  0：实时；1：预约；2：接机；3：送机		 
data.results.type_name|用车类型名|String|Y  |实时、预约、接机、送机（展示时使用此字段）		
data.results.arrival_name|目的地信息|string| Y|	 
data.results.arrival_lng|目的地经度|double| Y|123.99
data.results.arrival_lat|目的地纬度|double|Y|10.99
data.results.driver_info|司机信息|jsonobject|N|可能是空对象{}
data.results.driver_info.driver_order_count|司机接单数|integer|N | 神州没有该数据，注意兼容	
data.results.driver_info.driver_phone|司机电话|string|N|17909890878
data.results.driver_info.driver_level|司机评分|Double |	N|
data.results.driver_info.driver_car_type|车型号|string| N|
data.results.driver_info.driver_car_color|车辆颜色|string|N  |可能为空（神州没有、滴滴老数据也没有）注意兼容
data.results.driver_info.driver_card|	车牌|string |N|京Q34567
data.results.driver_info.driver_name|		司机称呼	|string	 |N|张师傅
data.results.driver_info.driver_avatar	|司机头像|string	|N  |神州专车没有司机头像，注意兼容
data.results.wait_duration|等待时长|integer | Y | 根据叫车时间与系统当前时间比较的时间差，单位秒（客户端列表跳转到叫车界面使用）	
data.results.total_price_str|	订单金额字符串|string |Y	|"￥660.00"
data.results.employee_name | 下单人姓名 | string | Y | 张三|
data.results.employee_id | 下单人id | string | Y | uejk8489u78078993u7848



```

{  "request_id": "IOCCucbNYCDEkCOOakDP",
    "code": 0,
    "msg": "Success",
    "data": {
        "results": [
            {
                "order_id": "596dcb622798634dbc16768b",//订单id
                "vorder_id": "1125899951260423",
                "departure_name": "世贸国际公寓",//出发地名称
                "departure_lat": 39.914876,//出发地纬度
                "departure_lng": 116.451379,//出发地经度
                "arrival_name": "物资学院路[地铁站]",//
                "spec": {//
                    "id": 600,//
                    "name": "快车"//
                },
                "type": 0,//
                "status": 610,//订单状态
                "status_info": "已取消",订单状态描述
                "price": 0,
                "order_time": "2017-07-18 16:48:34",
                "schedule_time": "2017-07-18 16:48:34",
                "can_process": true,
                "vendor_id": 1,//供应商id
                "vendor_name": "滴滴",供应商名
                "type_name": "实时",//用车类型名  0：实时；1：预约；2：接机；3：送机
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "driver_info": {},
                "wait_duration": 1183107,
                "employee_name":"张三",
                "employee_id":"56768798765645",
                "total_price_str":"￥0.00"
            },
            {
                "order_id": "596c830d2798630a935b5dd4",
                "vorder_id": "1125899949696928",
                "departure_name": "东大桥路24号楼",
                "departure_lat": 39.914829,
                "departure_lng": 116.451343,
                "arrival_name": "物资学院路[地铁站]",
                "spec": {
                    "id": 600,
                    "name": "快车"
                },
                "type": 1,
                "status": 610,
                "status_info": "已取消",
                "price": 0,
                "order_time": "2017-07-17 17:27:41",
                "schedule_time": "2017-07-18 23:00:00",
                "can_process": true,//是否有查看权限	Boolean	判断当前登录用户是否有查看权限
                "vendor_id": 1,
                "vendor_name": "滴滴",
                "type_name": "预约",
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "employee_name":"张三",
                "employee_id":"56768798765645",
                "driver_info": {}
            }
            
           
        ],
        "total_count": 247
        
    }
}

```
