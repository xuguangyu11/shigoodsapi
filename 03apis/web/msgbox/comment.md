# PC端评论接口

-------
1. [获取商品评论列表](#1)
2. [添加商品评论接口](#2)

 --------
<h2 id="1"></h2>
###1 获取商品评论列表

>**请求url：**http://192.168.1.168/sigoods/web/comment/list/{code}

>**请求方式：**get <br/>
>**接口描述：** 接口返回在指定商品编码下的商品评论记录数据 <br/>
>**输入参数：** <br/>
**code** ：商品编码如：P14536923627706448 <br/>
**currentPage** ：当前页数,默认第1页<br/>
**showCount** ：每页显示记录数，默认10条记录 <br/>

**参数说明：** <br/>
	
	data:数据主体
	code:200数据返回正常
	msg:数据返回描述
	count : 商品评论总数
	
	pcId;//主键
	pcCreateTime;//创建时间
	pcMemberId;//评论人id
	pcProductId;//商品id
	pcOrderNo;//订单号
	pcImgs;//图片串
	pcType;//1正常使用，0删除
	pcParentId;//上级评论id，第一次评论为空
	pcText;//评论内容
	pcThumbImgs;//缩略图
	pcNickName;// 用户昵称
	pcAreaInfo;//用户地区信息
	pcIsAnonymous;//是否匿名 1否 2是
	
	member：
		id			//用户ID;
		nickname;    //昵称
		idCard;		//证件号（身份证）
		realName;	//真实姓名
		phone;		//手机号
		email;		//邮箱
		loginPwd;	//登录密码
		headImg;		//头像
		sex;			//性别
	

**返回结果:**
>	
	{
	"count":71,
    "data": [
        {
            "member": {
                "activate": 2,
                "address": "",
                "birthday": 1443888000000,
                "createtime": 1466131615000,
                "email": "249910142@qq.com",
                "enable": 1,
                "grade": 1,
                "headImg": "/1467685688432.jpeg",
                "id": 295,
                "idCard": "",
                "isdelete": 2,
                "loginPwd": "3ade3fd6e8eef84f2ea91f6474be10d9",
                "nickname": "",
                "realName": "徐通",
                "registerType": 9,
                "sex": 1,
                "type": 1,
                "updatetime": 1471422055000,
                "vip": 0,
                "wxgzhOpenid": "okAuwjjVRCeK9lsq0wPY9byUYyZY"
            },
            "pcAreaInfo": "北京",
            "pcCreateTime": 1471514822000,
            "pcId": 10839,
            "pcIsAnonymous": 2,
            "pcMemberId": 295,
            "pcOrderNo": "2950001001608180679",
            "pcParentId": 0,
            "pcProductId": 42,
            "pcText": "M端",
            "pcType": 1
        },
        {
            "pcAreaInfo": "辽宁",
            "pcCreateTime": 1471419365000,
            "pcId": 10836,
            "pcIsAnonymous": 2,
            "pcMemberId": 348,
            "pcOrderNo": "3480001001608173581",
            "pcParentId": 0,
            "pcProductId": 60,
            "pcText": "111",
            "pcType": 1
        },
        {
            "member": {
                "activate": 1,
                "createtime": 1466070495000,
                "enable": 1,
                "grade": 0,
                "headImg": "/1467797610127.jpg",
                "id": 289,
                "isdelete": 2,
                "loginPwd": "e10adc3949ba59abbe56e057f20f883e",
                "nickname": "j***k",
                "phone": "181***7730",
                "registerType": 7,
                "type": 1,
                "updatetime": 1466070495000,
                "vip": 0
            },
            "pcAreaInfo": "北京",
            "pcCreateTime": 1471340799000,
            "pcId": 10832,
            "pcImgs": "/1471340798772.jpg,/1471340808492.jpg,/1471340812779.jpg,/1471340815871.jpg",
            "pcIsAnonymous": 2,
            "pcMemberId": 289,
            "pcNickName": "j***k",
            "pcOrderNo": "2890001001607043773",
            "pcParentId": 0,
            "pcProductId": 34,
            "pcText": "Test For air",
            "pcThumbImgs": "/1471340798772_100x100.jpg,/1471340808492_100x100.jpg,/1471340812779_100x100.jpg,/1471340815871_100x100.jpg",
            "pcType": 1
        },
        {
            "member": {
                "activate": 1,
                "createtime": 1466070495000,
                "enable": 1,
                "grade": 0,
                "headImg": "/1467797610127.jpg",
                "id": 289,
                "isdelete": 2,
                "loginPwd": "e10adc3949ba59abbe56e057f20f883e",
                "nickname": "j***k",
                "phone": "181***7730",
                "registerType": 7,
                "type": 1,
                "updatetime": 1466070495000,
                "vip": 0
            },
            "pcAreaInfo": "北京",
            "pcCreateTime": 1471340640000,
            "pcId": 10831,
            "pcIsAnonymous": 2,
            "pcMemberId": 289,
            "pcNickName": "j***k",
            "pcOrderNo": "2890001001607043773",
            "pcParentId": 0,
            "pcProductId": 5,
            "pcText": "Just so so!",
            "pcType": 1
        }
    ],
    "code": "200",
    "msg": "web端查询商品评论列表成功"
	}
	失败的时候为: {"code":"201","msg":"操作失败"} 或为 其他提示语

 --------
<h2 id="2"></h2>
###2 添加商品评论接口

> **请求url：**http://192.168.1.168/sigoods/web/comment/add

> **请求方式：**post

> **参数：** <br/>
**orderNo** ：订单号 <br/>
**comment** ：[] 数组类型：商品评论内容，有多少个商品需要个评论内容<br/>
**commentPics** ： [] base64编码 字符一维数组类型 ， 数组元素代表一张商品的评价图片字符编码<br/>
**picCount** ：[] 每种商品即item上传图片数量  <br/>
ssScoreDescriptionMatch ：描述相符分数,1-5分 <br/>
ssScoreServiceAttitude ：服务态度分数,1-5分 <br/>
ssScoreDeliverySpeed ：发货速度分数,1-5分 <br/>
ssScoreExpressSpeed ：快递速度分数,1-5分 <br/>
ssScoreCourierAttitude ：快递员态度分数,1-5分 <br/>
**pcIsAnonymous** ：//是否匿名 1否 ，2是<br/>
**itemIds** :[] 退款itemId数组 <br/>
> **返回结果:**
		
	{"data":"Success","code":"200","msg":"操作成功"}

>失败的时候为: {"code":"201","msg":"操作失败"} 或为 其他提示语
