# web Member用户相关接口说明

-------

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


--------

<h2 id="1">1、登录接口</h2>

**1.1** ${ctx}/web/login

>**请求方式：** get

>**返回结果：** 跳转到登录主界面(login.jsp)

    返回文件路径：/modules/web/login.jsp


**1.2** ${ctx}/web/dologin

>**请求方式：** post

>**参数：**username表示手机号或者邮箱，pwd密码
>  {"username":"参数值","pwd":"参数值"}

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

    code为200才表示登录成功

------

<h2 id="2">2、注册接口</h2>

**3.1** ${ctx}/web/register

>**请求方式：** get

>**返回结果：** 跳转到注册界面(register.jsp)

    返回文件路径：/modules/web/register.jsp

**2.2** ${ctx}/web/register

>**请求方式：** post

>**参数：**  username:表示手机号或者邮箱，pwd:密码（前台限制6-20位长度），phonecode:手机、邮箱收到的校验码
>  {"username":"参数值","pwd":"参数值","code":"参数值"}

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

    code返回200表示注册成功

------

<h2 id="3">3、忘记密码，重置密码接口</h2>

**3.1** ${ctx}/web/resetpwd

>**请求方式：** get

>**返回结果：** 跳转到忘记密码界面(passwordBack.jsp)

    返回文件路径：/modules/web/member/passwordBack.jsp


**3.2** ${ctx}/web/resetpwd

>**请求方式：**post

>**参数：**  username:表示手机号或者邮箱，newpwd:密码，code:手机短信收到的校验码

>  {"username":"参数值","newpwd":"参数值","code":"参数值"}

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

    code返回200表示密码重置成功

-------

<h2 id="4">4、获取校验码接口</h2>

**4.1** 获取手机短信校验码

>**URL:** ${ctx}/web/phonecode

>**请求方式：** post

>**参数：** phone：手机号，type(1、2)1表示注册或更换绑定手机号时调用接口，2表示忘记密码,设置支付密码调用接口,validcode:图形验证码。

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**4.2** 获取邮箱短信校验码

>**URL:** ${ctx}/web/emailcode

>**请求方式：** post

>**参数：** email：邮箱号，type(1、2)1表示注册或更换绑定邮箱号时调用接口，2表示忘记密码,设置支付密码时调用接口，validcode:图形验证码。

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}

**4.3** 检验校验码是否正确接口

>**URL:** ${ctx}/web/checkcode

>**请求方法：**post

>**参数：**	code："校验码" ,username:"手机号/邮箱号"

>**返回结果：**  {"code":"结果代码200,300等","msg":"结果说明"}

-----

<h2 id="5">5 检测username是否已经被使用</h2>

**5.1** 请求，检测username(手机/邮箱)是否已经使用

>**URL:** ${ctx}/web/checkusername

>**请求方式：** post

>**参数：** username：登录账号（手机、邮箱）

>**返回结果:**  {"true/false":已经使用返回true，未使用返回false}

-------

<h2 id="6"> 6 购物车接口</h2>

**6.1** 购物车列表

>**Url:** ${ctx}/web/member/shopcart/list

>**请求方式：** get

>**参数：** 可带查询条件（参数名为实体shopcartVO的属性）    ``

>**返回结果:**  购物车列表结果集(/modules/web/member/cart/pro_cart.jsp) 界面

**6.2** 修改购物车数量

>**Url:** ${ctx}/web/member/shopcart/num

>**请求方式：** post

>**必要参数：**  num：修改之后的数量，最小值为1;shopcartId：当前购物车的Id

>**返回结果:** 根据isSuccess判断操作是否成功

        {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {
                "update success."
          },
          "code": null,
          "msg": null
        }

**6.3** 删除购物车

>**Url:** ${ctx}/web/member/shopcart/del

>**请求方式：** post

>**必要参数：**  shopcartId：购物车Id

