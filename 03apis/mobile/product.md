# 手机移动端

###1获取商品列表

> **请求url：**http://192.168.1.168/sigoods/mobile/product/items

> **请求方式：**get

> **参数：** <br/>
showCount ：每页显示记录数 <br/>
currentPage ：当前页，主要靠这个进行分页<br/>
sortCondition ： 排序条件，默认值是comprehensive，可以结合descOrAsc进行升序降序使用、具体传入的值：<br/>
	comprehensive 综合查询，热度，新品，价格，评论查询<br/>
    host 热度，按照热度排序，目前按照销量排序<br/>
    new 新品，按照产品添加顺序排序<br/>
    price 价格，按照产品的价格排序<br/>
    comment 评论，按照评论的次数排序<br/>
descOrAsc ：asc升序、desc降序 <br/>
search ：搜索文本，按照此文本进行搜索，格式：encodeURI编码后的文本 <br/>
cat ：分类id，查询当前分类及其子分类 <br/>
pdCodes ：商品code集合串，用逗号隔开 <br/>
pdIsNew ：传入的值为1的时候，则获取新品列表 <br/>
pdIsHot ：传入的值为1的时候，则获取热卖列表 <br/>

> **返回结果:**

	[
	     {
        "pdId": 6,
        "pdCreateTime": 1453693114000,
        "pdUpdateTime": 1469001538000,
        "pdShId": 1,
        "pdCode": "P14536930408557177",
        "pdCustomCode": null,
        "pdShortname": "M-0003家用小型电动简易料理机",
        "pdLongname": null,
        "pdMainImg": "/product/null/1459408630302.jpg",
        "pdGalleryImg": "/product/null/1453968438860.png,/product/null/1453968475362.jpg,/product/null/1453968478500.jpg,/product/null/1453968480657.jpg,/product/null/1453968486246.jpg",
        "pdOnline": 1,
        "pdOnlineTime": 1453693464000,
        "pdOfflineTime": null,
        "pdCategoryId": 21,
        "pdDescription": "",
        "pdDetail": null,
        "pdPropVids": "59",
        "pdOriginalPrice": 85,
        "pdPrice": 79,
        "pdFtId": 48,
        "pdFtName": "测试用",
        "pdWeight": null,
        "pdVolume": null,
        "pdLabelVids": null,
        "pdIsDelete": 0,
        "pdNumber": 111,
        "pdEnableNum": 20,
        "pdLockNum": 88,
        "pdSalesVolumes": 3,
        "pdVirtualNumber": 2160,
        "pdIsNew": true,
        "pdIsHot": true,
        "pdCommentNum": 1012,
        "productSkus": [
            {
                "psId": 69,
                "psCreateTime": 1453948429000,
                "psUpdateTime": 1469001538000,
                "psCode": null,
                "psCustomCode": "SG-MANGLER-0003",
                "psProductId": 6,
                "psOriginalPrice": 8500,
                "psPrice": 7900,
                "psNumber": 111,
                "psEnableNum": 20,
                "psLockNum": 88,
                "psIsUsed": 1,
                "psPropVids": "",
                "psVirtualNumber": 2160,
                "psSalesVolumes": 3,
                "psCustSerTime": 7,
                "product": null,
                "productProps": null,
                "propsNameAndValues": "",
                "page": null,
                "psOrglPriceDouble": 85,
                "psPriceDouble": 79
            }
        ],
        "props": null,
        "skuProps": null,
        "prop": null,
        "productCategory": null,
        "freightPrice": null,
        "sortCondition": "comprehensive",
        "categoryNode": null,
        "skuId": null,
        "pdCodes": null,
        "page": null,
        "descOrAsc": null,
        "orderBy": null,
        "pdOrlPriceInt": 8500,
        "pdPriceInt": 7900
    }]	


###2获取商品详情

> **请求url：**http://192.168.1.168/sigoods/mobile/product/{code}

> **请求方式：**get

> **参数：** <br/>
{code} ： 商品的系统编码，替换{code} <br/>

