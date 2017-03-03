# 首页接口

###1首页配置信息接口

> **请求url：**http://192.168.1.168/shiwu/web/pageconfig/mobile_index

> **请求方式：**get

> **接口说明：** <br/>

> **接口改动：** <br/>
	
	新增：
		adrLinesRecords：按照行号来分组默认为"null"，分组内的子元素和advertisementRecords内的一致
	
> **参数：** <br/>

	无 <br/>

> **返回结果:**

	{
    "advertisements": [
        {
            "adCode": "index_slide",
            "adCopiesTitle": "",
            "adCreateTime": 1452492562000,
            "adId": 1,
            "adRemarks": "图片大小 640*400",
            "adSort": 0,
            "adState": 1,
            "adTitle": "首页幻灯片",
            "adType": 1,
            "adUpdateTime": 1453974301000,
            "adUserId": 1,
            "adrLinesRecords": {
                "1": [
                    {
                        "adrAdId": 1,
                        "adrBgColor": "",
                        "adrCode": "llj",
                        "adrCreateTime": 1470044073000,
                        "adrDescribe": "web料理机",
                        "adrId": 74,
                        "adrImg": "/ad/1470044066925.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 1,
                        "adrLink": "P14536930408557177",
                        "adrLinkType": 3,
                        "adrOriginalPrice": 0,
                        "adrOriglPriceInt": 0,
                        "adrPrice": 0,
                        "adrPriceInt": 0,
                        "adrSort": 1,
                        "adrState": 1,
                        "adrSubtitle": "这是料理机",
                        "adrTitle": "料理机",
                        "adrUpdateTime": 1470381581000,
                        "adrUserId": 1,
                        "prodCommemtNums": 1010
                    }
                ],
                "null": [
                    {
                        "adrAdId": 1,
                        "adrBgColor": "",
                        "adrCode": "duoshilu",
                        "adrCreateTime": 1452493676000,
                        "adrDescribe": "web幻灯多士炉",
                        "adrId": 2,
                        "adrImg": "/ad/1470381533076.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLink": "P14536923627706448",
                        "adrLinkType": 3,
                        "adrOriginalPrice": 0,
                        "adrOriglPriceInt": 0,
                        "adrPrice": 0,
                        "adrPriceInt": 0,
                        "adrState": 1,
                        "adrSubtitle": "3分钟自动弹出",
                        "adrTitle": "多士炉",
                        "adrUpdateTime": 1470382985000,
                        "adrUserId": 1,
                        "prodCommemtNums": 70
                    }
                ]
            }
        },
        {
            "adCode": "mobile_white_collar_kitchen",
            "adCopiesTitle": "白领厨房",
            "adCreateTime": 1459336193000,
            "adId": 20,
            "adRemarks": "白领厨房",
            "adSort": 5,
            "adState": 1,
            "adTitle": "手机端白领厨房",
            "adType": 1,
            "adUpdateTime": 1466128703000,
            "adUserId": 1,
            "adrLinesRecords": {
                "1": [
                    {
                        "adrAdId": 20,
                        "adrBgColor": "",
                        "adrCode": "blcf",
                        "adrCreateTime": 1459336482000,
                        "adrDescribe": "",
                        "adrId": 50,
                        "adrImg": "/ad/1459336437139.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 1,
                        "adrLink": "19",
                        "adrLinkType": 2,
                        "adrSort": 1,
                        "adrState": 1,
                        "adrSubtitle": "",
                        "adrTitle": "aaaaaaaaaaaaaa",
                        "adrUpdateTime": 1461575073000,
                        "adrUserId": 1
                    }
                ],
                "2": [
                    {
                        "adrAdId": 20,
                        "adrBgColor": "",
                        "adrCode": "blcf",
                        "adrCreateTime": 1459336507000,
                        "adrDescribe": "产品2",
                        "adrId": 51,
                        "adrImg": "/ad/1459336501818.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 2,
                        "adrLink": "23",
                        "adrLinkType": 2,
                        "adrSort": 2,
                        "adrState": 1,
                        "adrSubtitle": "",
                        "adrTitle": "",
                        "adrUpdateTime": 1461575106000,
                        "adrUserId": 1
                    },
                    {
                        "adrAdId": 20,
                        "adrBgColor": "",
                        "adrCode": "blcf",
                        "adrCreateTime": 1459336534000,
                        "adrDescribe": "多士炉",
                        "adrId": 52,
                        "adrImg": "/ad/1459336518873.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 2,
                        "adrLink": "20",
                        "adrLinkType": 2,
                        "adrSort": 3,
                        "adrState": 1,
                        "adrSubtitle": "",
                        "adrTitle": "",
                        "adrUpdateTime": 1466145023000,
                        "adrUserId": 1
                    }
                ],
                "3": [
                    {
                        "adrAdId": 20,
                        "adrBgColor": "",
                        "adrCode": "blcf",
                        "adrCreateTime": 1459336577000,
                        "adrDescribe": "简易料理机",
                        "adrId": 53,
                        "adrImg": "/ad/1459336567037.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 3,
                        "adrLink": "21",
                        "adrLinkType": 2,
                        "adrSort": 4,
                        "adrState": 1,
                        "adrSubtitle": "",
                        "adrTitle": "",
                        "adrUpdateTime": 1466144245000,
                        "adrUserId": 1
                    },
                    {
                        "adrAdId": 20,
                        "adrBgColor": "",
                        "adrCode": "blcf",
                        "adrCreateTime": 1459336671000,
                        "adrDescribe": "料理配件",
                        "adrId": 56,
                        "adrImg": "/ad/1459336669170.png",
                        "adrIsHot": false,
                        "adrIsNew": false,
                        "adrLines": 3,
                        "adrLink": "19",
                        "adrLinkType": 2,
                        "adrSort": 7,
                        "adrState": 1,
                        "adrSubtitle": "",
                        "adrTitle": "",
                        "adrUpdateTime": 1466144217000,
                        "adrUserId": 1
                    }
                ]
            }
        },
        {
            "adCode": "web_hot_recommendation",
            "adCopiesTitle": "热卖推荐",
            "adCreateTime": 1470190276000,
            "adId": 36,
            "adRemarks": "PC端热卖推荐",
            "adSort": 1,
            "adState": 1,
            "adTitle": "Web端热卖推荐（勿删）",
            "adType": 1,
            "adUpdateTime": 1470210259000,
            "adUserId": 1,
            "adrLinesRecords":[
                    {
                        "adrAdId": 36,
                        "adrBgColor": "",
                        "adrCode": "rmtj",
                        "adrCreateTime": 1470199589000,
                        "adrDescribe": "原汁机",
                        "adrId": 79,
                        "adrImg": "/ad/1470199557294.jpg",
                        "adrIsHot": true,
                        "adrIsNew": false,
                        "adrLines": 1,
                        "adrLink": "P14537048766847503",
                        "adrLinkType": 3,
                        "adrOriginalPrice": 123,
                        "adrOriglPriceInt": 12300,
                        "adrPrice": 81.3,
                        "adrPriceInt": 8130,
                        "adrSort": 1,
                        "adrState": 1,
                        "adrSubtitle": "出汁又多又快",
                        "adrTitle": "原汁机",
                        "adrUpdateTime": 1470383417000,
                        "adrUserId": 1,
                        "prodCommemtNums": 46
                    },
                    {
                        "adrAdId": 36,
                        "adrBgColor": "",
                        "adrCode": "rmtj",
                        "adrCreateTime": 1470190996000,
                        "adrDescribe": "料理机",
                        "adrId": 76,
                        "adrImg": "/ad/1470190970766.png",
                        "adrIsHot": true,
                        "adrIsNew": false,
                        "adrLines": 1,
                        "adrLink": "P14536930408557177",
                        "adrLinkType": 3,
                        "adrOriginalPrice": 80,
                        "adrOriglPriceInt": 8000,
                        "adrPrice": 78,
                        "adrPriceInt": 7800,
                        "adrSort": 1,
                        "adrState": 1,
                        "adrSubtitle": "双刃多功能",
                        "adrTitle": "料理机",
                        "adrUpdateTime": 1470383308000,
                        "adrUserId": 1,
                        "prodCommemtNums": 1010
                    }
                ]         
        }
    ],
    "plcAdIds": "1,20,36",
    "plcCode": "web_index_config",
    "plcCreateTime": 1470210162000,
    "plcId": 13,
    "plcRemarks": "Web端首页配置",
    "plcState": 1,
    "plcTitle": "Web端首页配置（勿删）",
    "plcUpdateTime": 1470210219000,
    "plcUserId": 1
	}
	


