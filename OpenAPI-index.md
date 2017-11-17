
#分贝通接口说明
 
----------------


[toc]

环境|域名
----|---
沙箱环境|https://open-sandbox.fenbeitong.com
生产环境|https://open.fenbeitong.com

## 1.1 接入说明

### 1.11 接入方需要提供以下数据

	1.接入方的基本信息，公司名称，产品域名，公司资质
	
	2.公司调用提供方接口的服务器ip
	
	3.接入方提供支付成功回调url地址 
 
### 1.12 接入前准备
术语|说明
----|---
app_id|申请时分配的appIdapp_key|申请时分配的appKey，与appId一起用于认证授权
sign_key|申请时分配的signKey，用于接口签名

```
1.首先需要联系我司相关人员开通企业后台，并且将第三方员工组织架构录入其中；

2.申请企业Appkey和AppId;

3.如果开发阶段接入，请使用沙箱环境；

4.API对接方式现在在调整中，暂时只提供接口参数方式，暂时不提供线上环境；
```



#  H5对接接口
## 2.1 接入说明

```
1.生成企业AppKey和AppId，请联系相关人员进行操作，参数包括：

	1）appId/appKey/signKey 企业标识，请存储；
	
	2）服务端调用鉴权颁发Token，存入自己缓存，Token有效2小时；
	
	3）appUrl 例：https://open-sandbox.fenbeitong.com/auth/join?token=服务器颁发Token 嵌入到第三方应用中；
	
	4) 该Token为用户Token，每个用户不同；
	
2.查询企业URL等信息，可以根据appId和appKey进行查询

3.该接口访问频次每小时5次；
```


## 2.2 鉴权接口,颁发Token
根据企业appId/appKey等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/web/auth/v1/dispense

请求参数，以application/json传递：

名称|类型|必填|描述
----|---|---|---
appId|String|Y|企业ID
appKey |String|Y|企业key
tpUserId |String|Y|第三方系统中用户唯一身份标识（必填）, 是第三方本地用户信息的唯一标识，可以理解为第三方用户信息数据库表的id。
tpMobile |String|Y|手机号码

请求示例：

```
{
	"appId":"5747fbc10f0e60e0709d8d722",
	"appKey":"59b74c1323445f2d54dd07922",
	"tpUserId":"123456",
	"tpMobile":"18612667433"
}
```
返回结果：

```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": "{
			"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxLU9TcFZjYnhkOXc0SlFhK0FwaVRDbU5MbjVCRnNv"
    }"
}

```

#  API对接接口（调整中）


##3.1组织架构

###3.1.1 添加第三方员工
请求方式|请求地址
----|---
POST|/open/api/auth/third/user/create

请求参数
字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.employeeList|员工信息 |array |Y|
data.employeeList.name |员工信息 |string |Y|
data.employeeList.phone |员工信息 | string |Y|
data.employeeList.orgUnitId |员工信息 | string |Y|
data.employeeList.thirdEmployeeId |员工信息 | string |Y|



请求示例

```
{ "access_token": "xxx.xxx.xxx",  "timestamp": 123456789,  "employee_id":12345678,  "sign": "jifejfwojelajflejf",  "data":  {  
    "employeeList":[
      {
        "name":"张5s",
        "phone":"13718432812",
        "orgUnitId":"5747fbc10f0e60e0709d8d7d",
        "thirdEmployeeId":"57ab054c2528226a805bd5e1"
      }
    ]   }
}
```


返回结果
```
{   "request_id": "LaZNvBntsBD20nJ7ekgn",   "code": 0,   "msg": "success",   "data": {           }}
```





###3.1.2 查询部门
请求方式|请求地址
----|---
POST|/open/api/org/departments/detail

请求参数
字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.org_ unit_id|部门ID |string |Y|
 
请求示例

```
{ "access_token": "xxx.xxx.xxx",  "timestamp": 123456789,  "employee_id":12345678,  "sign": "jifejfwojelajflejf",  "data":  {   "org_unit_id":"综合部" }
}
```
返回结果
```
{   "request_id": "LaZNvBntsBD20nJ7ekgn",   "code": 0,   "msg": "success",   "data": {           }}
```

###3.1.3 添加部门
请求方式|请求地址
----|---
POST|/open/api/org/departments/create


请求参数:

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.org\_unit\_name|部门名称|string|Y|
data.parent\_id| 父部门 id|string |Y|
data.org\_unit\_id|部门 id| string |Y|
 
 请求示例:
 ```
{"access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data": {   "org_unit_name":"综合部",   "org_unit_id":"xxxx",   "parent_id":"xxxxx" }
}
```

返回结果

```

{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```
###3.1.4 修改部门
修改企业部门
请求方式|请求地址
----|---
POST|/open/api/org/departments/update

请求参数

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.org\_unit\_id|部门ID |string|Y|
data.org\_unit\_name|部门名称| string |Y|
data.parent\_id| 父部门 id|string |Y|
data.manager\_list||array|N|

请求示例
```
{"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf",	"data":	{	 "org_unit_id":"idexample",	 "org_unit_name":"name",	 "parent_id":"parent_id_example",	 “manager_list”:[“id1”,”id2”]	}
}
```

