# Mobile端用户模块接口说明
------
1. [登录接口](#1)
2. [注册接口](#2)
3. [忘记密码，重置密码接口](#3)
4. [获取校验码接口](#4)
5. [异步检测username接口](#5)
6. [购物车接口](#6)
7. [用户收货地址接口](#7)
8. [个人中心](#8)
9. [省市区三级列表](#9)
10. [账户充值](#10)
11. [账户关联](#11)
12. [获取IM账号密码](#12)
13. [用户话费充值接口](#13)
14. [Mobile端积分兑换余额接口](#14)



------

<h2 id="1">1. 登录login  接口</h2>

**1.1** ${ctx}/mobile/login

>**请求方法：**post

>**参数：** username:登录名，pwd:密码  {"username":"参数值","pwd":"参数值"}

>**返回结果：**

    {"code":"结果代码200,300等","msg":"结果说明" ,"memInfo":"{包括用户基本信息，如昵称等}"}

    {
      "memInfo": {
        "phone": "13242322015",
        "realName": null,
        "sex": 1,
        "nickName": "Wickywe"
      },
      "code": "200",
      "msg": "登录成功"
    }


**1.2** ${ctx}/mobile/login

>**请求方式:** get

>**返回：**  跳转到mobile端的登录界面

------

<H2 id="2">2. 注册接口</H2>

**2.1** ${ctx}/mobile/register

>**请求方式：**post

>**参数：**username表示手机号或者邮箱，pwd密码（6-32位长度），phoneCode手机或者邮箱校验码
>  {"username":"参数值","pwd":"参数值","phoneCode":"参数值"}

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**2.2** ${ctx}/mobile/register

>**请求方式：** get

>** 返回:**  mobile端注册界面

------

<h3 id="3">3、忘记密码，重置密码接口</h3>

**3.1** 忘记密码界面

>**Url:** ${ctx}/mobile/newpwd

>**请求方式：** get

**3.2** 保存重置的新密码

>**Url:** ${ctx}/mobile/member/newpwd

>**请求方式：** post

>**参数：**  username：账户名（手机号或邮箱），newpwd：新密码，phonecode：手机/邮箱收到的校验码

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

------

<h2 id="4">4、获取校验码接口</h2>

** 4.1** 手机获取校验码短信接口

>**URL:** ${ctx}/mobile/phonecode

>**请求方法：**post

>**请求参数：**<br/>
**phone**：表示手机号，<br/>
**validcode**：图形验证码，<br/>
**type**：1表示注册或更换绑定手机号时调用接口，2表示忘记密码,设置支付密码调用接口<br/>

>**返回结果：** 

	{"code":"200","msg":"校验码已发送"}


** 4.2** 邮箱获取校验码短信接口

>**URL:** ${ctx}/mobile/emailcode

>**请求方法：** post

>**请求参数：** <br/>
 **email**：邮箱号，<br/>
 **type**：1表示注册或更换绑定邮箱号时调用接口，2表示忘记密码,设置支付密码时调用接口 <br/>

>**返回结果：**  

	{"code":"200","msg":"校验码已发送"}


**4.3** 验证码是否正确接口

>**URL:** ${ctx}/mobile/checkcode

>**请求方法：**post

>**请求参数：** <br/>
**phonecode**：校验码，<br/>
**username**：手机号或邮箱地址 ，<br/>
**validcode**：图形验证码<br/>

>**返回结果：**  

	{"code":"200","msg":"校验码正确"}
	
**4.4** 获取验证图形接口

>**URL:** ${ctx}/mobile/code/validcode

>**接口说明:** <br/>
获取随机图片前台展示，后台将图形验证码值缓存到session会话中，为后续获取短信验证码等校验接口服务<br/>

>**请求方法：**get

>**返回结果：**  

	返回验证图片*.jpeg格式

 --------

<h2 id="5">5 检测username是否已经被使用</h2>

>**Url:** ${ctx}/mobile/checkusername

>**请求方式：** post

>**参数：**  username：账户名（手机号或邮箱）

>**返回结果:**  (true、false)存在为true，不存在为false

-----

<h2 id="6"> 6 购物车接口</h2>

**6.1** 购物车列表

>**Url:** ${ctx}/mobile/member/shopcart

>**请求方式：** get

>**返回结果:**  返回到shopcartlist界面， 购物车列表结果集

**6.2** 修改购物车数量

>**Url:** ${ctx}/mobile/member/shopcart/num

>**请求方式：** post

>**必要参数：**  number：修改之后的数量，最小值为1;shopcartId：购物车Id

>**返回结果:**  true/false

**6.3** 删除购物车

>**Url:** ${ctx}/mobile/member/shopcart/del

>**请求方式：** post

>**必要参数：**  shopcartId：购物车Id

>**返回结果:**  true/false

**6.4** 加入购物车

>**Url:** ${ctx}/mobile/member/shopcart/save

>**请求方式：** post

>**必要参数：**  proId:产品Id； proSkuId：skuId; num:数量

>**返回结果:**  true/false

-------

<h2 id="7"> 7、用户收货地址接口</h2>

** 7.1** 微信H5保存用户收货地址

>**Url:** ${ctx}/weixinapi/address

>**请求方式：** post

>**参数：**  phone：手机号11位，provincename：省名，province:省编码，cityname：市名，city:市行政编码，areaname:区名，area:区行政编码，detail：详细地址，receiver：收货人，openId：微信openId

>**返回结果:**  true/false

** 7.2** 收货地址列表管理

>**Url:** ${ctx}/mobile/member/addr/list

>**请求方式：** get

>**返回结果:**  跳转到收货地址列表管理界面

**7.3** 获取单个收货地址

>**Url:** ${ctx}/mobile/member/addr/get

>**请求方式：** post

>**参数：** id表示要修改的收货地址id值

>**返回结果:**  返回一个收货地址对象

**7.4** 添加保存或修改保存 收货地址

>**Url:** ${ctx}/mobile/member/modify

>**请求方式：** post

>**请求参数：** 必填参数： tdProvince：省份编码，tdCity:市编码,tdArea:县编码，tdProvinceName：省名称，tdCityName：市名称，tdAreaName：县名称，tdDetail：详细地址，tdReciver：收货人，tdPhone：收货手机号
    可填参数：tdPostcode：邮编

>**说明：** 当参数带了 tdId,表示是修改保存，不带表示添加保存

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明","addrId":309}

**7.5**  设置默认收货地址

>**Url:** ${ctx}/mobile/member/addr/defualt

>**请求方式：** post

>**参数：** id表示要设置为默认收货地址id值

>**返回结果:**  true/false

**7.6** 收货地址（新增或编辑）

>**Url:** ${ctx}/mobile/member/addr/edit

>**请求方式：** get

>**参数：** id参数没有表示新增，id有表示要修改的收货地址id值

>**返回结果:**  跳转到添加或者编辑界面

**7.7** 收货地址列表

>**Url:** ${ctx}/mobile/member/addr/addrList

>**请求方式：** POST

>**返回结果:**  
   
    {
    "data": [
        {
            "id": 290,
            "country": "CN",
            "province": "101101",
            "city": "101101101",
            "area": "101101101101",
            "countryName": null,
            "provinceName": "北京市",
            "cityName": "北京",
            "areaName": "东城区",
            "detail": "dsfgdsg",
            "postCode": "123456",
            "phone": "18122457730",
            "tel": null,
            "reciver": "adds",
            "isdefault": 2,
            "memberId": 289,
            "createtime": 1466070586000,
            "updatetime": 1466070586000,
            "page": null,
            "orderBy": null,
            "descOrAsc": null
        }
    ],
    "code": "200",
    "msg": "操作成功"
    }

 -------

<h2 id="8">8 个人中心</h2>

**8.1.1** 用户个人中心界面

>** URL：** ${ctx}/mobile/member/index

>** 返回数据:

    {
      "data": {
        "member": {
          "tmRegisterType": 7,
          "tmMemberActivate": 1,
          "memberAccount": {
            "tmcMemberScore": 2,
            "tmcAccountNo": "1606167314901",
            "tmcEnableScore": 2,
            "tmcId": 287,
            "tmcBalance": 0
          },
          "tmMemberType": 1,
          "tmId": 289,
          "headImg": "/headpic/1467797610127.jpg",
          "tokenVo": {},
          "tmMemberPhone": "18122457730",
          "tmMemberGrade": 0,
          "tmMemberNickname": "jack",
          "tmVip": 0
        },
        "couponNum": 0,
        "orderStatusNums": {
          "11": 5,
          "12": 1,
          "13": 14,
          "14": 6,
          "15": 34
        }
      },
      "code": 200,
      "msg": "操作成功"
    }


**8.1.2** 用户修改密码界面

>**Url:** ${ctx}/mobile/member/modifypwd

>**请求方式：** get

**8.2** 保存用户修改密码

>**Url:** ${ctx}/mobile/member/modifypwd

>**请求方式：** post

>**参数：**  pwd：原密码，newpwd：新密码

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**8.3** 用户首次绑定 或 更换绑定手机、邮箱

>**Url:** ${ctx}/mobile/member/changebind

>**请求方式：** post

>**参数：**  username：新手机号或邮箱，phonecode：手机/邮箱收到的校验码,pwd:登录密码，type：绑定方式（"phone","email"）

>**说明** type为不同的方式，值为其中一个。pwd为校验密码，首次设置传一个"",更换绑定传用户输入的值

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**8.3.1** 检验 用户更换账号绑定时  验证新邮箱或者手机号，是否有绑定过其他的账户

>**URL:** ${ctx}/mobile/member/checkchange

>**请求参数：** username：账号，type:手机/邮箱（phone/email），pwd:密码(初次绑定是不用密码[传一个""空值]，更换绑定时要密码验证)

>**返回结果:** {"code":"结果代码200,300等","msg":"结果说明"}

**8.4** 用户设置/修改支付密码

>**Url:** ${ctx}/mobile/member/paypwd

>**请求方式：** post

>**参数：**  username:账号（手机、邮箱）,paypwd：支付密码，code：手机/邮箱收到的校验码

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**8.4.1** 跳转到用户设置支付密码界面（pc_paypwd.jsp）

>**Url:** ${ctx}/mobile/member/paypwd

>**请求方式：** get

**8.4.2** 检测用户是否设置支付密码

>**Url:** ${ctx}/mobile/member/checkpaypwd

>**请求方式：** post

>**参数：**  无

>**返回结果:**  true/false.true表示用户已设置过支付密码，false表示用户没有设置支付密码。

**8.5** 用户完善个人信息

>*URL:*** ${ctx}/mobile/member/saveinfo

>**说明：** 首次保存个人信息时birday参数必填，再次更新个人信息时不传birday参数值。（即用户一旦保存会员生日之后不能再修改）

>**请求参数:** tmMemberNickname：昵称,tmRealName：真实姓名,tmSex：性别（M/W）,tmBirthday：用户生日（填写之后不可以再修改）,tmIdCard：身份证号

>**返回结果:** true/false

**8.6** 检测用户是否设置支付密码

>**Url:** ${ctx}/web/member/checkpaypwd

>**请求方式：** post

>**参数：**  带token即可

>**返回结果:**  true/false.true表示用户已设置过支付密码，false表示用户没有设置支付密码。

**8.7** 修改用户头像

> **请求url：**${ctx}/mobile/member/updateheadpic

> **请求方式：**post

> **参数：** <br/>
headpic：图片转换成base64形式<br />

> **返回结果:**

    {
         "data": "\\1466142745314.jpeg",
         "code": 200,
         "msg": "头像修改成功"
    }

code=200 为操作成功，300失败，<br />
msg是提示信息，<br />
data 失败的时候为null，成功的时候是图片名称<br />

---------

<h2 id="9">9 省市区三级列表</h2>

>**Url:** ${ctx}/mobile/area/list

>**请求方式：** post

>**必要参数：**  pcode：当为‘1’查询出所有的省;当为省行政编码时查询出该省下所有行政市;当为市行政编码时查询出所有县行政编码

>**说明** pcode传1查询出省，用点击省份的code作pcode查询市，用点击市的code作pcode查询县

>**返回结果:**  list对象 结果集


 ---------------

<h2 id="10">10 用户账户管理接口</h2>

**10.1** 去充值余额页面

>**URL：** ${ctx}/mobile/member/gorecharge

>**请求方式：** get

>**结果：** 跳转到去充值页面：/modules/mobile/member/pc_recharge.jsp 
<br/>

**10.2** 是否拥有支付密码

>**URL：** ${ctx}/mobile/member/checkpaypwd <br/>
>**请求方式：** POST <br/>
>**返回成功：**

	{
    "isSuccess": true
    "data": true /** true：有，false:没有 **
    }

**10.3** 设置支付密码界面

>**URL：** ${ctx}/mobile/member/paypwd

>**请求方式：** get

>**结果：** 跳转设置支付密码界面：/modules/mobile/member/pc_paypwd.jsp
<br/>

**10.4** 设置支付密码接口

>**URL：** ${ctx}/mobile/member/paypwd

>**请求方式：** post

>**参数：** <br/>
code：短信验证码<br/>
paypwd：支付密码<br/>
username：用户手机号或邮箱地址<br/>

>**结果：** 

		{     
         "code": 200,
         "msg": "支付密码设置成功"
     }


**10.5** 生成一个充值待支付记录

>**URL:** ${ctx}/mobile/member/recharge

>**请求方式：** post

>**参数：** <br/>
amount：充值金额（前台控制保留两位小数）<br/>

>**返回成功：**
 
      {
	   "data": {
	            "memberId": 250, 
	            "remark": " recharge account balance ", 
	            "totalFee": 10, 
	            "tradeNo": "250000145647647323838", 
	            "tradeType": 101,/* 余额充值 */
	            "createTime": 1473127828388,
	            "payType": null
	    }, 
	    "code": 308, 
	    "msg": "交易创建成功 "
	}

>**返回说明：** <br/>
data : 充值记录 <br/>
code : (308,交易创建成功)，(221,"支付密码错误")，(222,"支付密码为空") 

**10.6 充值成功请求第三方支付接口（支付宝) **

>**请求URL:**  ${ctx}/alipay/bankspay <br/>

>**接口说明：** 平台完成交易创建记录成功后，用平台交易号向支付宝发起支付请求 <br/>

>**请求参数：** 
   trade_no:充值交易号  <br/>
   
>**返回结果：** 跳转支付宝支付页面待支付
>

**10.8 充值成功请求获取支付参数接口（微信支付) **

>**请求URL:**  ${ctx}/weixin/pay/get_jsapi_package <br/>

>**接口说明：** 平台完成交易创建记录成功后，请求后台获取微信支付配置信息：交易号、签名方式等 <br/>

>**请求参数：** 
   orderNum : 充值交易号  <br/>
   
>**返回结果：** 

			{
	    		    "appId" : data.appId, //公众号名称，由商户传入
               	"timeStamp": data.timeStamp,//时间戳，自 1970 年以来的秒数
               	"nonceStr" : data.nonceStr, //随机串
               	"package" : data.package,
               	"signType" : data.signType,//微信签名方式:
               	"paySign" : data.paySign //微信签名
		    }


##11 账户关联接口

**11.1 跳转去和主账户关联操作**

>**请求URL：** ${ctx}/mobile/member/relat

>**结果:** 跳转到去账户关联的界面（pc_relat.jsp）

>**说明：** 

**11.2 账户关联请求 **

>**URL:** ${ctx}/mobile/member/merge

>**参数:** username：待关联的主账户手机号。pwd：关联主账户的登录密码。

>**返回结果：**  {"code":"结果代码200,300等","msg":"结果说明"}

**11.3 关联账户之间切换登录 **

>**URL:** ${ctx}/mobile/member/relatelogin

>**方式** POST

>**返回结果：**  {"code":"结果代码200,300等","msg":"结果说明"}

----

<h2 id="12">IM账号密码 </h2>

>** 12.1 登录后获取IM账号

>** URL: ${ctx}/mobile/member/im

>** 请求方式: Post

>** 参数： 不需要参数，登录之后即可请求

>** 返回结果：

    {
      "pwd": "10109",
      "name": "EZ16010000582"
    }
    
  ---------------
<h2 id="13">13 用户话费充值接口</h2>

**13.1** 去充值话费页面

>**URL：** ${ctx}/mobile/member/gorechargephone

>**请求方式：** get

>**返回结果：** 
 
     跳转到去充值话费页面：/modules/mobile/member/pc_rechargephone.jsp

**13.2** 号码是否允许充值

>**请求URL:** ${ctx}/mobile/member/phonecheck

>**请求方式：** get

>**请求参数：** <br/>
**phone**：充值号码<br/>
**facevalue**：充值面值 （目前可选：10、20、30、50、100、300）<br/>

>**返回成功：**
 
     {
    "data": null,
    "code": "1000", /* 1000:允许充值 ，208505:错误的手机号码，  208506:错误的充值金额  */
    "msg": "允许充值"
    }

**13.3** 获取话费套餐信息

>**请求URL:** ${ctx}/mobile/member/phonepackage

>**请求方式：** post

>**请求参数：** <br/>
**phone**：充值号码<br/>
**facevalue**：充值面值 （目前可选：10、20、30、50、100、300）<br/>

>**返回成功：**
 
     {
    "data": {
        "phone": "15698566598",
        "errorCode": 0,
        "reason": "查询成功",
        "carId": "10674",
        "cardName": "山西联通话费20元",
        "faceValue": 20, /* 面值 10、20、30、50、100、300 */
        "purchasePrice": 19.96,/* 进货价 */
        "sellPrice": 19.96, /* 平台销售价 */
        "belongArea": "山西太原联通" /* 归属地 */
    },
    "code": "1000",
    "msg": "允许充值"
    }

>**返回说明：** <br/>
>  data : 充值套餐信息 <br/>
>  code:msg : 1000:允许充值 ，208505:错误的手机号码，  208506:错误的充值金额

**13.4** 获取充值面额

>**请求URL:** ${ctx}/mobile/member/facevalue

>**请求方式：** get

>**返回结果：**
  
     {
    "data": [10,20,30,50,100,300],
    "code": "200",
    "msg": "操作成功"
    }

 **13.5** 话费充值接口
 
>**请求URL:** ${ctx}/mobile/member/phonecharge

>**请求方式：** post

>**请求参数：** <br/>
**phone**：充值号码<br/>
**facevalue**：充值面值 （目前可选：10、20、30、50、100、300）<br/>
**paypwd**：支付密码  <br/>

>**返回成功：**

     {
    "data": {
        "phone": "13660362850",
        "errorCode": 0,
        "reason": "订单提交成功，等待充值",
        "carId": "10091",
        "cardName": "广东移动话费1元",
        "faceValue": 1,
        "purchasePrice": 1.06,
        "sellPrice": 1.06,
        "belongArea": "广东广州移动",
        "status": 0,
        "orderNo": "3700001001609191584",
        "tradeNo": "370000147428317598859",
        "thirdNo": "J147428328166413324"
    },
    "code": "1005",
    "msg": "充值进行中"
    }
    
>**其他结果：**
    
     {
    "data": {
        "phone": "13660362850",
        "errorCode": 1004,
        "reason": "账户余额不足",
        "carId": "10091",
        "cardName": "广东移动话费1元",
        "faceValue": 1,
        "purchasePrice": 1.06,
        "sellPrice": 1.06,
        "belongArea": "广东广州移动",
    },
    "code": "1004",
    "msg": "账户余额不足"
    }
    
>**返回说明：** <br/>
data : 充值信息 <br/>
code:msg : **1005:充值中 ，1004:账户余额不足**

 **13.6** 话费充值订单状态更新接口
 
>**请求URL:** ${ctx}/mobile/member/queryphone

>**请求方式：** get

>**请求说明：** <br/>
>  由于调第三方充值接口，整个过程有一些延迟，建议在话费充值接口成功返回后等待几秒再调用此接口

>**请求参数：** <br/>
**orderno**：充值订单号，从话费充值接口返回的数据data.orderNo获取订单号<br/>

>**返回成功：**

    {
    "data": {
        "errorCode": 0,
        "reason": "查询成功",
        "purchasePrice": 1.06,
        "sellPrice": 1.06,
        "thirdNo": "J147428328166413324",
        "chargeStatus": 1
    },
    "code": "1006",
    "msg": "充值成功"
    }

>**返回说明：** <br/>
data : 充值状态信息 <br/>
code:msg : **1005:充值中 ，1006:充值成功，1007:查询无结果**


 ---------

 <h2 id="14">14. Mobile端积分兑换余额接口</h2>

**14.1** 积分兑换余额页面跳转

>**请求URL:** 192.168.1.168/sigoods/mobile/member/exchangescore

>**请求方式：** get

>**返回成功：**<br/>

    1、 跳转到积分兑换余额页面：/modules/mobile/member/pc_exchangescore.jsp      
    2、 绑定数据参数：
      	可用积分：${score}

**14.2** 积分兑换余额接口

>**请求URL:** 192.168.1.168/sigoods/mobile/member/exchangescore

>**请求方式：** post

>**请求参数：** <br/>
**score**：用户手动输入兑换积分值，需要前端保证正整数传递<br/>

>**返回成功：**
 
    {
    "data": {
    			"balance" : 2.5,/*单位（元）*/
    			}
    "code": 200,
    "msg": "操作成功"
    }
 
>**返回说明：**
>1、操作码200表示操作成功；
>2、balance表示成功转换成余额价值，元为单位
