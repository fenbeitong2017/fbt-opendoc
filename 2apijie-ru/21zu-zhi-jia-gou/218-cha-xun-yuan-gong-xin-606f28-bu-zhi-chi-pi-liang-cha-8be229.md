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


请求示例

	"access_token": "xxx.xxx.xxx",

```

返回结果