返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```

###3.1.5 删除部门(支持批量删除)根据企业ID删除部门请求方式|请求地址
----|---
POST|/open/api/org/departments/delete

请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data |请求数据| jsonstring |Y|
data.org\_ unit\_ids| 部门id|array |Y|
 
 请求示例
```
{"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf",	"data":	{	 "org_unit_ids":["idexample",”idslfiaesj”]	 	}
}
```

返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```

###3.1.6 添加员工根据企业ID添加员工信息请求方式|请求地址
----|---
POST|/open/api/org/employees/create

请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee_id| 三方员工id|string|Y| 三方员工id  
 data.employee.phone| 手机号| string | Y| 13988987443
 data.employee.name|姓名 | string | Y| 张三
 data.employee.gender| 性别| string | Y|  1 
 data.employee.birth\_date| 生日| string | Y| yyyymmdd
 data.employee.employee\_id |员工 id| string | Y| 
 data.org\_unit_ids|  所属部门|string| |Y| 
data.cert\_list|证件 | array|Y| 
 data.cert\_list.cert\_type|证件类型 | string |Y| 
 data.cert\_list.cert\_no| 证件号| string |Y| 2211239012r28351
data.role|角色|string|Y| 
data.biz\_trip_policy||jsonstring |Y| 
data.biz\_trip\_policy.air\_priv\_flag|机票是否需要审批|boolean|Y| 机票权限
data.biz\_trip\_policy.air\_verify\_flag| |boolean|Y|
data.biz\_trip\_policy.hotel\_priv\_flag|酒店权限 |boolean|Y| 
data.biz\_trip\_policy.hotel\_verify\_flag|酒店是否需要审批 |boolean|Y| 
data.biz\_trip\_policy.train\_priv\_flag |火车权限 |boolean|Y|
data.biz\_trip\_policy.train\_verify\_flag| 火车是否需要审批|boolean|Y| 
data.biz\_trip\_policy.rule\_limit\_flag| 是否限制差旅规 |boolean|Y|
data.biz\_trip\_policy.rule\_id|差旅规则 |boolean|Y|  
data.biz\_trip\_policy.exceed\_buy\_flag|允许超标 |boolean|Y| 
data.car_policy| | jsonstring|N| 
data.car_policy.car\_priv\_flag| | boolean |N| 
data.car_policy.rule\_limit\_flag| | boolean |N| 
data.car_policy.rule\_id| | boolean |N| 
data.car_policy.exceed\_buy\_flag| | boolean |N| 
data.mall_policy|jsonstring| | N ||
data.mall_policy.mall\_priv\_flag| | boolean |N|
data.mall_policy.rule\_limit\_flag| | boolean |N| 
data.mall_policy.rule\_id| | boolean |N|  
data.mall_policy.exceed\_buy\_flag| | boolean |N|

  
 请求示例:``` 

{
 "access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data":{    "third_employee_id":"xxxx",    "employee": {        "phone": "13988987443",        "name": "hello",        "gender": 1,        "birth_date": "yyyymmdd",        "status": 1    },    "org_unit_ids": [        "abc",        "def"    ],I    "cert_list": [        {            "cert_type": 1,            "cert_no": "2211239012r28351"        }    ],    "role": 1,    "biz_trip_policy": {        "air_priv_flag": false,        "air_verify_flag": true,        "hotel_priv_flag": true,        "hotel_verify_flag": false,        "train_priv_flag": true,        "train_verify_flag": false,        "rule_limit_flag": true,        "rule_id": "575263e982f880a6d686ce11",        "exceed_buy_flag": false    },    "car_policy": {        "car_priv_flag": true,        "rule_limit_flag": true,        "rule_id": 2,        "exceed_buy_flag": false    },    "mall_policy": {        "mall_priv_flag": true,        "rule_limit_flag": true,        "rule_id": "ofaijwf",        "exceed_buy_flag": false    }}}

```

返回结果

```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}

```

###3.1.7 修改员工
根据企业ID修改员工信息
请求方式|请求地址
----|---
POST|/open/api/org/employees/update
(同添加员工)



请求参数：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee_id| 三方员工id|string|Y| 三方员工id  
 data.employee. phone || string | Y| 手机号:13988987443
 data.employee. name| | string | Y| 姓名：张三
 data.employee. gender| | string | Y| 性别 1 
 data.employee. birth_date| | string | Y| 生日yyyymmdd
 data.employee. employee_id| | string | Y| 员工 id
 data.org_ unit_ids| string| |Y|  所属部门
data.cert_list|| array|Y| 证件 
 data.cert\_list. cert_type| | string |Y| 证件类型
 data.cert\_list. cert_no| | string |Y| 证件号2211239012r28351
