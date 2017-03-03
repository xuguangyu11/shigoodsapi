# Mobile组团活动活动模块接口

----

1、[组团跳转](#1)

2、[组团列表](#2)

3、[活动详情](#3)

4、[参与组团](#4)

5、[确认组团](#5)

6、[我的团购](#6)

7、[规则详情](#7)

---

<h2 id="1">组团跳转</h2>

## M端跳转到组团列表界面

>** 请求方式： get

>** url:**  ${ctx}/mobile/member/market/activity/list

>**结果： 跳转到M端组团活动列表界面

<h2 id="2">组团列表</h2>

##  获取组团列表数据

>** 请求方式： post

>** 参数 ：**  分页查询 分页属性：currentPage 当前页

>** url:**  ${ctx}/mobile/member/market/activity/list

>** 返回结果：** 根据 isSuccess的true/false,判断此次请求是否成功，只有为true时才算请求成功结果数据在data里

      {
        "isSuccess": true,
        "errorCode": null,
        "message": null,
        "data": [
          {
            "id": 14000,                -------活动ID                                
            "code": "EZ10086",          -------活动编码
            "type": 1,                  -------活动类型
            "title": "EZ0001",          -------活动主题
            "mainPic": "/market/activity\\null\\1472725871784.jpg", --------活动列表主图(长型图)
        	"detailPic":"/market/activity\\null\\1472725871784.jpg",--------活动详情图(方形图)
            "url": "http://www.baidu.com", -------活动链接
            "state": 1,                   -------活动状态
            "itemId": 16,                 -------商品ID
            "itemName": "时物多功能多士炉", -------商品名称
            "skuId": 75,                  --------skudID
            "quantity": 10,               --------数量
            "actbuyNum":5,                --------购买数量
            "actlockNum":2,               --------活动商品锁定数量
            "price": 100,                 --------价格  
            "restriction": 5,             --------限购数量
            "virtualNum": 5,              --------虚拟用户
            "realNum": 3,                 --------真实用户
            "startTime": 1474626600000,   --------开始时间
            "endTime": 1475321700000,     --------结束时间
            "buyNum": 2,                  --------用户购买数量
            "minNum": 5,                  --------满足最低优惠的人数
            "cashBack": 5,                --------最低返现
            "page": null
          }
        ],
        "code": null,
        "msg": null
      }

<h2 id="3">活动详情</h2>

##  获取活动详情

>** 请求方式： post

>** 参数 ：

    actId : 活动ID

>** url:**  ${ctx}/mobile/member/market/activity/detail

>** 返回结果：** 根据 isSuccess的true/false,判断此次请求是否成功，只有为true时才算请求成功结果数据在data里

    {
        "id": 14000,       --------活动ID
        "code": "EZ10086", --------活动编码
        "type": 1,         --------活动类型
        "title": "EZ0001", --------活动标题
        "direction": "活动说明说明说明说明", --------活动说明
        "mainPic": "/market/activity\\null\\1472725871784.jpg", --------活动主图(长型图)
        "detailPic":"/market/activity\\null\\1472725871784.jpg",--------活动详情图(方形图)
        "mainDetail": "797615565654qw4f1a2sd31f23a1s54f6q4w1f3a1sd2f16q<img src=\"http://192.168.1.168:81/uploadfile/shiwu/market/activity\\null\\1472725883221.jpg\">", --------活动图文详情
        "url": "http://www.baidu.com",  --------活动链接
        "actruleName": "组团001",       --------活动规则名称
        "state": 1,                     --------活动状态
        "itemId": 16,                   --------商品ID
        "itemName": "时物多功能多士炉", --------商品名称
        "skuId": 75,                    --------skuId
        "quantity": 10,                 --------数量
        "actbuyNum":5,                  --------购买数量
        "actlockNum":2,                 --------活动商品锁定数量
        "price": 100,                   --------价格
        "restriction": null,            --------限购数量
        "virtualNum": 5,                --------虚拟用户
        "realNum": 2,                   --------真实用户  
        "startTime": 1474626600000,     --------开始时间
        "endTime": 1475321700000,       --------结束时间
        "sysTime":1475321700000,   --------系统当前时间
        "actruleMainList": [            =======规则信息列表
          {
            "id": 1,                    -------规则ID
            "code": "EZ001",            -------规则编码
            "name": "组团001",          -------规则名称
            "type": null,               -------规则类型
            "ruleState": null,          -------规则状态
            "chooseWay": null,          -------返利方式
            "minNum": 5,                -------最小区间
            "maxNum": 10,               -------最大区间
            "discountRate": null,       -------折扣率
            "cashBack": 5               -------返现金额
          },
          {
            "id": 2,
            "code": "EZ001",
            "name": "组团001",
            "type": null,
            "ruleState": null,
            "chooseWay": null,
            "minNum": 10,
            "maxNum": 15,
            "discountRate": null,
            "cashBack": 10
          }
        ],
        "memberRestriction": null
      }


<h2 id="4">参与组团</h2>

##  参与组团,点击参与组团按钮跳转到确认页面

>** 请求方式： get/post

>** 参数 ：

    actId : 活动ID
    buyNum : 购买数量

>** url:**  ${ctx}/mobile/member/market/activity/act_buy_page

>** 返回结果
    
    返回pro_activity_buy 页面

    返回对象:actBuyPage

    获取方式: 

        例:获取活动活动code ${actBuyPage.code}

    对象属性:
   
    id:活动ID

    code:活动编码

    type:活动类型
    
    title:活动主题
    
    mainPic:活动主图

    url:活动链接

    state:活动状态

    itemId:活动商品ID
    
    itemName:活动商品名称
    
    skuId:活动skuID
    
    price:活动支付金额

    addressList:用户收货地址列表 List<MemberAddressBO>
    
    defaultAddr:默认收货地址  MemberAddressBO 
    
    totalFee:购买总价

<h2 id="5">确认组团</h2>

##  点击确认组团,跳转到支付宝支付页面

>** 请求方式： get/post

>** 参数 ：

    totalFee : 购买总价
    skuId : skuId
    buyNum : 购买商品数量
    locId : 收货地址ID
    shopId : 商家ID
    actId : 活动ID
  

>** url:**  ${ctx}/mobile/member/market/groupact/join_group_act

>** 返回结果  

    根据 isSuccess的true/false,判断此次请求是否成功，只有为true时才算请求成功结果数据在data里
    
       {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": "2960001001609130098", ----订单号
          "code": null,
          "msg": null
        }

<h2 id="6">我的组团</h2>

## 我的组团页面

   (1)跳转到我的组团页面

   >** 请求方式： get
   
   >** url:**  ${ctx}/mobile/member/market/groupact/groupact_list

   (2)获取页面信息(我的组团)

    >** 请求方式： get/post

    >** url:**  ${ctx}/mobile/member/market/groupact/get_my_groupAct

    >** 参数 ：

    分页查询 分页属性：currentPage 当前页
    status : 组团活动状态 (组团中:10,组团成功:30,组团失败:20)


    >** 返回结果  根据 isSuccess的true/false,判断此次请求是否成功，只有为true时才算请求成功结果数据在data里
        
         {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": [
            {
              "id": 3,
              "atId": 14000,  -----------活动ID
              "mbId": 296,    -----------用户ID
              "mbName": "lee", ----------用户名称
              "phone": "15918737729", --------用户号码
              "mbType": 1,            --------用户类型
              "skuId": 75,            --------skuId
              "buyNum": 2,            --------购买数量
              "orderNo": "2960001001609130098", -------订单号
              "payFee": 50,           --------支付金额
              "status": 1,            --------参团状态
              "cashState":1,      --------返现状态 (1:返现中,2:返现成功,3:返现失败)
              "createTime": 1473750063000, ------创建时间
              "updateTime": 1473750063000, ------修改时间
              "activityMainBO": {   -------活动主题信息
                "id": 14000,        -------活动ID
                "code": "EZ10086",  -------活动编码
                "type": 1,          -------活动类型
                "title": "EZ0001",  -------活动主题
                "mainPic": "/market/activity\\null\\1472725871784.jpg", --------活动主图(长型图)
       			"detailPic":"/market/activity\\null\\1472725871784.jpg",--------活动详情图(方形图)
                "url": "http://www.baidu.com", --------活动URL
                "state": 3,         -------活动状态
                "itemId": 16,       -------商品ID
                "itemName": "时物多功能多士炉", -------商品名称
                "itemCode":X89898ASF,     -------商品编码
                "skuId": 75,        -------skuId
                "quantity": 10,     -------库存数量
                "price": 100,       -------活动商品价格
                "restriction": null,-------限购数量   
                "virtualNum": 5,    -------虚拟用户
                "realNum": 1,    -------真实用户
                "actruleCode":GZ001, -----规则编码
                "buyNum":1,  ------用户购买数量
                "minNum":5,  ------规则最小值
                "maxNum":20, ------规则最大值
                "cashBack":10,   -------返现金额
                "isCashback":1,  -------是否返现(1:是,2:否)
                "shopId":1,      -------商户ID
                "startTime": 1474626600000, ------活动开始时间
                "endTime": 1475321700000,   ------活动结束时间
                "page": null
              }
            }
          ],
          "code": null,
          "msg": null
        }

<h2 id="7">规则详情</h2>

##  通过规则编码 获取活动规则详情页面进行展示

>** 请求方式： get/post

>** 参数 ：

    code : 规则编号
  

>** url:**  ${ctx}/mobile/mobile/market/actrule/actrule_get/{code}

>** 返回结果  
    
    规则详情页面
   