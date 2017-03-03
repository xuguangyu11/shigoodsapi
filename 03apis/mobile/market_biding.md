# Mobile竞价试用活动模块接口

----

1、 [竞价试用活动](#1)

2、 [出价申请试用](#2)

3、 [我的试用](#3)

4、 [试用报告](#4)

---

<h2 id="1">竞价试用活动</h2>

## 1.1 M端跳转到竞价试用列表界面

>** 请求方式： get

>** url:**  ${ctx}/mobile/member/bidinfo/list

>**结果： 跳转到M端竞价试用活动列表界面

## 1.2 竞价试用活动列表信息list

>** url: ${ctx}/mobile/member/bidinfo/list

>** 请求方式：post

>** 参数 ：**  分页查询 分页属性：currentPage 当前页

>** 返回结果：** 根据 isSuccess的true/false,判断此次请求是否成功，只有为true时才算请求成功结果数据在data里

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": [
        {
          "id": 5,          // 活动id
          "code": "T1004",
          "title": "T1004标题",       //活动标题
          "mainPic": "/market/bid\\T1004\\1472035522883.jpg",       // 活动主图
          "originalPrice": null,     // 活动商品原价
          "price": 5599,             // 商品 竞猜最高价
          "quantity": 5,             // 活动商品数量
          "startTime": 1472043600000,   // 活动开始时间
          "endTime": 1472389200000,     // 活动结束时间
          "status": 2,                  // 活动状态  ，2 表示活动中
          "extLinks": "http://www.baidu.com",   // 活动外部链接
          "page": null,                 // 分页参数
          "applyCount": 0,          //已申请人数
          "isApply": null           //当前用户是否已申请，0表示未申请，11表示审核中，21审核通过,22完成支付，231试用报告审核通过，232试用报告审核未过，31申请失败
        },
        {
          "i                  d": 3,
          "code": "T1002",
          "title": "新品面条机S057竞价试用中",
          "mainPic": "主图地址..",
          "originalPrice": null,
          "price": 9900,
          "quantity": 10,
          "startTime": 1471591672000,
          "endTime": 1471850872000,
          "status": 2,
          "extLinks": null,
          "page": null,
          "applyCount": 0,          //已申请人数
          "isApply": null           //当前用户是否已申请，0表示未申请，11表示审核中，21审核通过,22完成支付，231试用报告审核通过，232试用报告审核未过，31申请失败
        }
      ],
      "code": null,
      "msg": null
    }

    ps: isApply状态说明：前端 取状态值 第一位进行 判断 ，0表示未申请此活动，1开头表示 申请中，2开头表示 申请成功，3开头表示 申请失败


## 1.3 单个竞价试用活动信息 detail

>** url: ${ctx}/mobile/member/bidinfo/i/{id}

>** url: ${ctx}/mobile/member/bidinfo/c/{code}

>**请求方式：** get

>** url说明，两个url都可以请求，第一个传活动信息的id，第二个传活动信息的唯一code

>** 返回结果数据：**  返回结果跳转到 pro_try_detail.jsp界面

    界面返回包括已查询的结果 ${bidInfoDetail} 在jsp界面中可以使用 标签取值。

    {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {
            "id": 1,
            "code": "T1001",
            "type": 1,
            "ruleCode": 1,
            "ruleDescription": "竞价最低且唯一者将得到试用新品资格..",
            "title": "新品面条机S057竞价试用中",
            "description": "竞价试用活动详细内容...",
            "mainPic": "主图地址..",
            "mainDetail": "图文详情..",
            "extLinks": null,
            "createTime": 1471327722000,
            "updateTime": 1472095419000,
            "userId": 17,
            "userName": "sigoods",
            "status": 2,
            "itemId": 3,
            "skuId": 59,
            "endTime": 1471846121000,
            "startTime": 1471586921000,
            "quantity": 10,
            "price": 9900,
            "rebate": 8000,
            "isDelete": 2,
            "originalPrice": null,
            "gtStartTime": null,
            "ltStartTime": null,
            "gtEndTime": null,
            "ltEndTime": null,
            "page": null,
            "productSkuBO": null,
            "applyCount": 1,
            "isApply": null     //当前用户是否已申请，0表示未申请，11表示审核中，21审核通过,22完成支付，231试用报告审核通过，232试用报告审核未过，31申请失败
          },
          "code": null,
          "msg": null
        }

----

<h2 id="2">竞价试用</h2>

## 2.1 用户提交竞价申请

>** url:**  ${ctx}/mobile/member/bidtry/add

>** 参数：** atId:活动信息的id，guessPrice:用户竞猜价格（单位：分）

>** 返回结果：** 根据isSuccess判断操作结果，true表示提交成功，false表示失败

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {

      },
      "code": null,
      "msg": null
    }


<h2 id="3">我的试用</h2>

## 3.1.1跳转到我的试用界面

>** URL : ${ctx}/mobile/member/bidtry/list

>** 请求方式： get

>** 结果 ： 跳转到 /modules/mobile/campaign/pro_try_my.jsp

##  3.1.2 查询用户的竞价试用申请

>** url:** ${ctx}/mobile/member/bidtry/list

>** 参数 ** ：  分页查询 分页属性：currentPage 当前页

>** 返回结果

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": [
        {
          "id": 1,
          "mbId": 289,
          "atId": 1,
          "payFee": null,
          "skuId": null,
          "orderNo": null,
          "mbName": "李四",
          "phone": "13245679874",
          "guessPrice": 599,
          "status": 1,
          "createTime": 1472105546000,
          "updateTime": 1472105542000,
          "page": null,
          "toSubmitReport": false               //此字段 用于判断 是否显示可 填写试用报告的字段
          "bidingInfoBO": {
            "id": 1,
            "code": "T1001",
            "type": 1,
            "ruleCode": 1,
            "ruleDescription": "竞价最低且唯一者将得到试用新品资格..",
            "title": "新品面条机S057竞价试用中",
            "description": "竞价试用活动详细内容...",
            "mainPic": "主图地址..",
            "mainDetail": "图文详情..",
            "extLinks": null,
            "createTime": 1471327722000,
            "updateTime": 1472095419000,
            "userId": 17,
            "userName": "sigoods",
            "status": 2,
            "itemId": 3,
            "skuId": 59,
            "startTime": 1471586921000,
            "endTime": 1471846121000,
            "quantity": 10,
            "price": 9900,
            "rebate": 8000,
            "isDelete": 2,
            "originalPrice": null,
            "gtStartTime": null,
            "ltStartTime": null,
            "gtEndTime": null,
            "ltEndTime": null,
            "page": null,
            "productSkuBO": null,
            "applyCount": 1,
            "isApply": null
          }
        }
      ],
      "code": null,
      "msg": null
    }