data.role||string|Y| 角色
data.biz\_ trip_policy||jsonstring |Y| 
data.biz\_ trip\_policy. air\_priv\_flag| |boolean|Y| 机票权限
data.biz\_ trip\_policy. air\_verify\_flag| |boolean|Y| 机票是否需要审批
data.biz\_ trip\_policy. hotel\_priv\_flag| |boolean|Y| 酒店权限
data.biz\_ trip\_policy. hotel\_verify\_flag| |boolean|Y| 酒店是否需要审批
data.biz\_ trip\_policy. train\_priv\_flag| |boolean|Y|火车权限 
data.biz\_ trip\_policy.train\_verify\_flag| |boolean|Y| 火车是否需要审批
data.biz\_ trip\_policy. rule\_limit\_flag| |boolean|Y| 是否限制差旅规
data.biz\_ trip\_policy. rule_id| |boolean|Y|差旅规则  
data.biz\_ trip\_policy. exceed\_buy\_flag| |boolean|Y| 允许超标
data. car_policy| | jsonstring|N|
data. car_policy.exceed\_ buy\_flag| | boolean|N|
 data. mall_policy | Object|N|
 data. mall_policy.mall\_ priv\_flag| | boolean |N|
 
 
 请求示例``` 

{
 "access_token": "xxx.xxx.xxx","timestamp": 123456789,"employee_id":12345678,"sign": "jifejfwojelajflejf","data":{
	"employee_id":"xxxxxx",    "employee": {        "phone": "13988987443",        "name": "hello",        "gender": 1,        "birth_date": "yyyymmdd",        "status": 1    },    "org_unit_ids": [        "abc",        "def"    ],I    "cert_list": [        {            "cert_type": 1,            "cert_no": "2211239012r28351"        }    ],    "role": 1,    "biz_trip_policy": {        "air_priv_flag": false,        "air_verify_flag": true,        "hotel_priv_flag": true,        "hotel_verify_flag": false,        "train_priv_flag": true,        "train_verify_flag": false,        "rule_limit_flag": true,        "rule_id": "575263e982f880a6d686ce11",        "exceed_buy_flag": false    },    "car_policy": {        "car_priv_flag": true,        "rule_limit_flag": true,        "rule_id": 2,        "exceed_buy_flag": false    },    "mall_policy": {        "mall_priv_flag": true,        "rule_limit_flag": true,        "rule_id": "ofaijwf",        "exceed_buy_flag": false    }}}

```

返回结果
```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```

###3.1.8 查询员工信息(不支持批量查询)

根据企业ID和员工ID查询员工信息
请求方式|请求地址
----|---
POST|/open/api/org/employees/detail

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|1位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data. employee\_id|操作人id | String |Y|


请求示例```
{
	"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf"	"data":	{    	employee_id:"faxxx12399004392293840274"	}}

```

返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```

###3.1.9 删除员工(不支持批量删)

根据企业ID和员工ID删除员工请求方式|请求地址
----|---
POST|/open/api/org/employees/delete

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access\_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
data || jsonstring |Y|
data.employee\_id| 操作人id|员工ID| String |Y|
 
 请求示例```
{
	"access_token": "xxx.xxx.xxx",	"timestamp": 123456789,	"employee_id":12345678,	"sign": "jifejfwojelajflejf"	"data":	{    	employee_id:"faxxx12399004392293840274"	}}

```

返回结果```
{    "request_id": "LaZNvBntsBD20nJ7ekgn",    "code": 0,    "msg": "success",    "data": {            }}
```



## 3.2 API接入说明
### 3.2.1 签名算法
需参与鉴权的参数定义:
1.分贝通颁发的sign\_key需要作为参数参与签名,且不参与传递;2.sign=md5(timestamp=xxxx&data="xxxx"&sign\_key="xxx)转小写,注意顺序;
3.MD5采用org.apache.commons下DigestUtils.md5Hex(param)加密；

字段|名称|类型|必填|描述
----|----|---|---|---
timestamp|时间戳|long|Y|13位时间戳
sign_key|签名key|string|Y|鉴权接口获得的口令
data|请求的业务参数|jsonstring|Y|

###3.2.2消息回调说明
1.消息回调数据格式为application/json传递
2.登录相应的管理后台，企业进行相应的回调地址的配置，根据企业配置的接口进行相应回调信息的接收


## 3.3 鉴权接口，颁发Token
根据企业appId/appKey等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/api/auth/v1/dispense

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
----|----|---|---|---
app_id|企业ID|String|Y|
app_key|企业key |String|Y|
app_type|类型|String|N|预留字段

请求示例：

```
{
	"appId":"5747fbc10f0e60e0709d8d722",
	"appKey":"59b74c1323445f2d54dd07922"
}
```
返回结果：

```
    "request_id": "RqnwAR3En48ZbaMfa6Ub",
    "code": 0,
    "msg": "success",
    "data":{"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ0b2tlbiIsImFwcElkIjoiNTc0N2ZiYzEwZjBlNjBlMDcwOWQ4ZDdkIiwiaXNzIjoiYXBpIiwiZXhwIjoxNTA3NTE1ODQ5LCJqdGkiOiI1OWNkYWVjOTIyZTlmMTRlNmI0YTkwNTIifQ.oPgr-a_95RxyZqMj2pzeOBb4vfMCz0ACED2L-fWIdnU"}
}