>**返回结果:**

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {
            "delete success."
      },
      "code": null,
      "msg": null
    }

**6.4** 加入购物车

>**Url:** ${ctx}/web/member/shopcart/save

>**请求方式：** post

>**必要参数：**  proId:产品唯一Id； proSkuId：skuId（sku唯一id）; num:数量

>**返回结果:**

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {
            "delete success."
      },
      "code": null,
      "msg": null
    }

-----

<h2 id="7"> 7、用户收货地址接口</h2>

>** 7.1** 收货地址列表接口

>**7.1.1** 跳转到收货列表接口

>**Url:** ${ctx}/web/member/addr/list

>** 请求方式：get

>** 跳转界面路径： /modules/web/member/web_addr.jsp

>** 返回数据，在jsp中 遍历 ${addrs}

    数据格式：
    [
      {
        "area": "104104101106",
        "areaName": "天河区",
        "city": "104104101",
        "cityName": "广州市",
        "country": "CN",
        "createtime": 1466491616000,
        "detail": "黄铺大道",
        "id": 297,
        "isdefault": 1,
        "memberId": 291,
        "phone": "13242322015",
        "postCode": "513001",
        "province": "104104",
        "provinceName": "广东省",
        "reciver": "lzs1",
        "updatetime": 1467105318000
      },
      {
        "area": "105101101104",
        "areaName": "锦江区",
        "city": "105101101",
        "cityName": "成都市",
        "country": "CN",
        "createtime": 1466654112000,
        "detail": "xxxxxxfafeaa",
        "id": 298,
        "isdefault": 2,
        "memberId": 291,
        "phone": "15023121231",
        "postCode": "456321",
        "province": "105101",
        "provinceName": "四川省",
        "reciver": "lzs02",
        "updatetime": 1467105313000
      }
    ]


>**7.1.2** 异步 获取个人的所有收货地址集合

>**Url:** ${ctx}/web/member/addr/list

>**请求方式：** post  异步获取 收货地址list

>**返回结果:**  收货地址列表结果

    根据isSuccess的值（true/false）判断请求是否通过，返回数据在data里

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": [
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
          "updatetime": 1467105318000,
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
          "updatetime": 1467105313000,
          "page": null,
          "orderBy": null,
          "descOrAsc": null
        }
      ],
      "code": null,
      "msg": null
    }

**7.2** 获取用户 单个收货地址详情  接口

>**Url:** ${ctx}/web/member/addr/detail

>**请求方式：** post

>**必要参数：**  id :单个收货地址id.

>**返回结果:**  返回单条收货地址数据json

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": "{\"id\":298,\"country\":\"CN\",\"province\":\"105101\",\"city\":\"105101101\",\"area\":\"105101101104\",\"countryName\":null,\"provinceName\":\"四川省\",\"cityName\":\"成都市\",\"areaName\":\"锦江区\",\"detail\":\"xxxxxxfafeaa\",\"postCode\":\"456321\",\"phone\":\"15023121231\",\"tel\":null,\"reciver\":\"lzs02\",\"isdefault\":2,\"memberId\":291,\"createtime\":1466654112000,\"updatetime\":1467105313000,\"page\":null,\"orderBy\":null,\"descOrAsc\":null}",
      "code": null,
      "msg": null
    }

**7.3** 收货地址（新增或编辑）

>**Url:** ${ctx}/web/member/addr/edit

>**请求方式：** get

>**参数：** id参数:没有id表示新增，有id 表示要修改的收货地址id( 有id 界面 通过${addr }取属性值)

>**返回结果:**  跳转到添加或者编辑界面(web_addr_edit.jsp)

**7.4** 添加保存或修改保存 收货地址

>**Url:** ${ctx}/web/member/modify

>**请求方式：** post

>**请求参数：** 必填参数： tdProvince：省份编码，tdCity:市编码,tdArea:县编码，tdProvinceName：省名称，tdCityName：市名称，tdAreaName：县名称，tdDetail：详细地址，tdReciver：收货人，tdPhone：收货手机号
    可填参数：tdPostcode：邮编