###2查询页面标签（商品列表分类）

> **请求url：**http://192.168.1.168/sigoods/web/cat

> **请求方式：**get

> **接口说明：**get
	
	目前标签类型有6种：lrType
		1:页面配置
		2:商品分类
		3:商品选择
		4:标签
		5:最新商品，调用查询商品接口，查询机最新商品
		6:热卖商品，调用查询商品接口，查询热卖商品
	
> **参数：** <br/>

> **参数说明：** <br/>

	输出参数：
	{
	data:数据主体
	code:200数据返回正常
	msg:数据返回描述
	
	tlId;//主键
    tlCreateTime;//创建时间
    tlUserId;//创建人
    tlUpdateTime;//修改时间
    tlTitle;//标题
    tlCode;//当前代码
    tlRemarks;//备注
    tlCopiesTitle;//文案标题
    tlState;//标签状态，1正常使用，0删除
    tlSort;//排序
    labelRecords;//标签信息记录
    
    labelRecords[]:标签记录
    lrId;//主键
    lrCreateTime;//创建时间
    lrUpdateTime;//修改时间
    lrUserId;//创建人
    lrTitle;//标题
    lrDescribe;//描述
    lrType;//标签类型
    lrPkId;//外键id，配合lr_type使用
    lrImg;//展示图片
    lrImgSelected;//选中后的展示图片
    lrState;//记录状态，1正常使用，0删除
    lrTlId;//标签主体id
    lrBgColor;//背景颜色
    lrSort;//排序
    lrProductIds;//商品ids，集合
    lrCode;//当前代码
    products;//商品主体，商品内容实体
    lrTypeText;//类型文本
    lrPkText;//外键文本
    
    categories[]:
    pcId;
	pcCreateTime;//创建时间
	pcUpdateTime;//修改时间
	pcName;//分类名称
	pcParentId;//上级分类的id
	pcIsDelete;//是否删除，使用的是逻辑删除，1表示删除，0表示没删除
	pcCode;//分类编码
	pcShId;//商家id,属于哪个商家，0表示系统的
	pcIcon;//分类图标
	pcSort;//排序  
	}
	