```

## 3.4 消息回调
###3.4.1机票消息回调


字段|名称|类型|必填|详情
----|----|---|---|---
orderId|订单id|String| Y | hksf83ho93lsbvnos145
totalPrice|订单金额 | Double| Y |344.33
typeName|订单类型名称 |String| Y |机票
type |订单类型| Integer | Y |机票:1
status |订单状态|Integer| Y |出票中:1700，出票成功:1800
companyId |公司id|String| Y | 5747fbc10f0e60e0709d8d89
companyName| 公司名称|String|Y|分贝通



数据格式:


```
{
	"orderId":"hksf83ho93lsbvnos145",
	"totalPrice": 344.33,
	"typeName":"机票",
	"type":1,
	"status":1700,
	"companyId":"5747fbc10f0e60e0709d8d89",
	"companyName":"分贝通"
	

}


```

###3.4.2用车消息回调


字段|名称|类型|必填|详情
----|----|---|---|---
orderId|订单id|String| Y |9884hhkhfsk
totalPrice|订单金额 | Double| Y |777.88
typeName|订单类型名称 |String| Y |用车
type |订单类型| Integer | Y |用车:2
status |订单状态|Integer| Y |已完成:700
companyId |公司id|String| Y | 5747fbc10f0e60e0709d8d89
companyName| 公司名称|String|Y|分贝通


数据格式:


```
{
	"orderId":"hksf83ho93lsbvnos145",
	"totalPrice": 344.33,
	"typeName":"用车",
	"type":2,
	"status":400,
	"companyId":"5747fbc10f0e60e0709d8d89",
	"companyName":"分贝通"
	

}


```


## 3.5 机票

### 3.5.1 机票列表

请求方式|请求地址
----|---
POST|/open/api/flight/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.name\_or\_phone|乘机人/下单人姓名/手机|string|N| 如 老王/13800
data.name\_or\_phone\_type|乘机人/下单人姓名/手机号类型|string| N | （0:全部(默认值) 1:乘机人 2:下单人）
data.search\_category|搜索维度| Integer | N | 1:企业 2:个人
data.state|查询状态|Integer|N|  0:全部(默认值) 1:处理中 2:已完成
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| Integer | N | 1(默认值)
data.page\_size|每页显示条数| Integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":"0",
		"page_index":"1",
		"data.page_size":"10",
		"search_category":"0",
		"order_ date_begin":"2017-01-01",
		"order_ date_end":"2017-05-01",
		"name_ or_phone":"123456",
		"name_ or_ phone_type":"1"
				
	}
}


```



响应结果：

```


{  "code": 0,  "msg": "success",  "data": {    "results": [      {        "order_id": "58e74c125d88db6664226ac8",        "remote_order_id": "112017040184019946",        "create_time": "2017-05-04 13:28:57",        "total_price": -1948,        "passenger_list": [          "汪远"        ],        "status": 1811,        "status_info": "退票成功",        "segment_info": {          "flight_no": "CA1835",          "airline_name": "中国国航",          "starting_code": "PEK",          "starting_city": "北京",          "destination_code": "PVG",          "destination_city": "上海",          "departure_timestamp": 0,          "arrived_timestamp": 0        },        "can_process": false      },      {        "order_id": "58deb1975d88db0e98febc28",        "remote_order_id": "112017040184019935",        "create_time": 1490989482042,        "total_price": 2160,        "passenger_list": [          "刘维中",          "汪远"        ],        "status": 1211,        "status_info": "已取消",        "segment_info": {          "flight_no": "MF8518",          "airline_name": "厦门航空",          "starting_code": "SHA",          "starting_city": "上海",          "destination_code": "XMN",          "destination_city": "厦门",          "departure_timestamp": 0,          "arrived_timestamp": 0        },        "can_process": false      }    ],    "total_count": 16  }}


```



### 3.5.2 机票订单详情
根据订单id查询机票详情

请求方式|请求地址
----|---
POST|/open/api/flight/order/detail

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| |String|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.order_id |机票订单id|String|Y|

请求示例：

```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"timestamp":124124325,
	"sign":"oihfnlyeofdh98",
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"523234c1323445f2d54dd0"
	}
}

```


