# 手机移动端

## 1.商品评论接口
###1添加商品评论

> **请求url：**http://192.168.1.168/sigoods/moblie/member/msgbox/comment/add

> **请求方式：**post

> **参数：** <br/>
orderNo ：订单号 <br/>
comment ：[] 数组类型：商品评论内容，有多少个商品需要个评论内容<br/>
commentPics ： [] base64编码 字符一维数组类型 ， 数组元素代表一张商品的评价图片字符编码<br/>
picCount ：[] 每种商品即item上传图片数量  <br/>
ssScoreDescriptionMatch ：描述相符分数,1-5分 <br/>
ssScoreServiceAttitude ：服务态度分数,1-5分 <br/>
ssScoreDeliverySpeed ：发货速度分数,1-5分 <br/>
ssScoreExpressSpeed ：快递速度分数,1-5分 <br/>
ssScoreCourierAttitude ：快递员态度分数,1-5分 <br/>
pcIsAnonymous ：//是否匿名 1否 ，2是<br/>
itemIds :[] 退款itemId数组 <br/>
> **返回结果:**
		
	{"code":"200","msg":"操作成功"}

失败的时候为: {"code":"201","msg":"操作失败"} 或为 其他提示语