> **返回结果:**

     {
     "code": "200",
     "msg": "WEB查询商品分类列表成功",
    "data": {
        "labelRecords": [
            {
                "categories": [
                    {
                        "childrens": [],
                        "pcCode": "16,19,24",
                        "pcCreateTime": 1452509214000,
                        "pcIcon": "/category/1452509205431.png",
                        "pcId": 24,
                        "pcIsDelete": 0,
                        "pcName": "原汁机",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 1,
                        "pcUpdateTime": 1454318189000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,19,23",
                        "pcCreateTime": 1452509200000,
                        "pcIcon": "/category/1452509199506.png",
                        "pcId": 23,
                        "pcIsDelete": 0,
                        "pcName": "绞肉机",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 2,
                        "pcUpdateTime": 1454318195000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,19,22",
                        "pcCreateTime": 1452509183000,
                        "pcIcon": "/category/1452509181844.png",
                        "pcId": 22,
                        "pcIsDelete": 0,
                        "pcName": "面条机",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 3,
                        "pcUpdateTime": 1454318201000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,19,21",
                        "pcCreateTime": 1452509169000,
                        "pcIcon": "/category/1452509167789.jpg",
                        "pcId": 21,
                        "pcIsDelete": 0,
                        "pcName": "简易料理机",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 4,
                        "pcUpdateTime": 1458628726000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,19,20",
                        "pcCreateTime": 1452509147000,
                        "pcIcon": "/category/1452509145934.png",
                        "pcId": 20,
                        "pcIsDelete": 0,
                        "pcName": "多士炉",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 5,
                        "pcUpdateTime": 1454318215000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,19,55",
                        "pcCreateTime": 1454313786000,
                        "pcIcon": "/category/1454384041188.jpg",
                        "pcId": 55,
                        "pcIsDelete": 0,
                        "pcName": "冷柜",
                        "pcParentId": 19,
                        "pcShId": 0,
                        "pcSort": 6,
                        "pcUpdateTime": 1454384045000
                    }
                ],
                "lrCode": "blcf",
                "lrCreateTime": 1471939937000,
                "lrDescribe": "白领厨房",
                "lrId": 41,
                "lrImg": "/label/1459404127353.png",
                "lrImgSelected": "/label/1466668539122.png",
                "lrPkId": 19,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "白领厨房",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940098000,
                "lrUserId": 1
            },
            {
                "categories": [],
                "lrCode": "rcjw",
                "lrCreateTime": 1471940228000,
                "lrDescribe": "日常家务",
                "lrId": 42,
                "lrImg": "/label/1471940215036.png",
                "lrImgSelected": "/label/1471940219686.png",
                "lrPkId": 2,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "日常家务",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940627000,
                "lrUserId": 1
            },
            {
                "categories": [
                    {
                        "childrens": [],
                        "pcCode": "16,17,62",
                        "pcCreateTime": 1454492723000,
                        "pcIcon": "/category/1454492713586.jpg",
                        "pcId": 62,
                        "pcIsDelete": 0,
                        "pcName": "干衣机",
                        "pcParentId": 17,
                        "pcShId": 0,
                        "pcUpdateTime": 1464677138000
                    },
                    {
                        "childrens": [],
                        "pcCode": "16,17,63",
                        "pcCreateTime": 1454493106000,
                        "pcIcon": "/category/1454493104803.jpg",
                        "pcId": 63,
                        "pcIsDelete": 0,
                        "pcName": "加湿器",
                        "pcParentId": 17,
                        "pcShId": 0,
                        "pcSort": 2,
                        "pcUpdateTime": 1464677138000
                    }
                ],
                "lrCode": "qjhl",
                "lrCreateTime": 1471940513000,
                "lrDescribe": "清洁护理",
                "lrId": 43,
                "lrImg": "/label/1471940501927.png",
                "lrImgSelected": "/label/1471940505432.png",
                "lrPkId": 17,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "清洁护理",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940513000,
                "lrUserId": 1
            },
            {
                "categories": [
                    {
                        "childrens": [],
                        "pcCode": "14,15,60",
                        "pcCreateTime": 1454386223000,
                        "pcIcon": "/category/1454386378813.jpg",
                        "pcId": 60,
                        "pcIsDelete": 0,
                        "pcName": "碎料器",
                        "pcParentId": 15,
                        "pcShId": 0,
                        "pcUpdateTime": 1454386381000
                    },
                    {
                        "childrens": [],
                        "pcCode": "14,15,56",
                        "pcCreateTime": 1454316086000,
                        "pcIcon": "/category/1454317358175.jpg",
                        "pcId": 56,
                        "pcIsDelete": 0,
                        "pcName": "切菜器",
                        "pcParentId": 15,
                        "pcShId": 0,
                        "pcSort": 1,
                        "pcUpdateTime": 1454318309000
                    },
                    {
                        "childrens": [],
                        "pcCode": "14,15,57",
                        "pcCreateTime": 1454319380000,
                        "pcIcon": "/category/1454319378082.png",
                        "pcId": 57,
                        "pcIsDelete": 0,
                        "pcName": "情侣杯",
                        "pcParentId": 15,
                        "pcShId": 0,
                        "pcSort": 2,
                        "pcUpdateTime": 1464677138000
                    }
                ],
                "lrCode": "jjyp",
                "lrCreateTime": 1471940557000,
                "lrDescribe": "家居用品",
                "lrId": 44,
                "lrImg": "/label/1471940545531.png",
                "lrImgSelected": "/label/1471940549299.png",
                "lrPkId": 15,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "家居用品",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940557000,
                "lrUserId": 1
            },
            {
                "categories": [
                    {
                        "childrens": [],
                        "pcCode": "11,12,64",
                        "pcCreateTime": 1454493707000,
                        "pcIcon": "/category/1454493704321.jpg",
                        "pcId": 64,
                        "pcIsDelete": 0,
                        "pcName": "手机特效镜头",
                        "pcParentId": 66,
                        "pcShId": 0,
                        "pcUpdateTime": 1454506493000
                    },
                    {
                        "childrens": [],
                        "pcCode": "11,12,65",
                        "pcCreateTime": 1454495485000,
                        "pcIcon": "/category/1454495482208.jpg",
                        "pcId": 65,
                        "pcIsDelete": 0,
                        "pcName": "移动电源",
                        "pcParentId": 66,
                        "pcShId": 0,
                        "pcUpdateTime": 1454513874000
                    }
                ],
                "lrCode": "sssm",
                "lrCreateTime": 1471940605000,
                "lrDescribe": "随身数码",
                "lrId": 45,
                "lrImg": "/label/1471940593559.png",
                "lrImgSelected": "/label/1471940595908.png",
                "lrPkId": 66,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "随身数码",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940604000,
                "lrUserId": 1
            },
            {
                "categories": [],
                "lrCode": "znsm",
                "lrCreateTime": 1471940858000,
                "lrDescribe": "",
                "lrId": 46,
                "lrImg": "/label/1471940849133.png",
                "lrImgSelected": "/label/1471940853411.png",
                "lrPkId": 13,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "智能数码",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940857000,
                "lrUserId": 1
            },
            {
                "categories": [
                    {
                        "childrens": [],
                        "pcCode": "9,77",
                        "pcCreateTime": 1465699232000,
                        "pcIcon": "",
                        "pcId": 77,
                        "pcIsDelete": 0,
                        "pcName": "测试验证",
                        "pcParentId": 9,
                        "pcShId": 0,
                        "pcSort": 4,
                        "pcUpdateTime": 1465959544000
                    },
                    {
                        "childrens": [],
                        "pcCode": "9,10",
                        "pcCreateTime": 1452508303000,
                        "pcIcon": "",
                        "pcId": 10,
                        "pcIsDelete": 0,
                        "pcName": "春季产品",
                        "pcParentId": 9,
                        "pcShId": 0,
                        "pcSort": 10,
                        "pcUpdateTime": 1456218251000
                    }
                ],
                "lrCode": "jjcp",
                "lrCreateTime": 1471940966000,
                "lrDescribe": "季节产品",
                "lrId": 47,
                "lrImg": "/label/1471940955030.png",
                "lrImgSelected": "/label/1471940958040.png",
                "lrPkId": 9,
                "lrProductIds": "",
                "lrState": 1,
                "lrTitle": "j季节产品",
                "lrTlId": 29,
                "lrType": "2",
                "lrTypeText": "商品分类",
                "lrUpdateTime": 1471940965000,
                "lrUserId": 1
            }
        ],
        "tlCode": "web_product_ctg",
        "tlCopiesTitle": "分类配置",
        "tlCreateTime": 1471939820000,
        "tlId": 29,
        "tlRemarks": "web端标签商品分类配置",
        "tlState": 1,
        "tlTitle": "web端标签商品分类列表配置(不能删除)",
        "tlUpdateTime": 1471940969000,
        "tlUserId": 1
        }
    }
	