返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
total_price |订单金额| Inreger|Y| 453
status. key |订单状态	| string | Y |1900:有退改签
order_id |订单号	| string | Y|59b5fe4a2798631761f29db8
order_owner.name |预定人| string|Y| "name": "辛植"
create_time|订单创建时间|string|Y|2017-09-11 11:08:58
ticket_no |票号| string | Y | 784-2310286513
cost_attribution |费用归属| string|Y|例：研发部
airline_name |航空公司| string|Y|例：吉祥航空
flight_no |航班号	|string| Y |HO1252
passenger_info .name |乘机人姓名| string |Y| name:"辛植"
identity\_type_name.key |证件类型|string|Y|0.未知 1:身份证  2.护照 3.回乡证 4.台胞证
phone |乘机人手机号| string|Y|16676823457
identity_no |乘机人证件号| string | Y |数字，英文字母
status.key |机票状态| string|Y| 1811:退票成功 
refund_amount |退款金额| Integer |Y|  1600
refund_fee |手续费| Integer | Y |100
seat_msg |舱位| string |Y|头等舱/商务舱
starting_city |出发城市| string | Y |北京
starting_airport |出发机场| string|Y|中英文  首都国际机场
starting_code |出发航程三字码| string | Y |PEK
starting_terminal |起飞航站楼| string |Y|首都T3
departure_timestamp |起飞时间| string | Y|1507079400000
destination_city|到达城市| string|Y| 上海destination_airport |到达机场| string|Y|虹桥国际机场
destination_code|到达航程三字码|string|Y|SHA
destination_terminal |到达航站楼| string |Y|T4
arrived_timestamp |到达时间|Integer | Y | 1537099400000
par_price|机票单价| Integer |Y|3370
airport_tax |机建| Integer | Y |50
fuel_tax |燃油| Integer| Y |44
coupon_amount|订单优惠券	| Integer |Y|例：20
category_code|险种| string|Y| 1:航意险，2：航延险
policy_number |保单编号| string|Y|10450061900247380997
status.key |保单状态| Integer |Y|8:退保成功
insurant_name |被保人| string |Y|张胜男
insurant_amount |数量| Integer | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
unit_price|保费| Integer |Y|
type |乘客类型| Integer |Y|0:成人,1:婴儿


```
{
    "request_id": "Ml4VL4moJ6VtKbG2vE83",
    "code": 0,
    "msg": "success",
    "data": {
    		"order_id": "576b917bdec24c7c091d2f72",			"remote_order_id": "102016062360137545",    		"create_time": 1466667402270,   			"can_process": false,   			"cost_attribution":  "",    		"total_price": 7540,    		“apply_id”:”23423sdrefds”,//审批单ID    		“exceeded”:false, //是否已超标    		“exceed_info” :{				“reason”:”就是要超”,     //超标理由				“comment”:”超标补充说明”    		},   			"check_info":[			{				"title":"未选择最低价格理由",				"reason":"陪客户出行",				"comment":"额外补充"			},			{				"title":"未提前3天预订机票",				"reason":"陪领导出差",				"comment":"额外补充"			},  		],    	"passenger_list": [      {        "passenger_info": {          "identity_type": "1",          "identity_no": "410183198603180012",          "name": "王超",          "type": 0        },        "ticket_no": "xxxxxxxxx",        "status": {     //机票状态				"key":1800,				"value":"出票成功"					},        "product_id": "5774c54f7a3170af796ba290",        "refund_info": {          "refund_amount": 700,          "refund_amount_msg": "退票处理中",          "refund_fee": 300,          "refund_fee_msg": "退票处理中"        },        "change_info": {          "upgrade_price": 300,          "upgrade_price_msg": "改签处理中",          "change_fee": 200,//改签费          "agency_fee": 10,//改签手续费          "change_fee_msg": "改签处理中"        }      }    ],   "status": {     //订单状态		"key":1800,"value":"出票成功"},    "segment_info": {      "starting_terminal": "T3",      "cabin": "F",      "plane_type": "787",      "arrived_time": "0940",      "destination_terminal": "T2",      "destination_code": "SHA",      "seat_msg": "头等舱",      "starting_code": "PEK",      "departure_time": "0730",      "is_middle_stop": "false",      "flight_no": "CA1831",      "departure_date": "2016-10-20",      "departure_timestamp": 1476919800000,      "arrived_timestamp": 1476927600000,      "starting_city": "北京",      "starting_airport": "首都国际机场",      "destination_city": "上海",      "destination_airport": "虹桥国际机场",      "airline_name": "中国国际航空",      "code_share": false,      "share_airline_name": "",      "share_num": ""    },    "price_info": {      "settle_price": 329.8,      "discount": 3,      "par_price": 3720,      "fuel_tax": 0,      "airport_tax": 50,      "coupon_amount": 20    },    "policy_info": {      "policy_id": "111402007"    },    "stipulate_info": {      "cabin": "F",      "par_price": 3720,      "modify_stipulate": "可以改签;",      "comment": "",      "refund_stipulate": "取消座位时间计算手续费;按照当前舱位票面价收取退票费;起飞前免收退票费,起飞后收取当前舱位票面价的10.0%退票费;",      "change_stipulate": "按照当前舱位票面价收取变更费;起飞前免收改期费,起飞后收取当前舱位票面价的5.0%改期费;"    },    "contact_name": "王超",    "contact_phone": "18610297769",    "order_owner": {      "id": "57613c435eac323d0c174216",      "name": "汪识瀚",      "phoneNum": "13717505875",      "loginInfo": {        "providerID": "credentials",        "providerKey": "13717505875"      },      "role": {        "key": 3,        "value": "普通员工"      },      "status": {        "key": 1,        "value": "启用"      }    },    "remark_reson": "remark_reson",    "remark_detail": "remark_detail",    "comment": "",    "insurance_info": [         //保险字段      {        "category_code": 1,        "category_name": "航意险",        "desc": "最高保额10000元，让关心你的人更放心",        "desc_link": "平安航延险说明链接",        "unit_price": 30,        "insurant_list": [          {            "premium": 30,            "insurant_name": "李四",            "status": {              "key": 5101,              "value": "已投保"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {              "url": "http://15607.corp.51zxtx.com/177474/				polices/{policyNumber}",              "headers": [                {                  "name": "Content-Type",                  "value": "application/pdf"                },                {                  "name": "X-Zxtx-Sign",                  "value": 					"5A492D6F67169DDA7F83611FCAD5B30C"                }              ]            }          },          {            "premium": 30,            "insurant_name": "张三",            "status": {              "key": 5101,              "value": "投保中"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {    }          }        ]      },      {        "category_code": 2,        "category_name": "航延险",        "unit_price": 30,        "desc": "最高保额10000元，让关心你的人更放心",        "desc_link": "平安航延险说明链接",        "insurant_list": [          {            "premium": 30,            "insurant_name": "李四",            "status": {              "key": 5101,              "value": "投保中"            },            "policy_number": "1000191573",            "start_date": "2017-03-20",            "end_date": "2017-03-21",            "insurance_link": {}          }        ]      }    ]   
        }
}
```



