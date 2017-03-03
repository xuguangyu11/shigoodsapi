# Mobile端订单相关接口

----
## 1.下订单接口

**1.1 从购物车界面点击结算后都确认订单页面**

> **请求url：**http://${ctx}/sigoods/mobile/member/order/preorder_p?skuIds=19,20&numbers=2,1&type=0

> **请求方式：**get

>**参数：** <br/>
**skuIds**：购买的产品的sku的id ,多个用逗号隔开<br/>
**numbers**：购买的产品的数量，对应skuid<br/>
**type**：订单的类型 ：0-->实物商品，1-->虚拟商品 ，2-->线下交易<br/>
**orderWay**：0-->立即购买,1-->购物车下单

>**返回结果:**  直接返回订单页面
      
      绑定数据参数：
      可用积分：${scoreAval} ,
      积分可抵现金：${offsetAmount} ,
      账户余额：${balance}
  

**1.2 从商品详情界面点击立即购买跳转订单页面**

> **请求url：**http://${ctx}/sigoods/mobile/member/order/directbuy

> **请求方式：**get

>**参数：** <br/>
**skuId**：购买的产品的sku的id<br/>
**number**：购买的产品的数量<br/>
**type**：订单的类型 ：0-->实物商品，1-->虚拟商品 ，2-->线下交易<br/>
**orderWay**：0-->立即购买,1-->购物车下单

>**返回结果:**  直接返回订单页面
      
      绑定数据参数：
      可用积分：${scoreAval}，
      积分可抵现金：${offsetAmount}，
      账户余额：${balance}

----
## 2.确认订单接口

> **请求url：**http://${ctx}/sigoods/mobile/member/order/cfm

> **请求方式：**post

>**请求参数：** <br/>
**orderForm（必传）**：购买订单实体<br/>
**locId（必传）**：用户收货地址ID<br/>
**paypwd（非必传）**：用户支付密码，当使用余额支付，需要提供<br/>
**isScore（非必传）**：(布尔类型)是否使用积分抵现 ，true 是，false 否<br/>
**isBalance（非必传）**：(布尔类型)是否使用余额支付 ，true 是，false 否<br/>

>**参数说明：** <br/>
>请求表单参数orderForm形式如下：
    
     {
    "orders": [
        {
            "couponCode": "",
            "leaveWord": "",
            "odType": 0,
            "orderWay": 1,
            "orderitemBOs": [
                {
                    "delivery": 4,
                    "itemImg": "/product/P14536929508719501/1453692988072.jpg",
                    "itemName": "M-0002不锈钢家用电动绞肉机",
                    "itemNumber": 1,
                    "itemProCode": "P14536929508719501",
                    "itemProductSkuId": 64,
                    "itemProp": "",
                    "itemProps": []
                }
            ],
            "shopId": 1,
            "source": 1
        }
    ]
    }

>**返回结果:**
   
    {
    data: {
        order_nos:"7000001002016020170,70000010020160201222"
        },
    msg: "订单请求成功",
    code: 200 /* 200:订单请求成功 ,1000:余额支付不足,1002:余额为零,1003:余额支付成功，221：支付密码错误 */
    }

>**结果说明:**<br/>
>1.如果使用第三方支付，结果返回码200表示操作成功，可调用**去支付**接口；<br/>
>2.如使用余额支付，结果返回码1003表示支付成功，无需调第三方去支付接口，但要跳转**订单待发货列表**<br/>

 -----
## 3.去支付

> **请求url：**http://${ctx}/sigoods/mobile/member/order/pay

> **请求方式：**post/get

> **参数：** <br/>
**odnos**: 订单号串，逗号隔开 <br />

> **返回结果:**

	{
		data:{"trade":xxxxxxxxx}
		msg: "请求成功",
		code: 200
	}

>code=200 为操作成功，300失败，<br />
msg是提示信息，<br />
data 失败的时候为null，成功的时候创建的时物系统的交易号<br />


