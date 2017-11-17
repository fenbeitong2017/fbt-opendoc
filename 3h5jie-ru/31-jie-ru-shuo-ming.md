
```
1.生成企业AppKey和AppId，请联系相关人员进行操作，参数包括：

	1）appId/appKey/signKey 企业标识，请存储；
	
	2）服务端调用鉴权颁发Token，存入自己缓存，Token有效2小时；
	
	3）appUrl 例：https://open-sandbox.fenbeitong.com/auth/join?token=服务器颁发Token 嵌入到第三方应用中；
	
	4) 该Token为用户Token，每个用户不同；
	
2.查询企业URL等信息，可以根据appId和appKey进行查询

3.该接口访问频次每小时5次；
```
