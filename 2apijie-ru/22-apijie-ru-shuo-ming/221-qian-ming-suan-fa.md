需参与鉴权的参数定义:
#### 1.sign_key说明:
```
分贝通颁发的sign_key需要作为参数参与签名,且不参与传递.加密数据包括时间戳timestamp和data数据
sign_key:企业开通后提供的sign_key
timestamp:13位时间戳
data:请求的data业务参数
```
#### 2.MD5加密说明:
```
采用org.apache.commons下DigestUtils.md5Hex(param)加密，
不同的编程语言MD5加密是相同的，调用相对应的编程语言进行数据加密即可

```
#### 3.签名示例:

```
java:

import org.apache.commons.codec.digest.DigestUtils;
public static String getSign(String timestamp, String jsonData, String signKey) {
        //使用相对应的方法进行字符串拼接,可以调用不同方法生成签名字符串
        1.String signStr = StrUtils.formatString("timestamp={0}&data={1}&sign_key={2}", timestamp, jsonData, signKey);
        2.String signStr = MessageFormat.format(timestamp, jsonData,signKey);
        3.String signStr = "timestamp="+timestamp+"&data="+jsonData+"&sign_key="+signKey
        byte[] bytes;
        try {
            bytes = signStr.getBytes("utf-8");
        } catch (UnsupportedEncodingException e) {
            log.error("生成openapi签名出错", e);
            throw new FinhubException(MessageCode.EXCEPTION);
        }
        String sign = DigestUtils.md5Hex(bytes)
        return sign;  
    }

```


