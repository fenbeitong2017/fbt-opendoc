1.1.2 获取access_token:

 请求方式 | 请求地址 
 --- | --- 
 POST | /open/api/auth/v1/dispense

请求参数，以application/x-www-form-urlencoded传递：



术语|是否必填|说明
----|---|---
app_id|Y|申请时分配的app_id|
app_key|Y|申请时分配的app_key，与app_id一起用于认证授权
sign_key|N|申请时分配的sign_key，用于接口签名



```

1.首先需要联系我司相关人员开通企业后台，并且将第三方员工组织架构录入其中；
2.申请企业app_key和app_id;
3.如果开发阶段接入，请使用沙箱环境；
4.API对接方式现在在调整中，暂时只提供接口参数方式，暂时不提供线上环境；

```
