2.14.1采购正向订单列表

####接口说明
- 1.**最新接口**
- 2.查询采购正向订单列表
  通过该接口可以查询企业使用分贝通产生的采购正向订单信息
- 3.该接口一次最多可查询1000条数据，如订单数超过1000，则需要分页查询


请求方式|请求地址
----|---
POST|/open/api/mall/order/forward/list

字段|名称|类型|必填|描述
-----|-----|----|----|----
timestamp|时间戳 |long |Y|13位时间戳
sign|签名 |string |Y|gaghegsgd535te3534
access_token|token | string |Y|登录 token
employee_id| 操作人id|string |Y|操作人id,调用接口人 id
employee_type| 用户类型|string|Y|类型，0为分贝用户，1为第三方用户
data |请求数据| jsonobject |Y|
data.companyId|公司ID |string |Y|99o8878pw902436748
data.pageIndex |页码| integer | Y |1(默认值)
data.pageSize|每页显示条数| integer| Y |10(默认值)
data.createBegin|开始时间|string | N |2018-04-05
data.createEnd |结束时间| string | N |2019-05-29
data.finishBegin|开始时间|string | N |2018-04-15
data.finishEnd |结束时间| string | N |2019-05-19



请求示例：

```



"access_token":"5747fbc10f0e60e0709d8d722",
"sign":"oihfnlyeofdh98",
"timestamp":124124325,
"employee_id":"59b74c1323445f2d54dd07922",
"employee_type":"1",
"data":{"companyId":"5747fbc10f0e60e0709d8d7d","pageSize":1000,"pageIndex":1,"createBegin":"2019-04-14","createEnd":"2019-05-14"}


```


响应数据：

字段|名称|类型|必填|描述
-----|-----|----|----|----
orderId| 订单ID|string |Y|订单ID
serviceOrderId| 服务单id|string |Y|服务单id
product |商品信息| jsonarray | Y |商品信息
consigneeInfo |收货人信息| jsonobject | Y | 收货人信息
orderTrack |物流跟踪信息| jsonobject | Y | 物流跟踪信息
bookingPerson|预定人信息| jsonobject| Y |预订人信息
priceInfo |价格信息| jsonobject | Y |价格信息
company|公司信息| jsonobject| Y |分贝通
department|部门信息 |jsonobject | Y |测试部
customRemark|备注信息|jsonarray|Y|备注信息
createTime|下单时间 |string |Y|2019-04-29 14:34:31
department|部门信息 |jsonobject | Y |测试部
freight|运费|double|Y|运费
orderStatus|订单状态| jsonobject| Y |订单状态信息
orderStatus.key|状态码| integer | Y |4701
orderStatus.value|订单状态名称| string| Y |已取消
applicationTime|服务单申请时间|string|Y|服务单申请时间
checkTime|审核时间|string|Y|审核时间
checkResult|审核状态| jsonobject| Y |审核状态
step|售后单状态| jsonobject| Y |售后单状态