## 3.6 用车




### 3.6.1 用车列表

请求方式|请求地址
----|---
POST|/open/api/car/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.search\_category|搜索维度| Integer | N | 1:企业 2:个人
data.state|查询状态|Integer|N|  0:全部(默认值) 1:处理中 2:已完成
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| Integer | N | 1(默认值)
data.page\_size|每页显示条数| Integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":"0"
	}
}
```



响应结果示例：


```

{
    "code": 0,
    "msg": "Success",
    "data": {
        "results": [
            {
                "order_id": "596dcb622798634dbc16768b",
                "vorder_id": "1125899951260423",
                "departure_name": "世贸国际公寓",
                "departure_lat": 39.914876,
                "departure_lng": 116.451379,
                "arrival_name": "物资学院路[地铁站]",
                "spec": {
                    "id": 600,
                    "name": "快车"
                },
                "type": 0,
                "status": 610,
                "status_info": "已取消",
                "price": 0,
                "order_time": "2017-07-18 16:48:34",
                "schedule_time": "2017-07-18 16:48:34",
                "can_process": true,
                "vendor_id": 1,
                "vendor_name": "滴滴",
                "type_name": "实时",
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "driver_info": {}
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
                "can_process": true,
                "vendor_id": 1,
                "vendor_name": "滴滴",
                "type_name": "预约",
                "arrival_lat": 39.926776,
                "arrival_lng": 116.639717,
                "spec_name": "快车",
                "driver_info": {}
            }...
        ],
        "total_count": 247
    }
}

```



###3.6.2 用车订单详情

根据企业appId/appKey等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/api/car/order/detail

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|String|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.order_id| 用车订单id|String|Y|

请求示例：

```
{
	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"order_id":"523234c1323445353dd0"
	}
}
```
返回结果：


字段|名称|类型|必填|描述
----|---|---|---|---
total_price |订单金额| Integer | Y |88
status.key|订单状态| Integer |Y|99
departure_place.name |出发地| string|Y|例：北京
arrival_place.name |目的地| string | Y |例：上海
em_name | 下单人| string | Y |例：韩冰
em_tel |下单人手机号| string |Y|例：15070713001
order_time |下单时间| string | Y |2017-09-11 11:08:58
cost_attribution |费用归属| string |Y|乘机人1/乘机人2/
type |用车类型| string | Y |0：实时；1：预约；2：接机；3：送机
spec.id |车辆类型	|Integer|Y| 100:舒适；400：七座商务；200：豪华型；600:快车
vendor.key |供应商| Integer |Y|2：神州
driver_name|司机姓名| string|Y|王师傅，dave han
driver_card |车牌号	| string | Y |英文字符,数字
driver\_car_type |品牌车型| string |Y|别克
driver_level |司机评分| string | Y |5.0
driver\_order_count|接单数| string|Y|3
tel |用车人手机号| string | Y |例：15070713088
begin\_charge_time |出发时间	| string | Y |
finish\_charge_time |到达时间| array|Y|
category_code |保险险种| Integer | Y |
policy_number | 保单编号| string|Y|
status |保单状态	| string | Y |
insurant_name |被保人姓名|string|Y|
insurant_amount |保险数量| Integer | Y |保单数量，根据保单号来进行数量判断，每个保单号会有一个保单,定义为保留字段
premium |保险保费| Double |Y|




```