## 3.2  申请成功-去确认订单

>** URL: ${ctx}/mobile/member/bidtry/confirm

>** 请求方式： get

>** 参数： actId : 活动id, tryId : 竞价申请id.

>**结果：**  跳转到 订单确认界面  /modules/mobile/campaign/pro_try_buy.jsp

    {
        "tryId": 11,
        "bidingTryBuyFO": {
          "id": 1,
          "code": "T1001",
          "type": 1,
          "title": "新品面条机S057竞价试用中",
          "mainPic": "主图地址..",
          "extLinks": null,
          "status": 2,
          "itemId": 3,
          "itemName": null,
          "skuId": 59,
          "totalFee": 19900,
          "addressList": [
            {
              "id": 309,
              "country": "CN",
              "province": "101101",
              "city": "101101101",
              "area": "101101101101",
              "countryName": null,
              "provinceName": "北京市",
              "cityName": "北京",
              "areaName": "东城区",
              "detail": "dddsssdddddd大声地说",
              "postCode": "56985",
              "phone": "15011566953",
              "tel": null,
              "reciver": "simon",
              "isdefault": 2,
              "memberId": 289,
              "createtime": 1467103654000,
              "updatetime": 1467103653000,
              "page": null,
              "orderBy": null,
              "descOrAsc": null
            },
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
          "defaultAddr": {
            "id": 309,
            "country": "CN",
            "province": "101101",
            "city": "101101101",
            "area": "101101101101",
            "countryName": null,
            "provinceName": "北京市",
            "cityName": "北京",
            "areaName": "东城区",
            "detail": "dddsssdddddd大声地说",
            "postCode": "56985",
            "phone": "15011566953",
            "tel": null,
            "reciver": "simon",
            "isdefault": 2,
            "memberId": 289,
            "createtime": 1467103654000,
            "updatetime": 1467103653000,
            "page": null,
            "orderBy": null,
            "descOrAsc": null
          }
        }
      }


## 3.3 确认订单（创建订单-去支付）

>** URL: ${ctx}/mobile/member/bidtry/create

>** 请求方式： post

>** 参数： locId : 收货地址ID, tryId : 竞价申请id， skuId : 商品skuid

>** 返回参数：  orderno 表示订单号

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": [
        {
          "orderno": xxxxxxx
          }
        }
      ],
      "code": null,
      "msg": null
    }

----

<h2 id="4">试用报告</h2>

## 4.1.1 去填写试用报告

>** URL : ${ctx}/mobile/report/member/to

>** 请求方式： get

>** 参数： actId ：活动id，tryId: 试用申请记录id

