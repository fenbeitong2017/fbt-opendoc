2.9.5 根据公司ID拉取公司自定义字段
####接口说明
- 1.**最新接口**
- 2.根据公司ID拉取公司下单时需要的自定义字段内容



 请求方式 | 请求地址 
--- | --- 
 POST | open/api/attr/select
 

 字段 | 名称 | 类型 | 必填 | 描述 
 --- | --- | --- | --- | --- 
 access\_token | 鉴权Token | string | Y | 5747fbc10f0e60e0709d8d722 
 sign | 签名 | string | Y | oihfnlyeofdh98 
 timestamp | 时间戳 | long | Y | 13位时间戳  1241243250000 
 employee\_id | 用户ID | string | Y | 分贝用户id或者第三方用户id 
 employee\_type | 用户类型 | string | Y |  类型，0为分贝用户，1为第三方用户 
 data |  请求数据 | jsonobject | Y |请求数据
 data.company_id |公司ID| string | Y |59b74c132344WASF83269
 data.business |业务场景| Integer | Y |(3,"打车"),(7,"国内机票"),(40,"国际机票"),(11,"酒店"),(15,"火车"),(20,"采购"),(30,"用餐"）
 data.employee_id |员工ID| string | N |59b74c13234439kd89ws8ow
 data.mobile_phone |员工手机号| string | Y |17080151666




请求示例：

```



    "access_token":"5747fbc10f0e60e0709d8d722",
    "timestamp":124124325,
    "sign":"oihfnlyeofdh98",
    "employee_id":"59b74c1323445f2d54dd07922",
    "employee_type":"1",
    "data":{  
    "company_id":"59b74c132344WASF83269",
    "business":40        
     }



```

响应结果：

```



{
    "request_id": "M5NrqkfNe4ifAni4dLlC",
    "code": 0,
    "msg": "success",
    "data": 
    [
        {
        "attr_name":"cost_center",
        "label":"成本中心",
        "options":[{"cost_center_id":"1234",
        "cost_center_name":"项目管控成本中心"},{"cost_center_id":"00876",
        "cost_center_name":"成本核算中心"}],
        "type":"select",input:文本输入,number:数字输入、select:下拉选择
        "placeholder":"请选择",//提示文本:默认为请输入,请选择
        "required":true,//是否为必填项
        "multiple":false, //是否需要多选
        "business":40,
        "remote_address":"www.open.xxx.com/open/attr/select"  
    },{
        "attr_name":"expenses_classify",
        "label":"费用归属",
        "options":[{"expenses_classify_id":"ALIDEOCD""expenses_classify_name":"管理费用"},{"expenses_classify_id":"ALIDEOCD""expenses_classify_name":"经营费用"}],
        "type":"select",
        "placeholder":"请选择",//提示文本，默认就是请输入,请选择
        "required":true,
        "multiple":false,
        "business":40,
        "remote_address":"www.open.xxx.com/open/attr/select"
    },{
        "attr_name":"project_center",
        "label":"项目中心",
        "options":[{"project_center_id":"24455","project_center_name":"国航客户项目中心"},{"project_center_id":"24485","project_center_name":"中铁客户项目中心"}],
        "type":"select",
        "placeholder":"请选择",//提示文本，默认就是请输入,请选择
        "required":true,
        "multiple":false,
        "business":40,
        "remote_address":"www.open.xxx.com/open/attr/select"
    }

]
     
    
}




```



