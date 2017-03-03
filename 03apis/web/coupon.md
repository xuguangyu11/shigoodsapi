# 优惠券接口

-------

优惠券的相关接口：<br />

1. [可领取券列表](#1)
2. [领券](#2)
3. [用户各状态的券的查看](#3)
4. [删除过期的券](#4)
5. [下单时可用的券](#5)

-------

<h2 id="1">1.可领取券列表</h2>


-------

<h2 id="2">2.领券</h2>


-------

<h2 id="3">3.用户各状态的券的查看</h2>

> **请求url：**http://localhost/shiwu/web/member/coupon/list

> **请求方式：**post/get

> **参数：** <br/>
**token**: 用户请求身份标识 <br />
**status**：查询的券的状态，1--> 可用券, 2--> 正常使用的券 , 3--> 已过期的券 ,此值不传则默认只查询可用券<br />

> **返回结果:** <br />
![result](/imgs/20160218160009.png) <br />

**code** 200为操作成功，300失败，<br />
**msg** 提示信息，<br />
**data** code==200 的时候有值，里面的对象数量为空则没有可用券，不为空则有。

券实体里面说明：<br />

| 字段          | 说明          |
| ------------- |:-------------:| 
|    code		|  	券号	|
|    trigger_amount		|   使用限制	|
|    reduce_amount 		|   券的面额	|
|    effect_start_time 		|   有效时间开始	|
|    effect_end_time 		|   有效结束时间	|


-------

<h2 id="4">4.删除过期的券</h2>

> **请求url：**http://localhost/shiwu/web/member/coupon/del

> **请求方式：**post/get

> **参数：** <br/>
**token**: 用户请求身份标识 <br />
**ids**：要删除的券的id串，多个之间用逗号隔开 <br />

> **返回结果:**

	{
		msg: "请求成功",
		code: 200
	}

code=200 为操作成功，300失败，<br />
msg是提示信息，<br />


--------
<h2 id="5">5.下单时可用的券</h2>

> **请求url：**http://localhost/shiwu/web/member/coupon/useful

> **请求方式：**post/get

> **参数：** <br/>
**token**: 用户请求身份标识 <br />
**shop**：购买产品下单时候的店铺的id <br />

> **返回结果:** <br />
![result](/imgs/20160218150716.png) <br />

**code** 200为操作成功，300失败，<br />
**msg** 提示信息，<br />
**data** code==200 的时候有值，里面的对象数量为空则没有可用券，不为空则有。

券实体里面说明：<br />

| 字段          | 说明          |
| ------------- |:-------------:| 
|    code		|  	券号	|
|    trigger_amount		|   使用限制	|
|    reduce_amount 		|   券的面额	|
|    effect_start_time 		|   有效时间开始	|
|    effect_end_time 		|   有效结束时间	|
 