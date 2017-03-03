# 手机移动端

###1根据退款类型获取退款原因

> **请求url：**http://192.168.1.168/shiwu/mobile/member/custservice/refund/get_reason

> **请求方式：**get

> **参数：** <br/>
type ：退款类型，1表示仅退款，2表示退款退货 <br/>

> **返回结果:**

	{
	    "data": {
	        "1": "卖家缺货",
	        "2": "拍错了",
	        "3": "不想要了",
	        "4": "未按约定时间发货"
	    },
	    "code": "200",
	    "msg": "操作成功"
	}

###2添加退款申请

> **请求url：**http://192.168.1.168/shiwu/mobile/member/custservice/refund/add

> **请求方式：**post

> **参数：** <br/>
trId :   退款单Id  ---不为空则为修改(也就是业务中的重新申请退款)
trOrderNo ：涉及订单 <br/>
trSkuId ：涉及商品skuid <br/>
trRefundType ：退款类型，1表示仅退款，2表示退款退货 <br/>
trReason ：退款原因id <br/>
trMoney ：退款金额，大于0，小于等于订单总额 <br/>
trExplain ：退款说明 <br/>
refundPics : 退货图片凭证 base64 集<br/> 

> **返回结果:**

	{
	    "data": null,
	    "code": "200",
	    "msg": "操作成功"
	}


###3获取我的退款申请

> **请求url：**http://localhost:8081/sigoods/mobile/member/custservice/get_records

> **请求方式：**get

> **参数：** <br/>
showCount ：每页显示记录数 <br/>
currentPage ：当前页，主要靠这个进行分页<br/>

> **参数说明**
    
> **返回结果:**
	
	{
	  "data": [
	    {
	      "refundState": 10,
	      "orderNo": "2890001001607210932",
	      "orderItems": [
	        {
	          "itemNum": 1,
	          "itemName": "NM-0001全自动家用面条机",
	          "itemSkuId": 68,
	          "itemImg": "/product/null/1454051056095.png",
	          "itemPrice": 799,
	          "itemSku": [
	            "容量:一次1000g面粉",
	            "型号:SG-NM-0001G",
	            "品牌:时物1"
	          ],
	          "itemRefundId": 122
	        }
	      ],
	      "refundType": 2,
	      "totleFee": 700
	    },
	    {
	      "refundState": 7,
	      "orderNo": "2890001001607220213",
	      "orderItems": [
	        {
	          "itemNum": 1,
	          "itemName": "多士炉家用 自动调档",
	          "itemSkuId": 62,
	          "itemImg": "/product/null/1453693956884.jpg",
	          "itemPrice": 0,
	          "itemSku": [
	            "颜色分类:白色"
	          ],
	          "itemRefundId": 116
	        }
	      ],
	      "refundType": 1,
	      "totleFee": 0
	    }
	  ],
	  "code": "200",
	  "msg": "操作成功"
	}

	
###4获取退款详情

> **请求url：**http://192.168.1.168/shiwu/mobile/member/custservice/get_detail

> **请求方式：**get

> **参数：** <br/>
trId：退款id主键 <br/>

