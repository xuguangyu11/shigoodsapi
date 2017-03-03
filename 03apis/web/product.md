# 商品接口

-------
1. [商品列表跳转](#1)
2. [获取商品列表](#2)
3. [商品详情跳转](#3)
4. [商品详情](#4)

-------

<h2 id="1"></h2>

###1商品列表跳转
> **请求url：**http://192.168.1.168/sigoods/web/product/list

> **请求方式：**get

> **返回结果:**		
	
	跳转到商品列表页面 


 --------
<h2 id="2"></h2>

###2获取商品列表

> **请求url：**http://192.168.1.168/sigoods/web/product/items

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

> **参数说明：** <br/>

	data:数据主体
	code:200数据返回正常
	msg:数据返回描述
	count : 上架的商品总数
	
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
	
	productSkus[]：
	psId//skuid;
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
	psCustSerTime;
	
	

> **返回结果:**

	{
	"count":21,
    "data": [
        {
            "pdCategoryId": 63,
            "pdCode": "P14545024718908841",
            "pdCommentNum": 25,
            "pdCreateTime": 1454504337000,
            "pdDescription": "",
            "pdEnableNum": 59,
            "pdFtId": 0,
            "pdFtName": "",
            "pdGalleryImg": "/product/P14545024718908841/1454503574000.jpg,/product/P14545024718908841/1454503582367.jpg,/product/P14545024718908841/1454503585911.jpg,/product/P14545024718908841/1454503611358.jpg",
            "pdId": 33,
            "pdIsDelete": 0,
            "pdIsHot": false,
            "pdIsNew": false,
            "pdLockNum": 18,
            "pdMainImg": "/product/P14545024718908841/1459836382980.jpg",
            "pdNumber": 77,
            "pdOnline": 1,
            "pdOnlineTime": 1454513187000,
            "pdOriginalPrice": 36.99,
            "pdOrlPriceInt": 3699,
            "pdPrice": 23.6,
            "pdPriceInt": 2360,
            "pdPropVids": "130,132,133,135,137,138,140,141,142,143,144,145,146,147",
            "pdSalesVolumes": 0,
            "pdShId": 1,
            "pdShortname": "加湿器家用静音卧室大容量大雾空气加湿",
            "pdUpdateTime": 1470995952000,
            "pdVirtualNumber": 100,
            "productSkus": [
                {
                    "propsNameAndValues": "",
                    "psCreateTime": 1454504339000,
                    "psCustSerTime": 7,
                    "psCustomCode": "DEM-F370",
                    "psEnableNum": 59,
                    "psId": 92,
                    "psIsUsed": 1,
                    "psLockNum": 1,
                    "psNumber": 77,
                    "psOrglPriceDouble": 36.99,
                    "psOriginalPrice": 3699,
                    "psPrice": 2360,
                    "psPriceDouble": 23.6,
                    "psProductId": 33,
                    "psPropVids": "",
                    "psUpdateTime": 1470995952000,
                    "psVirtualNumber": 100
                }
            ],
            "sortCondition": "comprehensive"
        },
        {
            "pdCategoryId": 62,
            "pdCode": "P14544977113904738",
            "pdCommentNum": 40,
            "pdCreateTime": 1454498656000,
            "pdDescription": "",
            "pdEnableNum": 90,
            "pdFtId": 34,
            "pdFtName": "测试模板1",
            "pdGalleryImg": "/product/P14544977113904738/1454497834842.jpg,/product/P14544977113904738/1454497838406.jpg,/product/P14544977113904738/1454497842403.jpg,/product/P14544977113904738/1454497846716.jpg",
            "pdId": 30,
            "pdIsDelete": 0,
            "pdIsHot": false,
            "pdIsNew": false,
            "pdLockNum": 10,
            "pdMainImg": "/product/P14544977113904738/1459836455166.jpg",
            "pdNumber": 100,
            "pdOnline": 1,
            "pdOnlineTime": 1454513200000,
            "pdOriginalPrice": 6.98,
            "pdOrlPriceInt": 698,
            "pdPrice": 2.89,
            "pdPriceInt": 289,
            "pdPropVids": "124,116,125,127,119,128,121,114,122,123,115",
            "pdSalesVolumes": 0,
            "pdShId": 1,
            "pdShortname": "家用可折叠烘衣机 宝宝专用超静音杀菌",
            "pdUpdateTime": 1467014423000,
            "pdVirtualNumber": 100,
            "productSkus": [
                {
                    "propsNameAndValues": "",
                    "psCreateTime": 1454498656000,
                    "psCustSerTime": 7,
                    "psCustomCode": "DEM-SZ3",
                    "psEnableNum": 90,
                    "psId": 89,
                    "psIsUsed": 1,
                    "psLockNum": 1,
                    "psNumber": 100,
                    "psOrglPriceDouble": 6.98,
                    "psOriginalPrice": 698,
                    "psPrice": 289,
                    "psPriceDouble": 2.89,
                    "psProductId": 30,
                    "psPropVids": "",
                    "psUpdateTime": 1467014423000,
                    "psVirtualNumber": 100
                }
            ],
            "sortCondition": "comprehensive"
        }
    ],
    "code": "200",
    "msg": "web端查询商品分页列表成功"
    }


  --------
<h2 id="3"></h2>

###3商品详情跳转

> **请求url：**http://192.168.1.168/sigoods/web/product/{code}

> **请求方式：**get

> **参数：** <br/>
{code} ： 商品的系统编码，替换{code} <br/>

> **返回结果:**
		
    跳转商品详情页面/modules/web/proDetail.jsp,并将商品编码放在隐藏域<input type="hidden" id="pdcode" value="${pdcode}" />


 --------
<h2 id="4"></h2>
###4获取商品详情

> **请求url：**http://192.168.1.168/sigoods/web/product/{code}

> **请求方式：**post

> **参数：** <br/>
{code} ： 商品的系统编码，替换{code} <br/>

> **参数说明：** <br/>

	data:数据主体
	code:200数据返回正常
	msg:数据返回描述
	
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
	
	productSkus[]：
	psId//skuid;
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
	psCustSerTime;
	
	props[]:
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
	
	propValues[]:
	ppvId;
	ppvCreateTime;//创建时间
	ppvUpdateTime;//修改时间
	ppvPpId;//属性名的id
	ppvValue;//属性值
	ppvIsDelete;//是否删除，1为是，表示删除，0没有删除
	ppvShId;//商家id,属于哪个商家，0表示系统的

> **返回结果:**
		
	{
    "data": {
        "pdId": 8,
        "pdCreateTime": 1453704947000,
        "pdUpdateTime": 1472440736000,
        "pdShId": 1,
        "pdCode": "P14537048766847503",
        "pdCustomCode": null,
        "pdShortname": "J-0001高端原汁机",
        "pdLongname": null,
        "pdMainImg": "/product/null/1459408745643.jpg",
        "pdGalleryImg": "/product/P14537048766847503/1460962555815.jpg,/product/P14537048766847503/1460962555358.jpg,/product/P14537048766847503/1460964905448.jpg",
        "pdOnline": 1,
        "pdOnlineTime": 1472107396000,
        "pdOfflineTime": 1470990228000,
        "pdCategoryId": 24,
        "pdDescription": "",
        "pdDetail": "<img src=\"/upload/shiwu/product/null/1453706007694.jpg\" title=\"Image: /upload/shiwu/product/null/1453706007694.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705895897.jpg\" title=\"Image: /upload/shiwu/product/null/1453705895897.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705900396.jpg\" title=\"Image: /upload/shiwu/product/null/1453705900396.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705906197.gif\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705909337.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705911990.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705917817.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453705920476.jpg\" title=\"Image: /upload/shiwu/product/null/1453705920476.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453706039771.jpg\" style=\"display: block;\"><img title=\"Image: /upload/shiwu/product/null/1453706043853.jpg\" src=\"/upload/shiwu/product/null/1453706043853.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453706046028.jpg\" title=\"Image: /upload/shiwu/product/null/1453706046028.jpg\" style=\"display: block;\"><img src=\"/upload/shiwu/product/null/1453706051757.jpg\" title=\"Image: /upload/shiwu/product/null/1453706051757.jpg\" style=\"display: block;\">",
        "pdPropVids": "26,158,175",
        "pdOriginalPrice": 40,
        "pdPrice": 32.99,
        "pdFtId": 51,
        "pdFtName": "测试2",
        "pdWeight": null,
        "pdVolume": null,
        "pdLabelVids": null,
        "pdIsDelete": 0,
        "pdNumber": 299,
        "pdEnableNum": 271,
        "pdLockNum": 69,
        "pdSalesVolumes": 1,
        "pdVirtualNumber": 370,
        "pdIsNew": true,
        "pdIsHot": true,
        "pdCommentNum": 46,
        "productSkus": [
            {
                "psId": 101,
                "psCreateTime": 1464690975000,
                "psUpdateTime": 1472107385000,
                "psCode": null,
                "psCustomCode": "HL0676",
                "psProductId": 8,
                "psOriginalPrice": 4520,
                "psPrice": 5670,
                "psNumber": 50,
                "psEnableNum": 37,
                "psLockNum": 13,
                "psIsUsed": 1,
                "psPropVids": "224,23,25,180,183",
                "psVirtualNumber": 100,
                "psSalesVolumes": null,
                "psCustSerTime": 7,
                "product": null,
                "productProps": null,
                "propsNameAndValues": "",
                "page": null,
                "psOrglPriceDouble": 45.2,
                "psPriceDouble": 56.7
            },
            {
                "psId": 108,
                "psCreateTime": 1467013014000,
                "psUpdateTime": 1472107385000,
                "psCode": null,
                "psCustomCode": "SG-Meatgrinder-00025",
                "psProductId": 8,
                "psOriginalPrice": 8500,
                "psPrice": 4500,
                "psNumber": 50,
                "psEnableNum": 49,
                "psLockNum": 1,
                "psIsUsed": 1,
                "psPropVids": "224,23,25,179,184",
                "psVirtualNumber": 100,
                "psSalesVolumes": 0,
                "psCustSerTime": 7,
                "product": null,
                "productProps": null,
                "propsNameAndValues": "",
                "page": null,
                "psOrglPriceDouble": 85,
                "psPriceDouble": 45
            },
            {
                "psId": 109,
                "psCreateTime": 1467015688000,
                "psUpdateTime": 1472440735000,
                "psCode": null,
                "psCustomCode": "HL067",
                "psProductId": 8,
                "psOriginalPrice": 4000,
                "psPrice": 3299,
                "psNumber": 99,
                "psEnableNum": 85,
                "psLockNum": 14,
                "psIsUsed": 1,
                "psPropVids": "224,23,25,179,183",
                "psVirtualNumber": 70,
                "psSalesVolumes": 1,
                "psCustSerTime": 7,
                "product": null,
                "productProps": null,
                "propsNameAndValues": "",
                "page": null,
                "psOrglPriceDouble": 40,
                "psPriceDouble": 32.99
            },
            {
                "psId": 110,
                "psCreateTime": 1467015721000,
                "psUpdateTime": 1472107385000,
                "psCode": null,
                "psCustomCode": "HL06766d",
                "psProductId": 8,
                "psOriginalPrice": 15600,
                "psPrice": 12300,
                "psNumber": 100,
                "psEnableNum": 100,
                "psLockNum": 0,
                "psIsUsed": 1,
                "psPropVids": "224,23,25,180,184",
                "psVirtualNumber": 100,
                "psSalesVolumes": 0,
                "psCustSerTime": 7,
                "product": null,
                "productProps": null,
                "propsNameAndValues": "",
                "page": null,
                "psOrglPriceDouble": 156,
                "psPriceDouble": 123
            }
        ],
        "props": [
            {
                "ppId": 128,
                "ppCreateTime": 1456124678000,
                "ppUpdateTime": 1457942497000,
                "ppName": "2341",
                "ppFormStyle": "radio",
                "ppIsDelete": 0,
                "ppIsKey": 0,
                "ppUseAsFilter": 1,
                "ppShId": 0,
                "ppvIdIn": null,
                "ppCategoryId": 24,
                "propValues": [
                    {
                        "ppvId": 158,
                        "ppvCreateTime": 1456124678000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 128,
                        "ppvValue": "324",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    }
                ]
            },
            {
                "ppId": 44,
                "ppCreateTime": 1452755997000,
                "ppUpdateTime": 1464677512000,
                "ppName": "颜色分类",
                "ppFormStyle": "radio",
                "ppIsDelete": 0,
                "ppIsKey": 0,
                "ppUseAsFilter": 1,
                "ppShId": 1,
                "ppvIdIn": null,
                "ppCategoryId": 24,
                "propValues": [
                    {
                        "ppvId": 26,
                        "ppvCreateTime": 1452755997000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 44,
                        "ppvValue": "红色",
                        "ppvIsDelete": 0,
                        "ppvShId": 1
                    }
                ]
            },
            {
                "ppId": 151,
                "ppCreateTime": 1457942546000,
                "ppUpdateTime": 1465697961000,
                "ppName": "材料",
                "ppFormStyle": "radio",
                "ppIsDelete": 0,
                "ppIsKey": 0,
                "ppUseAsFilter": 1,
                "ppShId": 0,
                "ppvIdIn": null,
                "ppCategoryId": 24,
                "propValues": [
                    {
                        "ppvId": 175,
                        "ppvCreateTime": 1457942546000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 151,
                        "ppvValue": "钢",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    }
                ]
            }
        ],
        "skuProps": [
            {
                "ppId": 38,
                "ppCreateTime": 1452753222000,
                "ppUpdateTime": 1465803592000,
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
                        "ppvId": 224,
                        "ppvCreateTime": 1465803592000,
                        "ppvUpdateTime": 1465803521000,
                        "ppvPpId": 38,
                        "ppvValue": "1000ml以下（含1000ml）",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    }
                ]
            },
            {
                "ppId": 154,
                "ppCreateTime": 1460599582000,
                "ppUpdateTime": 1460600510000,
                "ppName": "颜色",
                "ppFormStyle": "radio",
                "ppIsDelete": 0,
                "ppIsKey": 1,
                "ppUseAsFilter": 0,
                "ppShId": 0,
                "ppvIdIn": null,
                "ppCategoryId": 24,
                "propValues": [
                    {
                        "ppvId": 179,
                        "ppvCreateTime": 1460599582000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 154,
                        "ppvValue": "白色",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    },
                    {
                        "ppvId": 180,
                        "ppvCreateTime": 1460599582000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 154,
                        "ppvValue": "黑色",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    }
                ]
            },
            {
                "ppId": 155,
                "ppCreateTime": 1460617445000,
                "ppUpdateTime": 1464677512000,
                "ppName": "(⊙o⊙)…",
                "ppFormStyle": "radio",
                "ppIsDelete": 0,
                "ppIsKey": 1,
                "ppUseAsFilter": 0,
                "ppShId": 0,
                "ppvIdIn": null,
                "ppCategoryId": 24,
                "propValues": [
                    {
                        "ppvId": 183,
                        "ppvCreateTime": 1460617445000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 155,
                        "ppvValue": "1",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    },
                    {
                        "ppvId": 184,
                        "ppvCreateTime": 1460617445000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 155,
                        "ppvValue": "2",
                        "ppvIsDelete": 0,
                        "ppvShId": 0
                    }
                ]
            },
            {
                "ppId": 43,
                "ppCreateTime": 1452753509000,
                "ppUpdateTime": 1460614688000,
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
                        "ppvId": 25,
                        "ppvCreateTime": 1452753509000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 43,
                        "ppvValue": "200w及以下",
                        "ppvIsDelete": 0,
                        "ppvShId": 1
                    }
                ]
            },
            {
                "ppId": 39,
                "ppCreateTime": 1452753255000,
                "ppUpdateTime": 1464248363000,
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
                        "ppvId": 23,
                        "ppvCreateTime": 1452753255000,
                        "ppvUpdateTime": 1464677675000,
                        "ppvPpId": 39,
                        "ppvValue": "豆腐 冰淇淋 婴儿辅食 制奶昔 榨汁",
                        "ppvIsDelete": 0,
                        "ppvShId": 1
                    }
                ]
            }
        ],
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
        "pdOrlPriceInt": 4000,
        "pdPriceInt": 3299,
        "freeShip": false,
        "freeShipDesc": null
    },
    "code": "200",
    "msg": "web端查询商品详情成功"
    }

		