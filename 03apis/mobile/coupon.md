# 手机移动端优惠券

## 1.微信红包接口

###1.1点击领取优惠券

> **请求url：**http://localhost/shiwu/weixinapi/coupon

> **请求方式：**post

> **参数：** <br/>
pmid：活动的id <br/>
String md5：md5 加密串<br/>
Long datetime ： 时间戳<br/>
String opid：微信的openId <br/>

> **返回结果:**

	{
		data: null,
		code: 300,
		msg: "已达到领取上限"
	}

code=200 为操作成功，300失败，msg是提示信息，data 失败的时候为null，成功的时候是一个券的实体

## 2.手机端接口

###1.1查询可用的优惠券，确认订单页面

> **请求url：**http://localhost/shiwu/mobile/member/coupon/useful

> **请求方式：**post/get

> **参数：** <br/>
shop：商家的id<br/>

> **返回结果:**

	{
	data: [
		 {
		code: "MTFaWEpoZW1GeTAw",
		coupon:  {
			cp_type: "1",
			effect_end_time: 1454212800000,
			effect_start_time: 1453176000000,
			id: 11,
			is_default: 1,
			max_received_num: 1,
			name: "满50减5，测试",
			provider_shop: 1,
			reduce_amount: 5,
			status: "1",
			trigger_amount: 50
		},
		coupon_id: 11,
		id: 91,
		member_id: 18,
		status: "1"
		}
	],
	msg: "请求成功",
	code: 200
	}

code=200 为操作成功，300失败，msg是提示信息，data 失败的时候为null，成功的时候是一个券的实体

data券实体里面，code是券号，trigger_amount使用限制，reduce_amount面额，effect_start_time有效时间开始，effect_end_time 有效结束时间

###1.2 切换收货地址，请求对应的运费

> **请求url：**http://localhost/shiwu/mobile/freight/fee

> **请求方式：**post/get

> **参数：** <br/>
pcode：收货地址的省份编码<br/>

> **返回结果:**

	{
		data: 10,
		msg: "请求成功",
		code: 200
	}

code=200 为操作成功，300失败，msg是提示信息，data 失败的时候为null，成功的时候是具体费用

-------

1.[可领取优惠券列表](#1)
2.[用户领券](#2)

<h2 id ="1">可领取优惠券列表</h2>

>**请求url：** ${ctx}/mobile/member/coupon/pick_list

>**请求方式：** post

>**参数：** 
    
>**返回结果:**

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": [
        {
          "id": 30,
          "name": "国庆大优惠01",              // 优惠券名称
          "cptype": 0,
          "triggerAmount": 6000,               //满 x 元  
          "reduceAmount": 500,                // 减 x 元 
          "effectStartTime": 1475164800000,   //有效开始时间
          "effectEndTime": 1477843200000,     //有效结束时间 
          "status": 1,                  // 优惠券 状态 ，1启用，2禁用
          "currentNum": 25,     //当前券已生成的总数量
          "maxReceivedNum": 1,   // 用户能领取此券 的最大数量
          "pickedCount": 1,     // 此类型的券已经被领取的数量
          "page": null,
          "lteffectEndTime": null,
          "gteffectEndTime": null,
          "currentPickCount": 0    // 当前登录用户领取此券的数量，0表示未领取，其他数 表示已领取数量
        },
        {
          "id": 31,
          "name": "国庆大优惠02",
          "cptype": 0,
          "triggerAmount": 10000,
          "reduceAmount": 1000,
          "effectStartTime": 1475251200000,
          "effectEndTime": 1477929600000,
          "status": 1,
          "currentNum": 20,
          "maxReceivedNum": 1,
          "pickedCount": 1,
          "page": null,
          "lteffectEndTime": null,
          "gteffectEndTime": null,
          "currentPickCount": 0
        }
      ],
      "code": null,
      "msg": null
    }
    
    
    
<h2 id="2">用户领取券</h2>    

>**请求url：** ${ctx}/mobile/member/coupon/pickup

>**请求方式：** post

> **参数：** <br/>
    couponId: 优惠券id
    
>**返回结果:**
    isSuccess 返回 true、false表示 操作 成功或者失败
    {
          "isSuccess": true/false,
          "errorCode": null,
          "message": null,
          "data": [
            {
              pick up success
            }
          ],
          "code": null,
          "msg": null
        }




