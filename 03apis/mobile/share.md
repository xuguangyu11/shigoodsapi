# 手机移动端Mobile 分享模块

###1.获取分享链接接口

**请求url：**http://192.168.1.168/sigoods/mobile/market/share/sharelink

**请求方式：**get

**请求参数：** <br/>
**shareId** ：当前需要分享的记录ID <br/>
**shareLink** ：当前需要分享的链接 <br/>
**shareChannel** ：分享渠道标识：2微信好友，3微信朋友圈，4QQ好友，5QQ空间，6新浪微博，7腾讯微博，8支付宝钱包，9人人网，10豆瓣网，11短信，12邮件，13来往，14易信
<br/>
**shareType** ：分享类型：1商品，2首页，3分类，4注册 <br/>
**shareDetail** ：分享详情：如商品编码、分类ID等,与分享类型配合使用  <br/>

**返回结果:**
>	
	{
    "isSuccess": null,
    "errorCode": null,
    "message": null,
    "data": {
        "shareId": 24000,
        "shareChannel": 4,
        "shareUser": 0,
        "shareTime": 1473127828388,
        "shareType": 1,
        "shareDetail": "P14537048766847503",
        "shareLink": "http://192.168.1.56:8080/sigoods/mobile/product/P14537048766847503?shareUser=0&shareId=24000&shareChannel=4",
        "deviceType": 2,
        "shareClick": null,
        "updateTime": null,
        "qrcodeImg": null,
        "qrcodeTime": null
    },
    "code": "200",
    "msg": "APP End get share link successfully "
    }

>失败的时候为: {"code":"300","msg":"操作失败"} 或为 其他提示语


###2.更新分享链接接口

**请求url：**http://192.168.1.168/sigoods/mobile/market/share/sharesuccess

**请求方式：**get<br/>

**接口说明：** 当M端调第三方API分享操作成功后，回调此接口更新后台分享记录成功状态<br/>

**请求参数：** <br/>
**shareId** ：当前需要分享链接ID <br/>

**返回结果**

	{
    "isSuccess": null,
    "errorCode": null,
    "message": null,
    "data": " Success ",
    "code": "200",
    "msg": " APP End Controller update share record successfully "
    }
	
>失败的时候为: {"code":"300","msg":"操作失败"} 或为 其他提示语