> **返回结果:**
		
	{
    "pdId": 31,
    "pdCreateTime": 1454500093000,
    "pdUpdateTime": 1469084997000,
    "pdShId": 1,
    "pdCode": "P14544989861299658",
    "pdCustomCode": null,
    "pdShortname": "手持式吸尘器 家用静音除螨",
    "pdLongname": null,
    "pdMainImg": "/product/P14544989861299658/1459836423268.jpg",
    "pdGalleryImg": "/product/P14544989861299658/1454499225313.jpg,/product/P14544989861299658/1454499229154.jpg,/product/P14544989861299658/1454499240261.jpg,/product/P14544989861299658/1454499249123.jpg",
    "pdOnline": 1,
    "pdOnlineTime": 1454513196000,
    "pdOfflineTime": null,
    "pdCategoryId": 61,
    "pdDescription": "",
    "pdDetail": null,
    "pdPropVids": "107,108,109,110,103,105,112",
    "pdOriginalPrice": 3,
    "pdPrice": 1,
    "pdFtId": 34,
    "pdFtName": "测试模板1",
    "pdWeight": null,
    "pdVolume": null,
    "pdLabelVids": null,
    "pdIsDelete": 0,
    "pdNumber": 94,
    "pdEnableNum": 76,
    "pdLockNum": 18,
    "pdSalesVolumes": 0,
    "pdVirtualNumber": 100,
    "pdIsNew": false,
    "pdIsHot": false,
    "pdCommentNum": 520,
    "productSkus": [
        {
            "psId": 90,
            "psCreateTime": 1454500093000,
            "psUpdateTime": 1469084997000,
            "psCode": null,
            "psCustomCode": "DX118C",
            "psProductId": 31,
            "psOriginalPrice": 300,
            "psPrice": 100,
            "psNumber": 94,
            "psEnableNum": 76,
            "psLockNum": 4,
            "psIsUsed": 1,
            "psPropVids": "",
            "psVirtualNumber": 100,
            "psSalesVolumes": null,
            "psCustSerTime": 7,
            "product": null,
            "productProps": null,
            "propsNameAndValues": "",
            "page": null,
            "psOrglPriceDouble": 3,
            "psPriceDouble": 1
        }
    ],
    "props": [
        {
            "ppId": 90,
            "ppCreateTime": 1454492610000,
            "ppUpdateTime": 1464677512000,
            "ppName": "产品名称",
            "ppFormStyle": "radio",
            "ppIsDelete": 0,
            "ppIsKey": 0,
            "ppUseAsFilter": 0,
            "ppShId": 0,
            "ppvIdIn": null,
            "ppCategoryId": 61,
            "propValues": [
                {
                    "ppvId": 112,
                    "ppvCreateTime": 1454492611000,
                    "ppvUpdateTime": 1464677675000,
                    "ppvPpId": 90,
                    "ppvValue": "真空吸尘器",
                    "ppvIsDelete": 0,
                    "ppvShId": 0
                }
            ]
        },      
        {
            "ppId": 85,
            "ppCreateTime": 1454492351000,
            "ppUpdateTime": 1454492388000,
            "ppName": "功率",
            "ppFormStyle": "radio",
            "ppIsDelete": 0,
            "ppIsKey": 0,
            "ppUseAsFilter": 0,
            "ppShId": 0,
            "ppvIdIn": null,
            "ppCategoryId": 61,
            "propValues": [
                {
                    "ppvId": 105,
                    "ppvCreateTime": 1454492388000,
                    "ppvUpdateTime": 1464677675000,
                    "ppvPpId": 85,
                    "ppvValue": "500W(含)-999W(含)",
                    "ppvIsDelete": 0,
                    "ppvShId": 0
                }
            ]
        }
    ],
    "skuProps": null,
    "prop": null,
    "productCategory": null,
    "freightPrice": 0,
    "sortCondition": "comprehensive",
    "categoryNode": null,
    "skuId": null,
    "pdCodes": null,
    "page": null,
    "descOrAsc": null,
    "orderBy": null,
    "pdOrlPriceInt": 300,
    "pdPriceInt": 100}


###3获取评论列表数据

> **请求url：**http://192.168.1.168/sigoods/mobile/product/get_comments/{code}    

> **请求方式：**get

> **参数：** <br/>
showCount ：每页显示记录数，不传则显示默认的记录数 <br/>
currentPage ：当前页，主要靠这个进行分页<br/>
{code} ： 商品系统编码替换整个{code}<br/>