> **参数说明：** <br/>

	Refund:退款申请
	trId;//主键
    trCreateTime;//创建时间
    trMemberId;//申请人
    trType;//投诉建议分类
    trOrderNo;//涉及订单
    trProductId;//涉及商品
    trSkuId;//涉及商品sku
    trRefundType;//退款类型
    trReason;//退款原因
    trState;//货物状态
    trMoney;//退款金额
    trExplain;//退款说明
    trVoucher;//图片凭证
    trRefundState;//退款状态
    trPaymentType;//原订单支付类型，退款支付类型，根据原路径返回
    trNo;//退款号
    trUpdateTime;//修改时间
    trRefundStateText;//退款状态文本
    trRefundTypeText;//退款类型文本
    trReasonText;//退款原因文本
    refundMessageLogs;//退款留言日志实体
    order;//订单实体
    
    refundMessageLogs:退款留言日志实体
    rmlId;//主键
    rmlSponsorId;//发起人id，既处理这个动作的人
    rmlBuyersMemberId;//买家id
    rmlCreateTime;//创建时间
    rmlText;//留言内容
    rmlTrId;//退款id
    rmlTrRefundState;//当时的退款状态
    rmlTrRefundStateText;//当时的退款状态文本
    
    order:订单实体
    oid;//主键
    order_name;//订单名称
	order_no;//订单号
	trade_no;//交易号
	total_fee;//总费用
	discount_fee;//总折扣费用
	payment;//实际支付费用
	member_id;//会员id
	invalid_time;//失效时间
	source;//订单来源
	status;//订单状态
	od_type;//订单类型，商品订单，虚拟产品订单，现在交易订单等
	delivery_time;//预计发货时间
	real_delivery_time;// 实际发货时间
	location_id;//发货地址id
	freight_fee;// 订单实际邮费
	leave_word;//用户留言
	is_delete;//是否删除 ，0未删除，1删除
	shop_id;//商家的id
	create_time;
	update_time;
	//引用的实体
	trade;//交易
	member;//会员
	location;//收货地址信息
	couponCode;//优惠券的券码 
	logistis;//物流信息实体
	orderItems;//关联子订单（每个产品）
	// 一下是状态值的显示值
	private String sourceName;
	private String statusName;
	private String od_typeName;
	
	location:收货地址信息
	id;//主键
	acceptor_name;//收货人姓名
	phone;//收货人电话
	province;//省
	city;//市
	area;//区
	detail;//详细地址
	post_code;//邮编
	province_code;
	totalAddr;// 完成显示地址
	
	orderItems:自订单信息，链接商品拿到详情（一种商品对应一个OrderItem实体）
	id;//主键
	order_no;//父订单号
	product_id;//产品sku id
	price;//价格
	discount_fee;//折扣价格
	number;//购买的数量
	status;//状态
	comment_times;// 评论次数
	remark;//备注
	create_time;
	update_time;
	oiRtId;//退款表id
	oiRefundState;//退款状态
	oiRefundStateText;//退款状态文本
	// 一下字段非持久化
	productSKU;//商品sku实体
	
	productSKU:商品sku实体
    psId;
    psCreateTime;//创建时间
    psUpdateTime;//修改时间
    psCode;//系统编码
    psCustomCode;//自定义编码
    psProductId;//所属产品id
    psOriginalPrice;//原价
    psPrice;//现价
    psNumber;//库存
    psEnableNum;//可用库存
    psLockNum;//锁定数量
    psIsUsed;//是否使用，1表示还在使用，0表示删除
    psPropVids;//sku属性的值的id串，逗号隔开
    psVirtualNumber;//虚拟销售数量
    psSalesVolumes;//实际销售数量
    product;//引用的实体，未持久化
    productProps;//商品属性实体
    // 直接合并显示属性的名和属性值 例如： "颜色：白，尺寸：42"  又如："尺寸:13.3寸"
    // 主要在于直接显示sku的关键属性的名字和值
    propsNameAndValues;
    
    productProps:sku属性实体
    ppId;
    ppCreateTime;//创建时间
    ppUpdateTime;//修改时间
    ppName;//属性名
    ppFormStyle;//属性呈现时的表单方式,radio单选
    ppIsDelete;//是否删除，1为是，表示删除，0没有删除
    ppIsKey;//是否为关键属性，即是否是影响库存和价格的属性
    ppUseAsFilter;//是否作为筛选条件
    ppShId;//商家id,属于哪个商家
	ppvIdIn;//传入多个属性值id查询
    ppCategoryId;//商品分类id
    propValues;//属性值实体
    
    propValues:属性值实体
    ppvId;//主键
    ppvCreateTime;//创建时间
    ppvUpdateTime;//修改时间
    ppvPpId;//属性名的id
    ppvValue;//属性值
    ppvIsDelete;//是否删除，1为是，表示删除，0没有删除
    ppvShId;//商家id,属于哪个商家，0表示系统的
    
    product:引用的实体，未持久化
    pdId;//主键
    pdCreateTime;//创建时间
    pdUpdateTime;//修改时间
    pdShId;//商家id,属于哪个商家
    pdCode;//系统生成的编码
    pdCustomCode;//自定义编码
    pdShortname;//短名称
    pdLongname;//长名称
    pdMainImg;//主图地址
    pdGalleryImg;//画廊图片列表，用，隔开
    pdOnline;//上下架（1表示上架，0表示下架）
    pdOnlineTime;//上架时间
    pdOfflineTime;//下架时间
    pdCategoryId;//商品分类的id
    pdDescription;//商品简单描述
    pdDetail;//商品详情
    pdPropVids;//商品的基本属性值id串,用逗号隔开
    pdOriginalPrice;//原价
    pdPrice;//现价
    pdFtId;//运费模板
    pdFtName;//运费模板名称
    pdWeight;//商品重量
    pdVolume;//商品体积
    pdLabelVids;//标签值id串,用逗号隔开
    pdIsDelete;//是否删除，使用的是逻辑删除，0表示没有删除，1表示删除
    pdNumber;//库存
    pdEnableNum;//可用库存
    pdLockNum;//锁定数量
    pdSalesVolumes;//销售数量
    pdVirtualNumber;//虚拟销售数量
    pdIsNew;//是否是新品
    pdIsHot;//是否是热卖
    pdCommentNum;//评论数
    productSkus;//商品sku
    props;//商品属性
    skuProps;//商品sku属性
    prop;//商品属性
    productCategory;//商品分类
    freightPrice;//商品运费
    categoryNode;//根据传入的分类id查询当前分类及之下的分类
    skuId;//sku库存id
    pdCodes;//商品codes
    
