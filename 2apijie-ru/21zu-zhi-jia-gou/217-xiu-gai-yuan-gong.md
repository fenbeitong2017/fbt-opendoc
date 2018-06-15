2.2.2.1更新第三方员工

#####  **接口说明**
- 1.**老接口(不建议采用)**
- 2.支持批量更新,该接口更新操作只可以进行修改用户相关信息，
 不能修改权限相关信息，权限还是默认管理后台现有的权限



请求方式|请求地址
----|---
POST|/open/api/third/employees/update


请求参数

字段 | 名称 | 类型 | 必填 | 描述 |
--- | --- | --- | --- | --- |
access_token|api鉴权Token|string|Y|
sign|签名|string|Y||
timestamp|时间戳 |long|Y|13位时间戳
employee\_id| 用户ID|string|Y|第三方用户id
employee\_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data| 请求数据 | jsonstring | Y | |
data.employee\_list | 员工信息 | jsonarray | Y ||
data.employee\_list.name | 员工姓名 | string | Y |张三|
data.employee\_list.phone | 员工手机号 | string | Y |16090190901|
data.employee\_list.org\_unit\_name | 部门名称| string | Y |员工部门名称，分贝通科技有限公司/研发部/后端服务
data.employee\_list.third\_employee\_id | 第三方员工ID | string | Y ||

请求示例

```
{ "access_token": "xxx.xxx.xxx",
"timestamp": 123456789,
"data":
{
"employee_list":[
{
"name":"张5s",
"phone":"13718432812",
"org_unit_name":"分贝通科技有限公司/研发部/后端服务",
"third_employee_id":"57ab054c2528226a805bd5e1"
}
]
}
}
```

返回结果


```
{
"request_id": "LaZNvBntsBD20nJ7ekgn",
"code": 0,
"msg": "success",
"data": {
}
}




{
"request_id": "LaZNvBntsBD20nJ7ekgn",
"code": 0,
"msg": "success",
"data": {
"result": [
{
"name": "张三(姓名)",
"phone": "13718432817（手机号）",
"companyId": "57ab054c2528226a805bd5e1(公司id)",
"thirdEmployeeId": "57ab054c2528226a805bd5e1(第三方用户id)",
"errorMsg": "手机号已存在"
}
]
}
}


```