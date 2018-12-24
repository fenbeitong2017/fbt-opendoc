> 1.生成企业app_key和app_id，请联系相关人员进行操作，参数包括:
1）app_id/app_key/sign_key 企业标识，请存储;
2）调用3.2.1接口，颁发公司token，存入自己缓存，token有效2小时;
3）appUrl
测试环境:http://webapp-test.fenbeijinfu.com/sso?token=ilsoiejfewdjkfjsfw84ur83kd&tp_user_id=201800989305&tp_mobile=17080151669
生产环境:https://webapp.fenbeitong.com
/sso?token=ilsoiejfewdjkfjsfw84ur83kd&tp_user_id=201800989305&tp_mobile=17080151669 嵌入到第三方应用中;
4)根据公司token和个人的第三方人员ID和手机号换取分贝通的个人token,分贝通会校验token的有效性，然后跳转到分贝通主页
> 2.查询企业URL等信息，可以根据app_id和app_key进行查询;