> **返回结果:**

	{
	    "data": {
	        "orderBy": null,
	        "descOrAsc": null,
	        "idIn": null,
	        "currentDoSearchUser": null,
	        "page": null,
	        "trId": 3,
	        "trCreateTime": 1457681789000,
	        "trMemberId": 1,
	        "trType": null,
	        "trOrderNo": "1000001002016030941",
	        "trProductId": 8,
	        "trSkuId": 65,
	        "trRefundType": 1,
	        "trReason": 3,
	        "trState": null,
	        "trMoney": 400,
	        "trExplain": "dsadsa",
	        "trVoucher": null,
	        "trRefundState": 4,
	        "trRefundStateText": "退款完成",
	        "trRefundTypeText": "仅退款",
	        "trReasonText": "不想要了",
	        "refundMessageLogs": [
	            {
	                "orderBy": null,
	                "descOrAsc": null,
	                "idIn": null,
	                "currentDoSearchUser": null,
	                "page": null,
	                "rmlId": 3,
	                "rmlSponsorId": 1,
	                "rmlBuyersMemberId": 1,
	                "rmlCreateTime": 1457681789000,
	                "rmlText": "发起了仅退款 原因：不想要了，金额：400，说明：dsadsa",
	                "rmlTrId": 3,
	                "rmlTrRefundState": 3,
	                "rmlTrRefundStateText": "退款中"
	            },
	            {
	                "orderBy": null,
	                "descOrAsc": null,
	                "idIn": null,
	                "currentDoSearchUser": null,
	                "page": null,
	                "rmlId": 4,
	                "rmlSponsorId": 1,
	                "rmlBuyersMemberId": 1,
	                "rmlCreateTime": 1457687009000,
	                "rmlText": "同意退款",
	                "rmlTrId": 3,
	                "rmlTrRefundState": 4,
	                "rmlTrRefundStateText": "退款完成"
	            }
	        ],
	        "order": {
	            "orderBy": null,
	            "descOrAsc": null,
	            "idIn": null,
	            "currentDoSearchUser": null,
	            "page": null,
	            "oid": 96,
	            "order_name": "J-0001高端原汁机...",
	            "order_no": "1000001002016030941",
	            "trade_no": "100000145750594120194",
	            "total_fee": 1627,
	            "discount_fee": 0,
	            "payment": 0,
	            "member_id": 1,
	            "invalid_time": 24,
	            "source": "1",
	            "status": "1",
	            "od_type": "0",
	            "delivery_time": 72,
	            "real_delivery_time": null,
	            "location_id": 111,
	            "freight_fee": 0,
	            "leave_word": "",
	            "is_delete": "0",
	            "shop_id": 1,
	            "create_time": 1457505958000,
	            "update_time": 1457505958000,
	            "trade": null,
	            "member": {
	                "orderBy": null,
	                "descOrAsc": null,
	                "idIn": null,
	                "currentDoSearchUser": null,
	                "page": null,
	                "tmId": 1,
	                "tmMemberLoginname": "13925144303",
	                "tmMemberNickname": "火火火嚯嚯嚯",
	                "tmRealName": null,
	                "tmIdCard": null,
	                "tmMemberEmail": null,
	                "tmMemberPwd": null,
	                "tmMemberImg": null,
	                "tmSex": null,
	                "tmBirthday": null,
	                "tmMemberPhone": null,
	                "tmMemberAddress": null,
	                "tmMemberGrade": null,
	                "tmMemberType": null,
	                "tmVip": null,
	                "tmQualification": null,
	                "tmRegisterType": null,
	                "tmMemberCreatetime": null,
	                "tmMemberUpdatetime": null,
	                "tmMemberActivate": null,
	                "tmMemberSecretkey": null,
	                "tmMemberOuttime": null,
	                "tmQqOpenid": null,
	                "tmWeixinOpenid": null,
	                "tmMobileqqOpenid": null,
	                "tmWxgzhOpenid": null,
	                "tmMemberEnable": null,
	                "tmMemberIsdelete": null,
	                "designer": {
	                    "orderBy": null,
	                    "descOrAsc": null,
	                    "idIn": null,
	                    "currentDoSearchUser": null,
	                    "page": null,
	                    "tdId": null,
	                    "tdMemberId": null,
	                    "tdRealname": null,
	                    "tdIdentityCards": null,
	                    "tdAuthentication": null,
	                    "tdDesignerSorce": null,
	                    "tdDesignerGrade": null,
	                    "tdFans": null,
	                    "tdConcerned": null,
	                    "tdWorks": null,
	                    "tdWeibo": null,
	                    "tdQqGroup": null,
	                    "tdWechat": null,
	                    "tdIntroduction": null
	                },
	                "memberAccount": {
	                    "orderBy": null,
	                    "descOrAsc": null,
	                    "idIn": null,
	                    "currentDoSearchUser": null,
	                    "page": null,
	                    "tmcId": null,
	                    "tmcAccountNo": null,
	                    "tmcPaymentPwd": null,
	                    "tmcBalance": null,
	                    "tmcMemberId": null,
	                    "tmcEnableScore": null,
	                    "tmcMemberScore": null,
	                    "tmcCreatetime": null,
	                    "tmcUpdatetime": null
	                },
	                "tokenVo": null
	            },
	            "location": {
	                "orderBy": null,
	                "descOrAsc": null,
	                "idIn": null,
	                "currentDoSearchUser": null,
	                "page": null,
	                "id": 111,
	                "acceptor_name": "王焱",
	                "phone": "13925144303",
	                "province": "广东省",
	                "city": "广州市",
	                "area": "白云区",
	                "detail": "保利克洛维",
	                "post_code": null,
	                "province_code": null,
	                "totalAddr": "广东省广州市白云区保利克洛维"
	            },
	            "couponCode": null,
	            "logistis": null,
	            "orderWay": null,
	            "ltRealDeliveryTime": null,
	            "ltCreateTime": null,
	            "gtCreateTime": null,
	            "sourceName": "web APP",
	            "statusName": "待发货",
	            "od_typeName": "实物商品",
	            "orderItems": [
	                {
	                    "orderBy": null,
	                    "descOrAsc": null,
	                    "idIn": null,
	                    "currentDoSearchUser": null,
	                    "page": null,
	                    "id": 108,
	                    "order_no": "1000001002016030941",
	                    "product_id": 65,
	                    "price": 599,
	                    "discount_fee": 0,
	                    "number": 1,
	                    "status": "0",
	                    "comment_times": null,
	                    "remark": null,
	                    "create_time": 1457505959000,
	                    "update_time": 1457681809000,
                    	"oiRtId": 3,
	                    "oiRefundState": 3,
	                    "oiRefundStateText": "退款中",
	                    "order": null,
	                    "productSKU": {
	                        "orderBy": null,
	                        "descOrAsc": null,
	                        "idIn": null,
	                        "currentDoSearchUser": null,
	                        "page": null,
	                        "psId": 65,
	                        "psCreateTime": 1453704947000,
	                        "psUpdateTime": 1457686332000,
	                        "psCode": null,
	                        "psCustomCode": "SG-JuiceMachine-0001R",
	                        "psProductId": 8,
	                        "psOriginalPrice": 1499,
	                        "psPrice": 599,
	                        "psNumber": 100,
	                        "psEnableNum": 84,
	                        "psLockNum": 16,
	                        "psIsUsed": 1,
	                        "psPropVids": "22,23,25",
	                        "psVirtualNumber": 450,
	                        "psSalesVolumes": 0,
	                        "product": {
	                            "orderBy": null,
	                            "descOrAsc": null,
	                            "idIn": null,
	                            "currentDoSearchUser": null,
	                            "page": null,
	                            "pdId": null,
	                            "pdCreateTime": null,
	                            "pdUpdateTime": null,
	                            "pdShId": 1,
	                            "pdCode": null,
	                            "pdCustomCode": null,
	                            "pdShortname": "J-0001高端原汁机",
	                            "pdLongname": null,
	                            "pdMainImg": "/product/null/1453949601772.jpg",
	                            "pdGalleryImg": null,
	                            "pdOnline": null,
	                            "pdOnlineTime": null,
	                            "pdOfflineTime": null,
	                            "pdCategoryId": null,
	                            "pdDescription": null,
	                            "pdDetail": null,
	                            "pdPropVids": null,
	                            "pdOriginalPrice": null,
	                            "pdPrice": null,
	                            "pdFtId": null,
	                            "pdFtName": null,
	                            "pdWeight": null,
	                            "pdVolume": null,
	                            "pdLabelVids": null,
	                            "pdIsDelete": null,
	                            "pdNumber": null,
	                            "pdEnableNum": null,
	                            "pdLockNum": null,
	                            "pdSalesVolumes": null,
	                            "pdVirtualNumber": null,
	                            "pdIsNew": null,
	                            "pdIsHot": null,
	                            "pdCommentNum": null,
	                            "productSkus": null,
	                            "props": null,
	                            "skuProps": null,
	                            "prop": null,
	                            "productCategory": null,
	                            "freightPrice": null,
	                            "sortCondition": "comprehensive",
	                            "categoryNode": null,
	                            "skuId": null
	                        },
	                        "productProps": [
	                            {
	                                "orderBy": null,
	                                "descOrAsc": null,
	                                "idIn": null,
	                                "currentDoSearchUser": null,
	                                "page": null,
	                                "ppId": 38,
	                                "ppCreateTime": 1452753222000,
	                                "ppUpdateTime": null,
	                                "ppName": "果肉渣滓盒容量",
	                                "ppFormStyle": "radio",
	                                "ppIsDelete": 0,
	                                "ppIsKey": 1,
	                                "ppUseAsFilter": 1,
	                                "ppShId": 1,
	                                "ppvIdIn": null,
	                                "ppCategoryId": 24,
	                                "propValues": [
	                                    {
	                                        "orderBy": null,
	                                        "descOrAsc": null,
	                                        "idIn": null,
	                                        "currentDoSearchUser": null,
	                                        "page": null,
	                                        "ppvId": 22,
	                                        "ppvCreateTime": 1452753222000,
	                                        "ppvUpdateTime": null,
	                                        "ppvPpId": 38,
	                                        "ppvValue": "500ml以下（含500ml）",
	                                        "ppvIsDelete": 0,
	                                        "ppvShId": 1
	                                    }
	                                ]
	                            },
	                            {
	                                "orderBy": null,
	                                "descOrAsc": null,
	                                "idIn": null,
	                                "currentDoSearchUser": null,
	                                "page": null,
	                                "ppId": 39,
	                                "ppCreateTime": 1452753255000,
	                                "ppUpdateTime": 1456125573000,
	                                "ppName": "榨汁机附加功能",
	                                "ppFormStyle": "radio",
	                                "ppIsDelete": 0,
	                                "ppIsKey": 1,
	                                "ppUseAsFilter": 0,
	                                "ppShId": 1,
	                                "ppvIdIn": null,
	                                "ppCategoryId": 24,
	                                "propValues": [
	                                    {
	                                        "orderBy": null,
	                                        "descOrAsc": null,
	                                        "idIn": null,
	                                        "currentDoSearchUser": null,
	                                        "page": null,
	                                        "ppvId": 23,
	                                        "ppvCreateTime": 1452753255000,
	                                        "ppvUpdateTime": null,
	                                        "ppvPpId": 39,
	                                        "ppvValue": "豆腐 冰淇淋 婴儿辅食 制奶昔 榨汁",
	                                        "ppvIsDelete": 0,
	                                        "ppvShId": 1
	                                    }
	                                ]
	                            },
	                            {
	                                "orderBy": null,
	                                "descOrAsc": null,
	                                "idIn": null,
	                                "currentDoSearchUser": null,
	                                "page": null,
	                                "ppId": 43,
	                                "ppCreateTime": 1452753509000,
	                                "ppUpdateTime": 1456124622000,
	                                "ppName": "功率",
	                                "ppFormStyle": "radio",
	                                "ppIsDelete": 0,
	                                "ppIsKey": 1,
	                                "ppUseAsFilter": 1,
	                                "ppShId": 1,
	                                "ppvIdIn": null,
	                                "ppCategoryId": 24,
	                                "propValues": [
	                                    {
	                                        "orderBy": null,
	                                        "descOrAsc": null,
	                                        "idIn": null,
	                                        "currentDoSearchUser": null,
	                                        "page": null,
	                                        "ppvId": 25,
	                                        "ppvCreateTime": 1452753509000,
	                                        "ppvUpdateTime": null,
	                                        "ppvPpId": 43,
	                                        "ppvValue": "200w及以下",
	                                        "ppvIsDelete": 0,
	                                        "ppvShId": 1
	                                    }
	                                ]
	                            }
	                        ],
	                        "propsNameAndValues": "果肉渣滓盒容量:500ml以下（含500ml） ， 榨汁机附加功能:豆腐 冰淇淋 婴儿辅食 制奶昔 榨汁 ， 功率:200w及以下 ， "
	                    },
	                    "freightInfo": null
	                }
	            ]
	        }
	    },
	    "code": "200",
	    "msg": "操作成功"
	}