> **返回结果:**	

    {
        "pcId": 152,
        "pcCreateTime": 1468208453000,
        "pcMemberId": 289,
        "pcProductId": 7,
        "pcOrderNo": "2890001002016062495",
        "pcImgs": "\\1468208458955.jpeg",
        "pcType": 1,
        "pcParentId": 0,
        "pcIsAnonymous": 2,  /*是否匿名: 1否, 2是*/
        "pcText": "绞肉车很好",
        "member": {
            "id": 289,
            "nickname": "j**k",
            "idCard": null,
            "realName": null,
            "phone": "181***7730",
            "email": null,
            "loginPwd": "e10adc3949ba59abbe56e057f20f883e",
            "headImg": "/1467797610127.jpg",
            "sex": null,
            "birthday": null,
            "address": null,
            "grade": 0,
            "type": 1,
            "vip": 0,
            "registerType": 7,
            "activate": 1,
            "qqOpenid": null,
            "weixinOpenid": null,
            "mobileqqOpenid": null,
            "wxgzhOpenid": null,
            "wxUnionid": null,
            "enable": 1,
            "isdelete": 2,
            "createtime": 1466070495000,
            "updatetime": 1466070495000,
            "page": null,
            "orderBy": null,
            "descOrAsc": null,
            "accountinfoBO": null,
            "apptokenBO": null
        },
        "product": null,
        "order": null,
        "pcThumbImgs": "\\1468208458955_100x100.jpeg",
        "pcNickName": "阿***桑",
        "pcAreaInfo": "北京",
        "pcMemberLevel": "玛瑙会员",
        "pcCollectStatus": null,
        "pcProductCode": null,
        "page": null,
        "descOrAsc": null,
        "orderBy": null,
        "listPro": null,
        "listMem": null,
        "replyList": [
            {
                "pcId": 153,
                "pcCreateTime": 1468208719000,
                "pcMemberId": 1,
                "pcProductId": 7,
                "pcOrderNo": "2890001002016062495",
                "pcImgs": "\\1468208458955.jpeg",
                "pcType": 3,
                "pcParentId": 152,
                "pcText": "好的绞肉车",
                "member": null,
                "product": null,
                "order": null,
                "pcThumbImgs": null,
                "pcCollectStatus": null,
                "pcProductCode": null,
                "page": null,
                "descOrAsc": null,
                "orderBy": null,
                "listPro": null,
                "listMem": null,
                "replyList": null
            }
        ]
    }
  

data 失败的时候为null，成功的时候是评论的实体列表


###4获取商品分类数据

> **请求url：**http://192.168.1.168/sigoods/mobile/cat

> **请求方式：**get

> **参数：** <br/>

	pcParentId:父分类id<br/>

> **返回结果:**
		
		[{
        "pcId": 16,
        "pcCreateTime": 1452508387000,
        "pcUpdateTime": 1454318115000,
        "pcName": "生活电器",
        "pcParentId": null,
        "pcIsDelete": 0,
        "pcCode": "16",
        "pcShId": 0,
        "pcIcon": "",
        "pcSort": 1,
        "childrens": [
            {
                "pcId": 19,
                "pcCreateTime": 1452508433000,
                "pcUpdateTime": 1454318158000,
                "pcName": "白领厨房",
                "pcParentId": 16,
                "pcIsDelete": 0,
                "pcCode": "16,19",
                "pcShId": 0,
                "pcIcon": "",
                "pcSort": 1,
                "childrens": [
                    {
                        "pcId": 24,
                        "pcCreateTime": 1452509214000,
                        "pcUpdateTime": 1454318189000,
                        "pcName": "原汁机",
                        "pcParentId": 19,
                        "pcIsDelete": 0,
                        "pcCode": "16,19,24",
                        "pcShId": 0,
                        "pcIcon": "/category/1452509205431.png",
                        "pcSort": 1,
                        "childrens": [],
                        "productProps": null,
                        "page": null
                    },
                    {
                        "pcId": 22,
                        "pcCreateTime": 1452509183000,
                        "pcUpdateTime": 1454318201000,
                        "pcName": "面条机",
                        "pcParentId": 19,
                        "pcIsDelete": 0,
                        "pcCode": "16,19,22",
                        "pcShId": 0,
                        "pcIcon": "/category/1452509181844.png",
                        "pcSort": 3,
                        "childrens": [],
                        "productProps": null,
                        "page": null
                    }             
                ],
                "productProps": null,
                "page": null
            },
            {
                "pcId": 18,
                "pcCreateTime": 1452508419000,
                "pcUpdateTime": 1454318164000,
                "pcName": "日常家务",
                "pcParentId": 16,
                "pcIsDelete": 0,
                "pcCode": "16,18",
                "pcShId": 0,
                "pcIcon": "",
                "pcSort": 2,
                "childrens": [
                    {
                        "pcId": 61,
                        "pcCreateTime": 1454489564000,
                        "pcUpdateTime": 1464677138000,
                        "pcName": "吸尘器",
                        "pcParentId": 18,
                        "pcIsDelete": 0,
                        "pcCode": "16,18,61",
                        "pcShId": 0,
                        "pcIcon": "/category/1454489550435.jpg",
                        "pcSort": null,
                        "childrens": [],
                        "productProps": null,
                        "page": null
                    }
                ],
                "productProps": null,
                "page": null
            }
        ],
        "productProps": null,
        "page": null
    }]





