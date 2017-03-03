# 订单接口

--------

订单相关接口：<br />

1. [购买，进入确认订单页面](#1)
2. [确认订单](#3)
3. [去支付](#4)
4. [订单详情](#5)
5. [取消订单](#6)
6. [提醒发货](#7)
7. [确认收货](#8)
8. [删除订单](#9)
9. [订单列表](#10)
10. [取消订单(待发货)](#11)

-------

<h2 id="1">1.购买，进入确认订单页面</h2>

> **请求url：** ${ctx}/web/member/order/preorder

> **请求方式：**post/get

> **参数：** <br/>
**token** : 身份标识 <br />
**skuIds**: 购买的产品的skuid串，多个时候用逗号隔开 <br />
**numbers**: 购买的产品的数量，与上面的sku对应，多个之间用逗号隔开<br />
**type**: 订单的类型，
	(0,"实物商品"),
	(1,"虚拟商品"),
	(2,"线下交易"),
	(3,"活动赠品");<br />
**source**: 订单的来源，
	(0,"PC端"),
	(1,"web APP"),
	(2,"微信"),
	(3,"Android APP端"),
	(4,"iOS APP端");<br />
**orderWay**
	 0-->立即购买,1-->购物车下单


例如： ${ctx}/web/member/order/preorder?token=abc&skuIds=73,69&numbers=1,2&type=0&source=4&orderWay=1
代表购买 skuid为73的产品1件，skuid为69的产品2件，生成一个订单

> **成功返回结果如下图:** <br />

    请求成功返回在确认订单界面，preOrders是订单信息，numbers是购买数量，skuids是 商品skuid,defaultAddr是默认收货地址，addrs是收货地址列表。
      {
        "numbers": "1",
        "skuids": "62",
        "defaultAddr": {
          "id": 297,
          "country": "CN",
          "province": "104104",
          "city": "104104101",
          "area": "104104101106",
          "countryName": null,
          "provinceName": "广东省",
          "cityName": "广州市",
          "areaName": "天河区",
          "detail": "黄铺大道",
          "postCode": "513001",
          "phone": "13242322015",
          "tel": null,
          "reciver": "lzs1",
          "isdefault": 1,
          "memberId": 291,
          "createtime": 1466491616000,
          "updatetime": 1474359799000,
          "page": null,
          "orderBy": null,
          "descOrAsc": null
        },
        "defaultFee": 500,
        "preOrders": [
          {
            "oid": null,
            "orderName": null,
            "orderNo": null,
            "tradeNo": null,
            "totalFee": 0,
            "discountFee": 0,
            "payment": 0,
            "memberId": 291,
            "invalidTime": 24,
            "source": 1,
            "status": 1010,
            "odType": 0,
            "deliveryTime": 24,
            "realDeliveryTime": null,
            "isDelete": 2,
            "locationId": null,
            "shopId": 1,
            "freightFee": null,
            "leaveWord": null,
            "createTime": null,
            "updateTime": null,
            "acceptTime": null,
            "completeTime": null,
            "signTime": null,
            "page": null,
            "orderBy": null,
            "descOrAsc": null,
            "gtcreatetime": null,
            "ltcreatetime": null,
            "ltrealDeliveryTime": null,
            "orderWay": 1,
            "couponCode": null,
            "orderitemBOs": [
              {
                "itemId": null,
                "itemOrderNo": null,
                "itemProductSkuId": 62,
                "itemPrice": 0,
                "itemDiscountFee": 0,
                "itemNumber": 1,
                "itemStatus": 1010,
                "itemCommentTimes": null,
                "itemRemark": null,
                "itemCreateTime": null,
                "itemUpdateTime": null,
                "itemRefundState": null,
                "itemRefundId": null,
                "itemName": "多士炉家用 自动调档",
                "itemImg": "/product/null/1453693956884.jpg",
                "itemProp": "颜色分类:白色",
                "itemProCode": "P14536923627706448",
                "itemProps": [
                  "颜色分类:白色"
                ],
                "custserTime": null,
                "page": null,
                "orderBy": null,
                "descOrAsc": null,
                "delivery": null,
                "order": null,
                "productSkuBO": null,
                "freightInfoBO": null,
                "number": null,
                "product_id": null
              }
            ],
            "orderaddressBO": null,
            "tradebo": null,
            "userRoleCode": null,
            "userShopId": null,
            "statusStr": null,
            "logistis": null,
            "orderItems": null,
            "shop_id": null,
            "od_type": null
          }
        ],
        "addrs": [
          {
            "id": 297,
            "country": "CN",
            "province": "104104",
            "city": "104104101",
            "area": "104104101106",
            "countryName": null,
            "provinceName": "广东省",
            "cityName": "广州市",
            "areaName": "天河区",
            "detail": "黄铺大道",
            "postCode": "513001",
            "phone": "13242322015",
            "tel": null,
            "reciver": "lzs1",
            "isdefault": 1,
            "memberId": 291,
            "createtime": 1466491616000,
            "updatetime": 1474359799000,
            "page": null,
            "orderBy": null,
            "descOrAsc": null
          },
          {
            "id": 298,
            "country": "CN",
            "province": "105101",
            "city": "105101101",
            "area": "105101101104",
            "countryName": null,
            "provinceName": "四川省",
            "cityName": "成都市",
            "areaName": "锦江区",
            "detail": "xxxxxxfafeaa",
            "postCode": "456321",
            "phone": "15023121231",
            "tel": null,
            "reciver": "lzs02",
            "isdefault": 2,
            "memberId": 291,
            "createtime": 1466654112000,
            "updatetime": 1474359789000,
            "page": null,
            "orderBy": null,
            "descOrAsc": null
          }
        ]
      }



-------

<h2 id="3">2.确认订单</h2>

> **请求url：** ${ctx}/web/member/order/cfm

> **请求方式：**post/get

> **参数：** <br/>

    **locId**: 收货地址id <br />
    多个订单实体，每个订单实体里面有多个orderItem,结构如果 i从0 到n,j从0到n。需要数据在上一步返回的orders里面有存在的

	orders[i].source  // 必填
	orders[i].od_type // 必填
	orders[i].shop_id // 必填
	orders[i].orderWay // 必填
	orders[i].orderItems[j].number // 必填
	orders[i].orderItems[j].product_id // 必填
	orders[i].couponCode // 不必填
	orders[i].leave_word // 不必填   用户留言


例如，两件产品一个单（73买1件，69买2件，两种产品属于一个商家1，则一个单）

	orders[0].source=4
	orders[0].od_type=0
	orders[0].shop_id=1
	orders[0].orderWay=1
	orders[0].couponCode=2
	orders[0].leave_word="hehe"

		orders[0].orderItems[0].number=1
		orders[0].orderItems[0].product_id=73

		orders[0].orderItems[1].number=2
		orders[0].orderItems[1].product_id=69
	

再如：两件产品两个单（73买1件，69买2件，两种产品属于商家1和商家2，则2个单）

	orders[0].source=4
	orders[0].od_type=0
	orders[0].shop_id=1
	orders[0].orderWay=1
	orders[0].couponCode=2
	orders[0].leave_word="hehe"

		orders[0].orderItems[0].number=1
		orders[0].orderItems[0].product_id=73

		

	orders[1].source=4
	orders[1].od_type=0
	orders[1].shop_id=2
	orders[1].orderWay=1
	orders[1].couponCode=
	orders[1].leave_word="hehe"

		orders[1].orderItems[0].number=2
		orders[1].orderItems[0].product_id=69

上面两个例子说明产品属于同一商家就是在一个订单中，每个订单有自己的留言和优惠券信息


> **返回结果:**

	{
	    isSuccess:true,
       "errorCode": null,
       "message": null,
		data: {
			    "7000001002016020170"
			},
		msg: "",
		code:
	}
    isSuccess:true 为操作成功,false失败，<br />
    message是错误提示，<br />
    data 失败的时候为null，成功的时候是一个订单号<br />


-------

<h2 id="4">3.去支付</h2>

> **请求url：** ${ctx}/web/member/order/pay

> **请求方式：**post/get

> **参数：** <br/>

    **odnos**: 订单号<br />

> **返回结果:**

	{
        isSuccess:true,
       "errorCode": null,
       "message": null,
        data: {
                xxx:xxx
                xxx:xxx
                xxx:xxx
                xxx:xxx
            },
        msg: "",
        code:
    }

    isSuccess:true 为操作成功,false失败，<br />
    message是错误提示，<br />
    data 失败的时候为null，成功的时候是一个 系统交易信息对象<br />


-------

<h2 id="5">4.订单详情</h2>

> **请求url：** ${ctx}/web/member/order/detail

> **请求方式：**post/get

> **参数：** <br/>

    **odNo**: 订单号 <br />

> **正确返回结果:** 跳转到订单详情界面

	    "data": {
	        "create_time": 1454322401000,
	        "delivery_time": 72,
	        "discount_fee": 0,
	        "freight_fee": 0,
	        "invalid_time": 24,
	        "is_delete": "0",
	        "leave_word": "",
	        "location": {
	            "acceptor_name": "陈龙腾",
	            "area": "天河区",
	            "city": "广州市",
	            "detail": "",
	            "id": 30,
	            "phone": "13660362850",
	            "province": "广东省",
	            "totalAddr": "广东省广州市天河区"
	        },
	        "location_id": 30,
	        "logistis": {
	            "showapi_res_body": {
	                "data": [
	                    {
	                        "context": "在新疆北屯市公司富蕴县便民寄存点分部进行签收扫描，快件已被 图片 签收",
	                        "time": "2015-06-01 19:34:01"
	                    },
	                    {
	                        "context": "进行派件扫描,派送业务员:富蕴分部;联系电话:0906-8727902",
	                        "time": "2015-06-01 13:37:26"
	                    },
	                    {
	                        "context": "到达目的地网点新疆北屯市公司富蕴县便民寄存点分部，快件将很快进行派送",
	                        "time": "2015-06-01 13:30:40"
	                    },
	                    {
	                        "context": "进行派件扫描,派送业务员:业务员;联系电话: 电话:4008216789",
	                        "time": "2015-05-31 12:14:30"
	                    },
	                    {
	                        "context": "从新疆乌鲁木齐分拨中心站点发出,本次转运目的地 新疆北屯市公司",
	                        "time": "2015-05-31 05:24:15"
	                    },
	                    {
	                        "context": "在新疆乌鲁木齐分拨中心进行中转集包扫描,将发往 新疆北屯市公司",
	                        "time": "2015-05-31 01:26:21"
	                    },
	                    {
	                        "context": "在广东广州花都区公司进行揽件扫描",
	                        "time": "2015-05-26 21:18:05"
	                    }
	                ],
	                "expSpellName": "yunda",
	                "expTextName": "韵达快运",
	                "mailNo": 1901118484678,
	                "status": 4,
	                "tel": "400-821-6789"
	            },
	            "showapi_res_code": 0,
	            "showapi_res_error": ""
	        },
	        "member": {
	            "designer": {},
	            "memberAccount": {},
	            "tmId": 7,
	            "tmMemberLoginname": "13660362850",
	            "tmMemberNickname": "clt"
	        },
	        "member_id": 7,
	        "od_type": "0",
	        "od_typeName": "实物商品",
	        "oid": 15,
	        "orderItems": [
	            {
	                "create_time": 1454322401000,
	                "discount_fee": 0,
	                "freightInfo": {
	                    "create_time": 1454322666000,
	                    "expressCompany": {
	                        "code": "yunda",
	                        "id": 9,
	                        "is_delete": "0",
	                        "name": "韵达快递"
	                    },
	                    "express_id": 9,
	                    "id": 8,
	                    "number": -1,
	                    "order_item_id": 17,
	                    "track_no": "1901118484678",
	                    "update_time": 1454322666000
	                },
	                "id": 17,
	                "number": 1,
	                "order_no": "7000001002016020170",
	                "price": 0.01,
	                "productSKU": {
	                    "product": {
	                        "pdMainImg": "/product/P14534810766166561/1453481121527.jpg",
	                        "pdShId": 1,
	                        "pdShortname": "测试商品，拍卖不发货",
	                        "sortCondition": "comprehensive"
	                    },
	                    "productProps": [
	                        {
	                            "ppCategoryId": 20,
	                            "ppCreateTime": 1453481071000,
	                            "ppFormStyle": "radio",
	                            "ppId": 56,
	                            "ppIsDelete": 0,
	                            "ppIsKey": 1,
	                            "ppName": "颜色分类",
	                            "ppShId": 0,
	                            "ppUseAsFilter": 0,
	                            "propValues": [
	                                {
	                                    "ppvCreateTime": 1453481071000,
	                                    "ppvId": 42,
	                                    "ppvIsDelete": 0,
	                                    "ppvPpId": 56,
	                                    "ppvShId": 0,
	                                    "ppvValue": "黑色"
	                                }
	                            ]
	                        }
	                    ],
	                    "propsNameAndValues": "颜色分类:黑色 ， ",
	                    "psCreateTime": 1453481154000,
	                    "psCustomCode": "",
	                    "psEnableNum": -2,
	                    "psId": 59,
	                    "psIsUsed": 1,
	                    "psLockNum": -1,
	                    "psNumber": 0,
	                    "psOriginalPrice": 169,
	                    "psPrice": 0.01,
	                    "psProductId": 3,
	                    "psPropVids": "42",
	                    "psSalesVolumes": 3,
	                    "psUpdateTime": 1454567343000,
	                    "psVirtualNumber": 0
	                },
	                "product_id": 59,
	                "status": "3",
	                "update_time": 1454322666000
	            }
	        ],
	        "order_name": "时物 SG-Toaster-0001B 多士炉烤面包机多功能家用全自动吐司机(测试商品，拍卖不发货)...",
	        "order_no": "7000001002016020170",
	        "payment": 0,
	        "real_delivery_time": 1454322666000,
	        "shop_id": 1,
	        "source": "1",
	        "sourceName": "web APP",
	        "status": "4",
	        "statusName": "已完成",
	        "total_fee": 0.01,
	        "trade_no": "700000145432240144260",
	        "update_time": 1454384121000
	    }



code=200 为操作成功，300失败，<br />
msg是提示信息，<br />
data 失败的时候为null，成功的时候是订单的详细信息<br />


-------

<h2 id="6">5.取消订单(未发货)</h2>

> **请求url：** ${ctx}/web/member/order/cancel

> **请求方式：**post/get

> **参数：** <br/>

    **order_no**: 要取消的订单号 <br />

> **返回结果:**

	{
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {

      },
     "code": null,
     "msg": null
   }

    isSuccess=true 为操作成功，false为失败，<br />


-------

<h2 id="7">6.提醒发货</h2>

> **请求url：** ${ctx}/web/member/order/remind

> **请求方式：**post/get

> **参数：** <br/>

    **order_no**: 要提醒的订单号 <br />

> **返回结果:**

	{
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {

      },
     "code": null,
     "msg": null
   }

    isSuccess=true 为操作成功，false为失败，<br />

-------

<h2 id="8">7.确认收货</h2>

> **请求url：** ${ctx}/web/member/order/accept

> **请求方式：**post/get

> **参数：** <br/>

**order_no**: 操作的订单的订单号 <br />

> **返回结果:**

	{
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {

      },
     "code": null,
     "msg": null
   }

    isSuccess=true 为操作成功，false为失败，<br />


-------

<h2 id="9">8.删除订单</h2>

> **请求url：** ${ctx}/web/member/order/del

> **请求方式：**post/get

> **参数：** <br/>

**orderNo**: 订单号 <br />

> **返回结果:**

	{
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {

      },
     "code": null,
     "msg": null
   }

    isSuccess=true 为操作成功，false为失败，<br />



-------
<h2 id="10">9.订单列表</h2>

## 9.1 跳转到订单列表界面

>** url: ${ctx}/web/member/order/index

>** 方式 ： get

>** 跳转到 ： /modules/web/member/order/order_list.jsp 界面

## 9.2 post获取订单列表信息

> **url：** ${ctx}/web/member/order/list

> **请求方式：** post

> **参数：** <br/>

    **st**: 订单状态，不传值默认查询所有状态的订单 ,如果只查询某几个状态，可以传递状态值，使用逗号<br />
    **currentPage**: 分页查询的页码从1开始<br />

> **返回结果:**

    virtual_dir 是图片服务器的虚拟访问地址
    isSuccess为true操作成功，false操作失败，<br />
    data中orders 失败的时候为null，成功的时候是0个或一个或多个订单<br />

	{
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {
        "virtual_dir": "http://192.168.1.168:81/uploadfile/shiwu",
        "orders": [
          {
            "oid": 1008,
            "orderName": "测试专用商品...",
            "orderNo": "2910001001608180514",
            "tradeNo": "291000147151115948845",
            "totalFee": 1,
            "discountFee": 0,
            "payment": 1,
            "memberId": 291,
            "invalidTime": 24,
            "source": 1,
            "status": 1110,
            "odType": 0,
            "deliveryTime": 24,
            "realDeliveryTime": null,
            "isDelete": 3,
            "locationId": 1038,
            "shopId": 1,
            "freightFee": 0,
            "leaveWord": "",
            "createTime": 1471511159000,
            "updateTime": 1471511306000,
            "acceptTime": null,
            "completeTime": 1471511306000,
            "signTime": null,
            "page": null,
            "orderBy": null,
            "descOrAsc": null,
            "gtcreatetime": null,
            "ltcreatetime": null,
            "ltrealDeliveryTime": null,
            "orderWay": null,
            "couponCode": null,
            "orderitemBOs": [
              {
                "itemId": 1112,
                "itemOrderNo": "2910001001608180514",
                "itemProductSkuId": 104,
                "itemPrice": 1,
                "itemDiscountFee": 0,
                "itemNumber": 1,
                "itemStatus": 1010,
                "itemCommentTimes": 0,
                "itemRemark": null,
                "itemCreateTime": 1471511159000,
                "itemUpdateTime": 1471511304000,
                "itemRefundState": 1501,
                "itemRefundId": 311,
                "itemName": "测试专用商品",
                "itemImg": "/product/P14647617437259202/1465717871072.jpg",
                "itemProp": "",
                "itemProCode": "P14647617437259202",
                "itemProps": [],
                "custserTime": 7,
                "page": null,
                "orderBy": null,
                "descOrAsc": null,
                "delivery": null,
                "order": null,
                "productSkuBO": {
                  "psId": 104,
                  "psCreateTime": 1465891715000,
                  "psUpdateTime": 1474270021000,
                  "psCode": null,
                  "psCustomCode": "12211",
                  "psProductId": 42,
                  "psOriginalPrice": 1000,
                  "psPrice": 500,
                  "psNumber": 10963,
                  "psEnableNum": 10961,
                  "psLockNum": 2,
                  "psIsUsed": 1,
                  "psPropVids": "",
                  "psVirtualNumber": 1,
                  "psSalesVolumes": null,
                  "psCustSerTime": 7,
                  "product": {
                    "pdId": 42,
                    "pdCreateTime": 1464761903000,
                    "pdUpdateTime": 1474270021000,
                    "pdShId": 1,
                    "pdCode": "P14647617437259202",
                    "pdCustomCode": null,
                    "pdShortname": "测试专用商品",
                    "pdLongname": null,
                    "pdMainImg": "/product/P14647617437259202/1465717860093.jpg",
                    "pdGalleryImg": "/product/P14647617437259202/1465717871072.jpg",
                    "pdOnline": 1,
                    "pdOnlineTime": 1473238435000,
                    "pdOfflineTime": 1473238355000,
                    "pdCategoryId": 55,
                    "pdDescription": "测试",
                    "pdDetail": "12320160907",
                    "pdPropVids": "90,66,92,93,89,74,75,76,101",
                    "pdFtId": 54,
                    "pdFtName": "测试用2",
                    "pdOrlPriceInt": 1000,
                    "pdPriceInt": 500,
                    "pdOriginalPrice": 10,
                    "pdPrice": 5,
                    "pdWeight": null,
                    "pdVolume": null,
                    "pdLabelVids": null,
                    "pdIsDelete": 0,
                    "pdNumber": 10963,
                    "pdEnableNum": 10961,
                    "pdLockNum": 2,
                    "pdSalesVolumes": 148,
                    "pdVirtualNumber": 1,
                    "pdIsNew": false,
                    "pdIsHot": true,
                    "pdCommentNum": 178,
                    "pdCustSerTime": 7,
                    "productSkus": null,
                    "props": null,
                    "skuProps": null,
                    "prop": null,
                    "productCategory": null,
                    "freightPrice": null,
                    "sortCondition": "comprehensive",
                    "categoryNode": null,
                    "skuId": null,
                    "pdCodes": null,
                    "page": null,
                    "descOrAsc": null,
                    "orderBy": null
                  },
                  "productProps": null,
                  "propsNameAndValues": "",
                  "page": null,
                  "psOrglPriceDouble": 10,
                  "psPriceDouble": 5
                },
                "freightInfoBO": null,
                "number": null,
                "product_id": null
              }
            ],
            "orderaddressBO": {
              "id": 1038,
              "acceptorName": "lzs1",
              "phone": "13242322015",
              "province": "广东省",
              "city": "广州市",
              "area": "天河区",
              "detail": "黄铺大道",
              "postCode": "513001",
              "provinceCode": "104104",
              "cityCode": "104104101",
              "areaCode": "104104101106",
              "totalAddr": "广东省广州市天河区黄铺大道"
            },
            "tradebo": null,
            "userRoleCode": null,
            "userShopId": null,
            "statusStr": null,
            "logistis": null,
            "orderItems": null,
            "shop_id": null,
            "od_type": null
          }
        ]
      },
      "code": null,
      "msg": null
    }


-------
<h2 id="11">10.取消订单(待发货)</h2>

> **请求url：**http://localhost:8081/sigoods/mobile/member/custservice/refund/cancleOrder

> **请求方式：**post/get

> **参数：** <br/>
**orderNo**: 订单号<br />

> **返回结果:**

	{
		"data":"2960001001607132953",
		"code":"910",
		"msg":"支付宝退款成功"
	}

	{
		"data":"2960001001607132953",
		"code":"911",
		"msg":"支付宝退款失败"
	}

	{
		"data":"2960001001607132953",
		"code":"912",
		"msg":"微信受理"
	}

	{
		"data":"2960001001607132953",
		"code":"913",
		"msg":"微信退款失败"
	}