###5添加快递单号

> **请求url：**http://192.168.1.168/sigoods/mobile/member/custservice/refund/addShipWayAndNo

> **请求方式：**get/post

> **参数：** <br/>
trId : 申请退款单ID  Long <br/>
shipWay : 快递方式(快递ID)  Integer <br/>
shipNo :  快递单号  String <br/>


> **返回结果:**

	{
	    "data": null,
	    "code": "200",
	    "msg": "操作成功"
	}

	{
	    "data": null,
	    "code": "201",
	    "msg": "操作失败"
	}

	{
	    "data": null,
	    "code": "300",
	    "msg": "程序异常"
	}


###6查询退款日志(协商退款)

> **请求url：**http://localhost:8081/sigoods/mobile/member/custservice/refund/refundMessageGet

> **请求方式：**get/post

> **参数：** <br/>
trId : 申请退款单ID  Long <br/>


> **返回结果:**

	成功:
			{
			  "data": {
			    "refundLog": [    -----------------退款日志集合
			      {
			        "rmlId": 199,
			        "rmlSponsorId": 289,
			        "rmlBuyersMemberId": 289,
			        "rmlCreateTime": 1468833304000,               -------------时间
			        "rmlText": "发起了仅退款 原因：用户取消(未发货)订单，金额：0，说明：用户取消(未发货)订单",  ------------ 信息(对话框)
			        "rmlTrId": 107,
			        "rmlTrRefundState": 3,                ------------ 退货状态
			        "rmlTrRefundStateText": "退款中",
			        "sellerOrBuyer": 0,					  -------------区分买家:0/卖家:1		
			        "orderBy": null,
			        "descOrAsc": null
			      }
			    ],
			    "refund": {      ------------------退款单信息
			      "trId": 107,
			      "trCreateTime": 1468833304000,
			      "trMemberId": 289,
			      "trType": null,
			      "trOrderNo": "2890001001607181440",
			      "trProductId": 5,
			      "trSkuId": 62,
			      "trRefundType": 1,					-----------退款类型
			      "trReason": 12,
			      "trState": null,
			      "trMoney": 0,
			      "trExplain": "用户取消(未发货)订单",
			      "trVoucher": null,
			      "trRefundState": 7,
			      "trPaymentType": 4,
			      "trNo": null,
			      "shipWay": null,
			      "shipNo": null,
			      "dealTime": null,
			      "notifyTime": null,
			      "trUpdateTime": 1468833304000,
			      "gtCreateTime": null,
			      "ltCreateTime": null,
			      "selOrderNo": null,
			      "trRefundStateText": "支付宝受理",
			      "trRefundTypeText": "仅退款",
			      "trReasonText": "用户取消(未发货)订单",
			      "refundMessageLogs": null,
			      "order": null,
			      "page": null,
			      "orderBy": null,
			      "descOrAsc": null
			    }
			  },
			  "code": "200",
			  "msg": "操作成功"
			}
				
	
	失败:
	{
	    "data": null,
	    "code": "300",
	    "msg": "程序异常"
	}