###3查询商品推荐

> **请求url：**http://192.168.1.168/sigoods/web/pageconfig/{code}

> **请求方式：**get

> **接口说明：**get

> **参数：** <br/>
code：web_recom <br />

> **参数说明：** <br/>

     输出参数：
    "isSuccess": true,//是否返回数据成功
    "errorCode": null,//不成功有错误编码
    "message": null,// 错误信息
    "data": {} // 数据实体
    
    plcId;//主键
	plcCreateTime;//创建时间
	plcUserId;//创建人
	plcUpdateTime;//修改时间
	plcTitle;//标题
	plcCode;//当前配置代码
	plcRemarks;//备注
	plcAdIds;//广告ids
	plcState;//状态，1正常使用，0删除
	
	advertisements:[]
	 adCreateTime;//创建时间
	adUserId;//创建人
	adUpdateTime;//修改时间
	adTitle;//标题
	adCode;//当前广告代码
	adType;//广告展示类型
	adRemarks;//备注
	adCopiesTitle;//文案标题
	adState;//广告状，1正常使用，0删除
	adSort;//排序
	
	advertisementRecords:[]
	adrCreateTime;//创建时间
	adrUpdateTime;//修改时间
	adrUserId;//创建人
	adrTitle;//标题
	adrDescribe;//描述
	adrLinkType;//跳转链接类型，1外链，2商品分类，3商品
	adrLink;//跳转链接，也可放js方法
	adrImg;//展示图片
	adrState;//记录状态，1正常使用，0删除
	adrAdId;//广告主体id
	adrBgColor;//背景颜色
	adrIsNew;//是否是新品
	adrIsHot;//是否是热卖
	adrOriginalPrice;//原价
	adrPrice;//现价
	adrSort;//排序
	adrCode;//当前代码
	adrLines;//行数，确认当前是第几行
	adrSubtitle;//副标题