{
    "code": 0,
    "msg": "success",
    "data": {
        "order_id": "595242ef1a671d2446d8dc82",
        "vorder_id": "1031014486130567180",
        "can_process": true,
        "cost_attribution": "北京分贝金服科技有限公司",
        "em_name": "常龙",
        "em_tel": "18911681154",
        "tel": "18911681154",
        "status": 700,
        "sub_status": 0,
        "sub_status_name": "",
        "status_info": "已完成",
        "city": 1,
        "city_name": "",
        "type": 0,
        "total_price": 23.56,
        "price_detail": [
            {
                "name": "正常行驶距离费",
                "amount": 0.16,
                "type": "normal_fee"
            },
            {
                "name": "快车时长费",
                "amount": 22.4,
                "type": "normal_time_fee"
            },
            {
                "name": "企业实付金额",
                "amount": 22.56,
                "type": "company_real_pay"
            },
            {
                "name": "企业应付金额",
                "amount": 22.56,
                "type": "company_pay"
            },
            {
                "name": "短途意外险",
                "amount": 1,
                "type": "insurance"
            }
        ],
        "coupon_amount": 0,
        "driver_info": {},
        "spec": {
            "id": 600,
            "name": "快车"
        },
        "distance": 0.1,
        "order_time": "2017-06-27 19:35:23",
        "schedule_time": "2017-06-27 19:35:23",
        "departure_place": {
            "name": "东大桥路24号楼",
            "address": "北京市朝阳区光华路甲9号东大桥路",
            "dlat": 39.9150390625,
            "dlng": 116.4510498046875
        },
        "arrival_place": {
            "name": "团结湖-地铁站",
            "address": "地铁10号线",
            "tlat": 39.933722,
            "tlng": 116.461743
        },
        "is_complaint": false,
        "comment": null,
        "remark_reason": "出差",
        "remark_detail": "去北京",
        "insurance_info": [
            {
                "category_code": 4,
                "category_name": "短途意外险",
                "desc": "1元最高保障10万元",
                "desc_link": "https://static.fenbeitong.com/mobile/carAccidentInsurance.html",
                "unit_price": 1,
                "insurant_list": [
                    {
                        "insurant_name": "常龙",
                        "premium": 1,
                        "status": {
                            "key": 6,
                            "value": "投保成功"
                        },
                        "policy_number": "",
                        "start_date": "2017-06-27",
                        "end_date": "2017-06-28",
                        "insurance_link": {}
                    }
                ]
            }
        ],
        "exceeded": false
    }
}

```


## 3.7 火车
###3.7.1 订单列表

根据企业appId/appKey等参数请求鉴权接口，返回请求Token

请求方式|请求地址
----|---
POST|/open/api/train/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|String|Y|类型，0为分贝用户，1为第三方用户
data || jsonstring |Y|
data.state| 查询状态|Integer |Y|0全部，1正处理，2已完成
data.name\_or\_phone|乘客/下单人姓名/手机号 |string |N|
data.name\_or\_phone\_type|乘客/下单人姓名/手机号类型 |string | N |
data.search\_category |搜索维度| Integer | N |
data.order\_date\_begin |下单开始日期|string | N |yyyy-MM-dd
data.order\_date\_end|下单结束日期 |string | N |yyyy-MM-dd
data.page\_index |页码| Integer |  N |1(默认值)
data.page\_size|每页显示条数| Integer|  N |10(默认值)


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
    "request_id": "IOCCucbNYCDEkCOOakDP",
    "code": 0,
    "msg": "success",
    "data": {
        "results": [
            {
                "order_id": "59e456cd2798636090cdf339",
                "status": {
                    "key": 3101,
                    "value": "已取消"
                },
                "departure_time": 1509686700000,
                "arrival_time": 1509691260000,
                "train_code": "6026",
                "passenger_names": [
                    "韩树起"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            },
            {
                "order_id": "59e4526b2798636090cdf30c",
                "status": {
                    "key": 3203,
                    "value": "出票失败"
                },
                "departure_time": 1509686700000,
                "arrival_time": 1509691260000,
                "train_code": "6026",
                "passenger_names": [
                    "韩梅梅"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            },
                       {
                "order_id": "59df44392798637cf9d5913a",
                "status": {
                    "key": 3400,
                    "value": "有退改纪录"
                },
                "departure_time": 1510205100000,
                "arrival_time": 1510209660000,
                "train_code": "6026",
                "passenger_names": [
                    "韩树起"
                ],
                "from_station_name": "九江",
                "to_station_name": "武穴",
                "total_price": 3,
                "can_process": true
            }
        ],
        "total_count": 6
    }
}


```


## 3.8 酒店
### 3.8.1 酒店订单列表

请求方式|请求地址
----|---
POST|/open/api/hotel/order/list

请求参数，以application/x-www-form-urlencoded传递：

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|
access_token|token | string |Y|登录 token
employee\_id| 操作人id|string |Y|操作人id,调用接口人 id
employee\_type| 用户类型|String|Y|0为分贝用户，1为第三方用户
data |请求数据| jsonstring |Y|
data.state|查询状态|Integer|Y|  0:全部(默认值) 1:处理中 2:已完成
data.name\_or\_phone|乘机人/下单人姓名/手机|string|N| 如 老王/13800
data.name\_or\_phone\_type|乘机人/下单人姓名/手机号类型|string| N | （0:全部(默认值) 1:乘机人 2:下单人）
data.search\_category|搜索维度| Integer | N | 1:企业 2:个人
data.order\_date\_begin|下单开始日期|string| N |格式为 yyyy-MM-dd  2017-01-01
data.order\_date\_end|下单结束日期|string|N|格式为 yyyy-MM-dd 2017-05-01
data.page\_index|页码| Integer | N | 1(默认值)
data.page\_size|每页显示条数| Integer |N| 10(默认值)
请求示例：


