# 个人中心接口

-------

##1. 点击进入用户中心

进入用户中心的时候需要的初始的数据

> **请求url：**http://localhost/shiwu/web/member/index

> **请求方式：**post/get

> **参数：** <br/>
token：请求和身份的标志 <br />

> **返回结果:**

![result](/imgs/20160218114912.png) <br />

code=200 为操作成功，300失败，<br />
msg是提示信息，<br />
data 失败的时候为null，成功的时候需求的实体信息<br />
data的数据说明<br />

| 实体          | 说明          |
| ------------- |:-------------:| 
|    memeber		|  	会员信息	|
|    couponNum		|   账户里面优惠券的数量	|
|    orderStatusNums 		|   订单状态和对应状态的订单数量	|

[订单状态点击查看状态参考表](../reference.html)