>**说明：** 当参数有 tdId,表示是修改保存，没有tdId表示添加保存

>**返回结果:**  isSuccess为true时，data里 包含 当前更新或者添加的收货地址信息

    {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": "{\"id\":298,\"country\":\"CN\",\"province\":\"105101\",\"city\":\"105101101\",\"area\":\"105101101104\",\"countryName\":null,\"provinceName\":\"四川省\",\"cityName\":\"成都市\",\"areaName\":\"锦江区\",\"detail\":\"xxxxxxfafeaa\",\"postCode\":\"456321\",\"phone\":\"15023121231\",\"tel\":null,\"reciver\":\"lzs02\",\"isdefault\":2,\"memberId\":291,\"createtime\":1466654112000,\"updatetime\":1467105313000,\"page\":null,\"orderBy\":null,\"descOrAsc\":null}",
          "code": null,
          "msg": null
        }

**7.6**  设置默认收货地址

>**Url:** ${ctx}/web/member/addr/defualt

>**请求方式：** post

>**参数：** id ：表示要设置为默认收货地址id值

>**返回结果:**

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": "{success/fail}",
      "code": null,
      "msg": null
    }

-------

<h2 id="8">8 个人中心</h2>

**8.1** 我的帐号

>**URL:** ${ctx}/web/member/index

>**请求方式：** get

>**返回到 个人中心界面。（/modules/web/member/web_index.jsp）

>**返回数据 ** 界面可以直接使用 ${member},${couponNum}等取值

    {
        "member": {
          "id": 291,
          "nickname": "Wickywe",   // 昵称
          "idCard": "",
          "realName": "Wickywe",
          "phone": "13242322015",  //手机号
          "email": "819251724@qq.com",  //邮箱号
          "loginPwd": null,
          "headImg": "/1469774838934.jpeg", //头像
          "sex": 1,     //性别  1 男，2女，0未知
          "birthday": 708624000000,   // 生日
          "address": null,
          "grade": 0,        // 账户 等级
          "type": 1,
          "vip": 0,           // vip等级
          "registerType": 9,
          "activate": 1,
          "qqOpenid": null,
          "weixinOpenid": null,
          "mobileqqOpenid": null,
          "wxgzhOpenid": "",
          "wxUnionid": null,
          "enable": 1,
          "isdelete": 2,
          "createtime": 1466070896000,
          "updatetime": 1466133125000,
          "page": null,
          "orderBy": null,
          "descOrAsc": null,
          "accountinfoBO": {
            "id": 289,
            "accountNo": "1606162161901",    //  钱包账户号
            "payPwd": null,
            "balance": 0,                    // 余额： 单位分
            "memberId": 291,
            "enableScore": 4,                // 可用积分
            "totalScore": 4,                 // 总积分
            "createtime": 1466070896000,
            "updatetime": 1468377965000
          },
          "apptokenBO": null
        },
        "couponNum": 0,
        "orderStatusNums": {
          "11": 1,
          "13": 1,
          "15": 7
        }
     }
    ps:orderStatusNums 订单状态对应的数量。
        10: 等待用户支付的订单
        11：等待发货中的订单
        12：等待收货的订单
        13：等待评论的订单
        14：已评论的订单
        15：已关闭的订单



**8.2** 用户修改密码界面(web_pwd.jsp)

>**URL:** ${ctx}/web/member/modifypwd

>**请求方式：** get

>**  跳转到用户修改密码界面（/modules/web/member/web_pwd.jsp）

**8.2.1** 用户修改密码

>**URL:** ${ctx}/web/member/modifypwd

>**请求参数：** newpwd:新密码，pwd:原密码

>**请求方式：** post

>**返回结果:**  根据isSuccess判断操作结果，true表示操作成功，false表示失败

        {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {

          },
          "code": null,
          "msg": null
        }

