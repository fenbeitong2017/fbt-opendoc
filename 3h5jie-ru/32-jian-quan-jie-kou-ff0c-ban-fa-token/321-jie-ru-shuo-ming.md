#### 1.生成企业app_key和app_id，参数包括

##### 1)app_id/app_key/sign_key 企业标识，请存储;

##### 2)调用3.2.1接口，颁发公司token，存入自己缓存，token有效2小时,token失效返回401;

##### 3)免登地址

```
测试环境:https://webapp-test.fenbeijinfu.com/sso?token=ilsoiejfewdjkfjsfw84ur83kd&tp_user_id=201800989305&tp_mobile=17080151669
生产环境:https://webapp.fenbeitong.com/sso?token=ilsoiejfewdjkfjsfw84ur83kd&tp_user_id=201800989305&tp_mobile=17080151669 嵌入到第三方应用中;
参数说明:token:颁发的公司token,tp_user_id:第三方人员ID,tp_mobile:第三方手机号



```


##### 4)根据公司token和个人的第三方人员ID和手机号换取分贝通的个人token,分贝通会校验token的有效性，然后跳转到分贝通主页