>** 结果： 跳转到界面：/modules/mobile/campaign/pro_try_report.jsp 界面

## 4.1.2 我的试用报告(提交试用报告)

>** url:** ${ctx}/mobile/report/member/add

>** 参数说明：**  以pic开头的图片参数传 base64转换之后的数据

>** 请求参数：**  atId:活动id，tryId:竞价试用申请记录id，title:试用报告标题，baseExplain：试用基本说明，
experience：试用心得总结，试用过程详细[ picOne:图片一,remarkOne:说明一，picTwo:图片二,remarkTwo:说明二
picThree:图片三,remarkThree:说明三，picFour:图片四,remarkFour:说明四，picFive:图片五,remarkFive:说明五]

>**返回数据：**

    {
      "isSuccess": true,
      "errorCode": null,
      "message": null,
      "data": {
          id; //试用报告id
          mbId;//用户id
          atId;//活动id
          tryId; // 申请记录id;
          title; //试用报告标题
          createTime;//提交试用报告时间
          baseExplain;//试用基本说明
              //试用过程详情,图文详情
              picOne;
              picTwo;
              picThree;
              picFour;
              picFive;
              remarkOne;
              remarkTwo;
              remarkThree;
              remarkFour;
              remarkFive;
          experience;// 试用后的心得总结
          status;//试用报告 状态  1:审核中，2：审核通过
          clickNum;//被点赞次数
      },
      "code": null,
      "msg": null
    }

## 4.2 我的试用报告(编辑修改 试用报告)

>** url:** ${ctx}/mobile/report/member/edit

>** 参数说明：**  以pic开头的图片参数传 base64转换之后的数据

>** 请求参数：**  id:试用报告id, atId:活动id，tryId:竞价试用申请记录id，title:试用报告标题，baseExplain：试用基本说明，
experience：试用心得总结，试用过程详细[ picOne:图片一,remarkOne:说明一，picTwo:图片二,remarkTwo:说明二
picThree:图片三,remarkThree:说明三，picFour:图片四,remarkFour:说明四，picFive:图片五,remarkFive:说明五]

>** 返回结果：**

    根据isSuccess判断操作结果，true表示提交成功，false表示失败

        {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {

          },
          "code": null,
          "msg": null
        }


## 4.3 我的试用报告(查看单个试用报告)

>** url:** ${ctx}/mobile/report/member/{id}

>** 参数说明：** {id} 为用户提交过的试用报告id。

>** 返回数据：**

    {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {
              id; //试用报告id
              mbId;//用户id
              atId;//活动id
              tryId; // 申请记录id;
              title; //试用报告标题
              createTime;//提交试用报告时间
              baseExplain;//试用基本说明
                  //试用过程详情,图文详情
                  picOne;
                  picTwo;
                  picThree;
                  picFour;
                  picFive;
                  remarkOne;
                  remarkTwo;
                  remarkThree;
                  remarkFour;
                  remarkFive;
              experience;// 试用后的心得总结
              status;//试用报告 状态  1:审核中，2：审核通过
              clickNum;//被点赞次数
          },
          "code": null,
          "msg": null
        }


## 4.4 用户查看所有试用报告)

>** url:** ${ctx}/mobile/report/member/list

>** 参数说明：** 无

>** 返回数据：**

    {
          "isSuccess": true,
          "errorCode": null,
          "message": null,
          "data": {
                {
                  id; //试用报告id
                  mbId;//用户id
                  atId;//活动id
                  tryId; // 申请记录id;
                  title; //试用报告标题
                  createTime;//提交试用报告时间
                  baseExplain;//试用基本说明
                      //试用过程详情,图文详情
                      picOne;
                      picTwo;
                      picThree;
                      picFour;
                      picFive;
                      remarkOne;
                      remarkTwo;
                      remarkThree;
                      remarkFour;
                      remarkFive;
                  experience;// 试用后的心得总结
                  status;//试用报告 状态  1:审核中，2：审核通过
                  clickNum;//被点赞次数
                },
                {
                      id; //试用报告id
                      mbId;//用户id
                      atId;//活动id
                      tryId; // 申请记录id;
                      title; //试用报告标题
                      createTime;//提交试用报告时间
                      baseExplain;//试用基本说明
                          //试用过程详情,图文详情
                          picOne;
                          picTwo;
                          picThree;
                          picFour;
                          picFive;
                          remarkOne;
                          remarkTwo;
                          remarkThree;
                          remarkFour;
                          remarkFive;
                      experience;// 试用后的心得总结
                      status;//试用报告 状态  1:审核中，2：审核通过，3 被驳回
                      clickNum;//被点赞次数
                }
          },
          "code": null,
          "msg": null
        }