```
{	"access_token":"5747fbc10f0e60e0709d8d722",
	"sign":"oihfnlyeofdh98",
	"timestamp":124124325,
	"employee_id":"59b74c1323445f2d54dd07922",
	"employee_type":1,
	"data":{
		"state":"0"					
	}
}


```



响应数据：

```

{ "request_id": "IOCCucbNYCDEkCOOakDP",  "code": 0,  "msg": "Success",  "data": {    "results": [      {        "order_id": "58eaf3285d88db107e2fc0da",        "status": 2700,        "status_name": "已关闭",        "checkin_date": 1492012800000,        "checkout_date": 1492185600000,        "hotel_address": "北京朝阳区弘善家园414号楼",        "hotel_code": "204_91725321",        "hotel_name": "北京市柠檬树家庭旅馆十里河店",        "hotel_lat": "0.000000",        "hotel_lng": "0.000000",        "hotel_phone": "18911949793",        "price": 466,        "can_process": false      },      {        "order_id": "58e761235d88db6828665237",        "status": 2800,        "status_name": "退订成功",        "checkin_date": 1493136000000,        "checkout_date": 1493222400000,        "hotel_address": "海淀区西二旗大街与西二旗东一路交界,G6八		 达岭高速西侧,龙兴园南区北面",        "hotel_code": "204_10101487",        "hotel_name": "格林豪泰(北京西三旗桥商务酒店)",        "hotel_lat": "0.000000",        "hotel_lng": "0.000000",        "hotel_phone": "62920998",        "price": -207,        "can_process": false      }    ],    "total_count": 26  }}


```



## 3.9 公用
### 3.9.1 根据城市获取机票机场列表和火车站列表

请求方式|请求地址
----|---
POST|/open/api/common/city-list



字段|名称|类型|必填|描述
----|----|---|---|---
access_token|api鉴权Token|String|Y|
sign|签名|String|Y|
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|String|Y|分贝用户id或者第三方用户id
employee\_type| 用户类型|String|Y|类型，0为分贝用户，1为第三方用户
data |请求数据|jsonstring|Y|
data.type|业务类型 | String |Y|1.火车，2，机票
data.city\_key|城市关键字 |String|Y|北京
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


## 3.10 审批单
###3.10.1 创建审批单


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
data.apply.id |申请单id|String|Y|
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


#  状态码




##4.1 机票状态码
### 4.1.1 机票订单状态码表

状态码|说明|
----|---|---
1100|待支付
1211| 已取消 
1400| 已关闭
1700|出票中
1800|出票成功
1801|出票失败
1811|退票成功
1820|改签中
1821|改签成功
1900|有退改签


###4.1.2 机票状态码表

状态码|说明|
----|---|---
1100|待支付
1211| 已取消 
1400| 已关闭
1700|出票中
1800|出票成功
1801|出票失败
1810|退票中
1811|退票成功
1812|退票失败
1820|改签中
1821|改签成功
1822|改签失败
1900|有退改签



##4.2 用车状态码
###4.2.1用车订单状态码表

状态码|说明|
----|---|---
300 |等待应答	
311 | 订单超时	
350 | 预约成功	
351| 预约失败
400 |等待接驾	
410 |司机已到达	
500 |行程中
600 |行程结束	
610 |已取消	
700 |已完成

##4.3 火车状态码
###4.3.1 火车票下单返回状态码表

字段|说明
-----|----
100501|需要审批
100502|已传入审批单，但不可用
100601|超标理由不能为空且小于50字
100602|超标理由补充说明不能多于200字
100603|允许超标，但需要超标理由
100604|不允许超标




###4.3.2 火车票订单状态码表

字段|说明
----|---
3100|待支付
3101|已取消
3102|已关闭
3201|出票中
3202|出票成功
3203|出票失败
3400|有退改记录
3600|退改进行中
3703|改签成功
3801|退票成功


###4.3.3 火车票状态码表


字段|说明
-----|----
3100|待支付
3101|已取消
3102|已关闭
3201|出票中
3202|出票成功
3203|出票失败
3700|占座中
3701|占座成功
3702|占座失败
3703|改签成功
3704|改签失败
3705|改签取消
3706|改签已确认
3800|退票中
3801|退票成功
3802|退票失败


##4.4 酒店状态码

###4.4.1 酒店订单状态码表


字段|说明
-----|----
2100|订单创建中
2101|订单创建失败
2200|待支付
2210|支付中
2300|订单取消中
2301|已取消
2401|已支付
2500|订房中
2501|订房成功
2502|订房失败
2700|已关闭
2800|退订成功
2801|退订中
2802|退订失败






	
##4.5 保险状态码
### 4.5.1 保单订单状态码表

状态码|说明|
----|---|---
1|待支付
2| 待投保
3| 已取消
4|投保中
5|投保成功
6|投保失败
7|退保中
8|退保成功
9|退保失败