**8.3** 用户更换账号绑定

>**URL:** ${ctx}/web/member/changebind

>**请求参数：** code:校验码，username：（新）账号，type:手机/邮箱（phone/email），pwd:密码(初次绑定是不用密码[传一个""空值]，更换绑定时要密码验证)

>**返回结果:** {"code":"结果代码200,300等","msg":"结果说明"}

**8.3.1** 跳转到绑定手机界面(changephone.jsp)

>**请求方式：** get

>**URL:** ${ctx}/web/member/changephone

**8.3.2** 跳转到绑定手机界面(changeemail.jsp)

>**请求方式：** get

>**URL:** ${ctx}/web/member/changeemail

**8.3.3** 检验 用户更换账号绑定时  验证新邮箱或者手机号，是否有绑定过其他的账户

>**URL:** ${ctx}/web/member/checkchange

>**请求方式：** post

>**请求参数：** username：账号，type:手机/邮箱（phone/email），pwd:密码(初次绑定是不用密码[传一个""空值]，更换绑定时要密码验证)

>**返回结果:** {"code":"结果代码200,300等","msg":"结果说明"}

**8.4** 用户完善个人信息

>*URL:*** ${ctx}/web/member/saveinfo

>**说明：** 首次保存个人信息时birday参数必填，再次更新个人信息时不传birday参数值。（即用户一旦保存会员生日之后不能再修改）

>**请求参数:** tmMemberNickname：昵称,tmRealName：真实姓名,tmSex：性别（M/W）,tmBirthday：用户生日（填写之后不可以再修改）,tmIdCard：身份证号

>**返回结果:** true/false

**8.5.1** 跳转到用户设置支付密码界面（web_paypwd.jsp）

>**Url:** ${ctx}/web/member/paypwd

>**请求方式：** get

**8.5.2** 用户设置/修改支付密码

>**Url:** ${ctx}/web/member/paypwd

>**请求方式：** post

>**参数：**  username:账号（手机、邮箱）,paypwd：支付密码，code：手机/邮箱收到的校验码

>**返回结果:**  {"code":"结果代码200,300等","msg":"结果说明"}


**8.5.3** 检测用户是否设置支付密码

>**Url:** ${ctx}/web/member/checkpaypwd

>**请求方式：** post

>**参数：**  无

>**返回结果:**  true/false.true表示用户已设置过支付密码，false表示用户没有设置支付密码。

------

<h2 id="9">9 省市区三级列表</h2> 

>**Url:** ${ctx}/web/area/list

>**请求方式：** post

>**必要参数：**  pcode：当为‘1’查询出所有的省;当为省行政编码时查询出该省下所有行政市;当为市行政编码时查询出所有县行政编码

>**说明** pcode传1查询出省，用点击省份的code作pcode查询市，用点击市的code作pcode查询县

>**返回结果:**  list对象 结果集

<h2 id="10">10 账户充值</h2>

**10.1 去充值界面（web_recharge.jsp） **

>**请求URL:** ${ctx}/web/member/gorecharge



**10.2 创建充值流水记录 **

>**请求URL:** ${ctx}/web/member/recharge

>**请求参数：** amount：充值金额（只充值整数金额）

>**返回结果说明：** data里面是充值记录。
{
    "data": {
        "data": {
            "member_id": 250, 
            "remark": "账号进行充值", 
            "total_fee": 1, 
            "trade_no": "250000145647647323838", 
            "trade_type": 1
        }
    }, 
    "code": 200, 
    "msg": "创建充值交易记录成功"
}


**10.2 充值成功回调方法 **

>**请求URL:** ${ctx}/web/member/payrefund

>**请求参数：** paytype：支付方式（0支付宝，1微信支付),tradeno:充值交易号

>**返回结果：**true:账户余额充值成功，false：账号余额充值失败

-------