###7查询钱款去向

> **请求url：**http://localhost:8081/sigoods/mobile/member/custservice/refund/moneyFlowGet

> **请求方式：**get/post

> **参数：** <br/>
flag : 标识    (取消订单:0,申请退款:1) int<br/>
orderNo : 订单号 (flag = 0 时必须)  String <br/>
trId : 申请退款单ID (flag = 1 时必须)  Long <br/>



> **返回结果:**

	成功:
			{
			  "data": {
			    "deal": 1468377487000,    --------受理时间
			    "notify": 1468377487000,  --------完成时间
			    "payWay": 4,			  --------付款类型(4:支付宝,1微信)	
			    "currentType": "notify",  --------当前状态(1.申请:create,2.受理:deal,3.完成:notify)
			    "create": 1468377487000,  --------申请时间
			    "totleFee": 100		 	  --------退款金额
			  },
			  "code": "200",
			  "msg": "操作成功"
			}
	
	
	失败:
			{
			    "data": null,
			    "code": code,            --------异常code
			    "msg" :  msg             --------异常信息
			}

			例:
				{
				  "data": null,
				  "code": "300",
				  "msg": "程序异常"
				}


				{
				  "data": null,
				  "code": "305",
				  "msg": "当前订单不属于该用户"
				}



###8用户主动取消退款/退货

> **请求url：**http://localhost:8081/sigoods/mobile/member/custservice/refund/memberCancleRefund

> **请求方式：**get/post

> **参数：** <br/>
trId : 申请退款单ID   Long <br/>

> **返回结果:**

	成功:
			{
			  "data": null,
			  "code": "200",
			  "msg": "操作成功"
			}
	
	
	失败:
			{
			    "data": null,
			    "code": code,            --------异常code
			    "msg" :  msg             --------异常信息
			}

			例:
				{
				  "data": null,
				  "code": "300",
				  "msg": "程序异常"
				}


				{
				  "data": null,
				  "code": "305",
				  "msg": "当前订单不属于该用户"
				}