```
{
    "request_id": "M9zzOQmrpAsi90QPNQgT",
    "code": 0,
    "type": 0,
    "msg": "success",
    "data": {
        "totalCount": 2,
        "results": [
            {
                "finishTime": "2019-05-13 16:40:13",
                "product": {
                    "id": 201904031630500,
                    "name": "村长测试商品006",
                    "amount": 1,
                    "actualPrice": 1,
                    "totalActual": 1,
                    "saleUnit": "原厂包装",
                    "spec": "<link rel=\"stylesheet\" type=\"text/css\" href=\"https://static.fenbeitong.com/css/mall.css\"></link><table class=\"mall-wrapping\"><tbody><tr><td><div class=\"item-title\">包装清单</div><div class=\"item-detail\">dsafga</div></td></tr><tr><td><div class=\"item-title\">正品行货</div><div class=\"item-detail\">分贝通向您保证所售商品均为正品行货，所有商品开具机打发票。所有商品及配送均由分贝通合作伙伴京东商城提供。</div></td></tr><tr><td><div class=\"item-title\">权利声明</div><div class=\"item-detail\">分贝通所有商品信息、规格介绍、包装清单是分贝通及其合作伙伴京东商城重要的经营资源，未经许可，禁止非法转载使用。</div><div class=\"item-detail\">注：本站商品信息均来自于合作方，其真实性、准确性和合法性由信息拥有者（合作方）负责。本站不提供任何保证，并不承担任何法律责任。</div></td></tr><tr><td><div class=\"item-title\">价格说明</div><div class=\"item-detail\">分贝通价：分贝通价为商品的销售价，是您最终决定是否购买商品的依据。</div><div class=\"item-detail\">折扣：如无特殊说明，折扣指销售商在原价、京东价等某一价格基础上计算出的优惠比例或优惠金额；如有疑问，您可在购买前联系贵司的分贝通客户经理。</div><div class=\"item-detail\">异常问题：商品促销信息以商品详情页“促销”栏中的信息为准；商品的具体售价以订单结算页价格为准；如您发现活动商品售价或促销信息有异常，建议购买前先联系贵司的分贝通客户经理咨询。</div></td></tr><tr><td><div class=\"item-title\">售后服务说明</div><div class=\"item-detail\">商品售后服务规定以分贝通公示为准，点击查询<a href=\"https://static.fenbeitong.com/self-support-returned-rules.html\">分贝通商品售后服务规定</a ></div></td></tr></tbody></table>",
                    "category": {
                        "category_code1": 9987,
                        "category_code2": 653,
                        "category_code3": 655,
                        "category_describe1": "手机",
                        "category_describe2": "手机通讯",
                        "category_describe3": "手机"
                    },
                    "couponAmount": 0,
                    "brandName": "LG"
                },
                "costAttribution": "北京分贝金服科技有限公司",
                "consignee": {
                    "name": "121",
                    "address": "上海上海市黄浦区城区1234",
                    "phone": "13671273136",
                    "province_name": "上海",
                    "city_name": "上海市"
                },
                "orderTrack": [
                    {
                        "time": "2019-05-13 16:40:13",
                        "status": "您的服务单已退款，请您注意查收",
                        "operator": "梓涵"
                    }
                ],
                "orderId": "5cd92d58e4b03a7be84ea24f",
                "bookingPerson": {
                    "id": "5b60291f23445f381412b1c2",
                    "name": "强蜀黍",
                    "phone": "12345678932"
                },
                "checkResult": {
                    "key": 0,
                    "value": "待审核"
                },
                "priceInfo": {
                    "refundCost": 10,
                    "refundPrice": 10
                },
                "checkTime": "2019-05-13 16:40:13",
                "applicationTime": "2019-05-13 16:40:13",
                "createTime": "2019-05-13 16:39:52",
                "step": {
                    "key": 50,
                    "value": "完成"
                },
                "company": {
                    "id": "5747fbc10f0e60e0709d8d7d",
                    "name": "北京分贝金服科技有限公司"
                },
                "department": {
                    "id": "59a80dd92798630fd780babf",
                    "name": "嘟嘟搞测试"
                },
                "serviceOrderId": "5cd92d6de4b03a7be84ea252",
                "status": {
                    "key": 1,
                    "value": "已退款"
                }
            },
            {
                "finishTime": "2019-05-07 11:57:14",
                "product": {
                    "id": 2018031523584121,
                    "name": "得力（Deli）0231-12号起钉器 颜色随机（KKJ）",
                    "amount": 1,
                    "actualPrice": 2.5,
                    "totalActual": 2.5,
                    "saleUnit": "原厂包装",
                    "spec": "<link rel=\"stylesheet\" type=\"text/css\" href=\"https://static.fenbeitong.com/css/mall.css\"></link><table class=\"mall-wrapping\"><tbody><tr><td><div class=\"item-title\">包装清单</div><div class=\"item-detail\">0231-12号起钉器 颜色随机</div></td></tr><tr><td><div class=\"item-title\">正品行货</div><div class=\"item-detail\">分贝通向您保证所售商品均为正品行货，所有商品开具机打发票。所有商品及配送均由分贝通合作伙伴京东商城提供。</div></td></tr><tr><td><div class=\"item-title\">权利声明</div><div class=\"item-detail\">分贝通所有商品信息、规格介绍、包装清单是分贝通及其合作伙伴京东商城重要的经营资源，未经许可，禁止非法转载使用。</div><div class=\"item-detail\">注：本站商品信息均来自于合作方，其真实性、准确性和合法性由信息拥有者（合作方）负责。本站不提供任何保证，并不承担任何法律责任。</div></td></tr><tr><td><div class=\"item-title\">价格说明</div><div class=\"item-detail\">分贝通价：分贝通价为商品的销售价，是您最终决定是否购买商品的依据。</div><div class=\"item-detail\">折扣：如无特殊说明，折扣指销售商在原价、京东价等某一价格基础上计算出的优惠比例或优惠金额；如有疑问，您可在购买前联系贵司的分贝通客户经理。</div><div class=\"item-detail\">异常问题：商品促销信息以商品详情页“促销”栏中的信息为准；商品的具体售价以订单结算页价格为准；如您发现活动商品售价或促销信息有异常，建议购买前先联系贵司的分贝通客户经理咨询。</div></td></tr><tr><td><div class=\"item-title\">售后服务说明</div><div class=\"item-detail\">商品售后服务规定以分贝通公示为准，点击查询<a href=\"https://static.fenbeitong.com/self-support-returned-rules.html\">分贝通商品售后服务规定</a ></div></td></tr></tbody></table>",
                    "category": {
                        "category_code1": 670,
                        "category_code2": 729,
                        "category_code3": 4837,
                        "category_describe1": "电脑办公",
                        "category_describe2": "文具/耗材",
                        "category_describe3": "办公文具"
                    },
                    "couponAmount": 0,
                    "brandName": "得力"
                },
                "costAttribution": "吃蛋蛋",
                "consignee": {
                    "name": "李雷",
                    "address": "北京北京市朝阳区三环以内润诚中心211",
                    "phone": "17778092750",
                    "province_name": "北京",
                    "city_name": "北京市"
                },
                "orderTrack": [
                    {
                        "time": "2019-05-07 11:57:14",
                        "status": "您的售后单已经申请成功，售后审核中",
                        "operator": "客服"
                    },
                    {
                        "time": "2019-05-07 11:59:32",
                        "status": "您的售后单审核通过，退货信息：姓名:赵光明 电话:13520682423 地址:十八里店乡1998号，合众奥顺达物流院里A3库房。请填写商品退回快递信息",
                        "operator": "客服"
                    },
                    {
                        "time": "2019-05-07 11:59:50",
                        "status": "您的售后单退回货物已收到",
                        "operator": "客服"
                    },
                    {
                        "time": "2019-05-07 12:00:20",
                        "status": "您的售后单财务已退款，请注意查收",
                        "operator": "客服"
                    }
                ],
                "orderId": "5ccfac5a2798632ab1869abf",
                "bookingPerson": {
                    "id": "5a2752f123445f3483c70354",
                    "name": "王蛋开",
                    "phone": "15601247725"
                },
                "checkResult": {
                    "key": 0,
                    "value": "待审核"
                },
                "priceInfo": {
                    "refundPrice": 2.5
                },
                "checkTime": "2019-05-07 11:57:14",
                "applicationTime": "2019-05-07 11:57:14",
                "createTime": "2019-05-06 11:39:04",
                "step": {
                    "key": 50,
                    "value": "完成"
                },
                "company": {
                    "id": "5747fbc10f0e60e0709d8d7d",
                    "name": "北京分贝金服科技有限公司"
                },
                "department": {
                    "id": "5bf54d8323445f128a722ef1",
                    "name": "权限测试(勿删)-子部门2"
                },
                "serviceOrderId": "5cd1021a2798632ab186b22b",
                "status": {
                    "key": 1,
                    "value": "已退款"
                }
            }
        ]
    }
}


```