> **返回结果:**

    {
    "isSuccess": true,
    "errorCode": null,
    "message": null,
    "data": {
        "plcId": 14,
        "plcCreateTime": 1472450728000,
        "plcUserId": 1,
        "plcUpdateTime": 1472450729000,
        "plcTitle": "PC端推荐商品",
        "plcCode": "web_recom",
        "plcRemarks": "PC端商品推荐备注",
        "plcAdIds": "4",
        "plcState": 1,
        "advertisements": [
            {
                "adId": 4,
                "adCreateTime": 1452497416000,
                "adUserId": 1,
                "adUpdateTime": 1453974363000,
                "adTitle": "猜你喜欢",
                "adCode": "guess_you_like",
                "adType": 1,
                "adRemarks": "图建议尺寸250*250",
                "adCopiesTitle": "猜你喜欢",
                "adState": 1,
                "adSort": 0,
                "advertisementRecords": [
                    {
                        "adrId": 28,
                        "adrCreateTime": 1463467475000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 0,
                        "adrTitle": "碎料器",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14543799089307550",
                        "adrImg": "/ad/1467018116033.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 899,
                        "adrPrice": 139,
                        "adrOriglPriceInt": 89900,
                        "adrPriceInt": 13900,
                        "adrSort": null,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 664
                    },
                    {
                        "adrId": 18,
                        "adrCreateTime": 1452499440000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 1,
                        "adrTitle": "M2-家用不锈钢绞肉机",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14536929508719501",
                        "adrImg": "/ad/1467018299286.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": true,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 329,
                        "adrPrice": 299,
                        "adrOriglPriceInt": 32900,
                        "adrPriceInt": 29900,
                        "adrSort": 1,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 2
                    },
                    {
                        "adrId": 17,
                        "adrCreateTime": 1452498686000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 1,
                        "adrTitle": "T2-家用不锈钢多士炉",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14536923627706448",
                        "adrImg": "/ad/1467018312995.png",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": true,
                        "product": null,
                        "adrOriginalPrice": 499,
                        "adrPrice": 198,
                        "adrOriglPriceInt": 49900,
                        "adrPriceInt": 19800,
                        "adrSort": 2,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 71
                    },
                    {
                        "adrId": 16,
                        "adrCreateTime": 1452498611000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 1,
                        "adrTitle": "SG-JuiceMachine-0001R时物多功能榨汁机",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14537048766847503",
                        "adrImg": "/ad/1467018324677.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 1499,
                        "adrPrice": 599,
                        "adrOriglPriceInt": 149900,
                        "adrPriceInt": 59900,
                        "adrSort": 3,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 46
                    },
                    {
                        "adrId": 15,
                        "adrCreateTime": 1452498582000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 1,
                        "adrTitle": "家用多功能小型绞肉机",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14536930408557177",
                        "adrImg": "/ad/1467018360156.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 15900,
                        "adrPrice": 8000,
                        "adrOriglPriceInt": 1590000,
                        "adrPriceInt": 800000,
                        "adrSort": 4,
                        "adrCode": "llj",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 1010
                    },
                    {
                        "adrId": 27,
                        "adrCreateTime": 1454320153000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 6,
                        "adrTitle": "猴年情人节纪念保温杯",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14540489225682016",
                        "adrImg": "/ad/1467018371825.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 199,
                        "adrPrice": 99,
                        "adrOriglPriceInt": 19900,
                        "adrPriceInt": 9900,
                        "adrSort": 5,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 3
                    },
                    {
                        "adrId": 29,
                        "adrCreateTime": 1463553882000,
                        "adrUpdateTime": 1467271887000,
                        "adrUserId": 0,
                        "adrTitle": "家用单门节能冰柜 小体积大容量",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14543122909526626",
                        "adrImg": "/ad/1467018389766.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 788,
                        "adrPrice": 488,
                        "adrOriglPriceInt": 78800,
                        "adrPriceInt": 48800,
                        "adrSort": 6,
                        "adrCode": "mobile_recom",
                        "adrLines": null,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 0
                    },
                    {
                        "adrId": 30,
                        "adrCreateTime": 1462171501000,
                        "adrUpdateTime": 1472452034000,
                        "adrUserId": 0,
                        "adrTitle": "双门小冰箱 一级节能",
                        "adrDescribe": "",
                        "adrLinkType": 3,
                        "adrLink": "P14543803482121344",
                        "adrImg": "/ad/1467018402363.jpg",
                        "adrState": 1,
                        "adrAdId": 4,
                        "adrBgColor": "",
                        "adrIsNew": false,
                        "adrIsHot": false,
                        "product": null,
                        "adrOriginalPrice": 1088,
                        "adrPrice": 699,
                        "adrOriglPriceInt": 108800,
                        "adrPriceInt": 69900,
                        "adrSort": 7,
                        "adrCode": "mobile_recom",
                        "adrLines": 2,
                        "adrSubtitle": "",
                        "productCategory": null,
                        "prodCommemtNums": 0
                    }
                ],
                "adrLinesRecords": null,
                "page": null,
                "idIn": null,
                "orderBy": null,
                "descOrAsc": null
            }
        ],
        "page": null
    }
    }
	
	
	