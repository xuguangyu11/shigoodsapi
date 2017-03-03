# 手机移动端

## 1.商品收藏接口

###1.1添加商品收藏

> **请求url：**http://192.168.1.168/shiwu/mobile/member/collection/add

> **请求方式：**post

> **参数：** <br/>
tcSkuId ：商品skuid <br/>
tcProductId ：商品id <br/>

> **返回结果:**
		
	{"code":"200","msg":"操作成功"}


###1.2删除商品收藏

> **请求url：**http://192.168.1.168/shiwu/mobile/member/collection/del/{id}

> **请求方式：**get

> **参数：** <br/>
{id} ：商品收藏id，替换{id} <br/>

> **返回结果:**
		
	{"code":"200","msg":"操作成功"}

###1.3获取我的商品收藏列表

> **请求url：**http://192.168.1.168/shiwu/mobile/member/collection/get_list

> **请求方式：**get

> **参数：** <br/>
showCount ：每页显示记录数 <br/>
currentPage ：当前页，主要靠这个进行分页<br/>

> **返回结果:**
	[
	    {
	        "orderBy": null,
	        "descOrAsc": null,
	        "idIn": null,
	        "currentDoSearchUser": null,
	        "page": null,
	        "tcId": 2,
	        "tcSkuId": 65,
	        "tcMemberId": 1,
	        "tcProductId": 8,
	        "product": {
	            "orderBy": null,
	            "descOrAsc": null,
	            "idIn": null,
	            "currentDoSearchUser": null,
	            "page": null,
	            "pdId": 8,
	            "pdCreateTime": 1453704947000,
	            "pdUpdateTime": 1454054002000,
	            "pdShId": 1,
	            "pdCode": "P14537048766847503",
	            "pdCustomCode": null,
	            "pdShortname": "J-0001高端原汁机",
	            "pdLongname": null,
	            "pdMainImg": "/product/null/1453949601772.jpg",
	            "pdGalleryImg": "/product/null/1453949612623.jpg,/product/null/1453949614500.jpg,/product/null/1453949616457.jpg,/product/null/1453949619223.jpg",
	            "pdOnline": 1,
	            "pdOnlineTime": 1453704956000,
	            "pdOfflineTime": null,
	            "pdCategoryId": 24,
	            "pdDescription": "",
	            "pdDetail": null,
	            "pdPropVids": "26",
	            "pdOriginalPrice": 1499,
	            "pdPrice": 599,
	            "pdFtId": null,
	            "pdFtName": null,
	            "pdWeight": null,
	            "pdVolume": null,
	            "pdLabelVids": null,
	            "pdIsDelete": 0,
	            "pdNumber": 100,
	            "pdEnableNum": 88,
	            "pdLockNum": 12,
	            "pdSalesVolumes": 0,
	            "pdVirtualNumber": 450,
	            "pdIsNew": true,
	            "pdIsHot": true,
	            "pdCommentNum": 5,
	            "productSkus": [
	                {
	                    "orderBy": null,
	                    "descOrAsc": null,
	                    "idIn": null,
	                    "currentDoSearchUser": null,
	                    "page": null,
	                    "psId": 65,
	                    "psCreateTime": 1453704947000,
	                    "psUpdateTime": 1457071723000,
	                    "psCode": null,
	                    "psCustomCode": "SG-JuiceMachine-0001R",
	                    "psProductId": 8,
	                    "psOriginalPrice": 1499,
	                    "psPrice": 599,
	                    "psNumber": 100,
	                    "psEnableNum": 88,
	                    "psLockNum": 12,
	                    "psIsUsed": 1,
	                    "psPropVids": "22,23,25",
	                    "psVirtualNumber": 450,
	                    "psSalesVolumes": 0,
	                    "product": null,
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
	                }
	            ],
	            "props": null,
	            "skuProps": null,
	            "prop": null,
	            "productCategory": null,
	            "freightPrice": null,
	            "sortCondition": "comprehensive",
	            "categoryNode": null,
	            "skuId": null
	        }
	    },
	    {
	        "orderBy": null,
	        "descOrAsc": null,
	        "idIn": null,
	        "currentDoSearchUser": null,
	        "page": null,
	        "tcId": 1,
	        "tcSkuId": 68,
	        "tcMemberId": 1,
	        "tcProductId": 11,
	        "product": {
	            "orderBy": null,
	            "descOrAsc": null,
	            "idIn": null,
	            "currentDoSearchUser": null,
	            "page": null,
	            "pdId": 11,
	            "pdCreateTime": 1453706433000,
	            "pdUpdateTime": 1454053936000,
	            "pdShId": 1,
	            "pdCode": "P14537061880191102",
	            "pdCustomCode": null,
	            "pdShortname": "NM-0001全自动家用面条机",
	            "pdLongname": null,
	            "pdMainImg": "/product/null/1454051064938.png",
	            "pdGalleryImg": "/product/null/1454051056095.png",
	            "pdOnline": 1,
	            "pdOnlineTime": 1453706731000,
	            "pdOfflineTime": null,
	            "pdCategoryId": 22,
	            "pdDescription": "大容量，一次能做2斤面，高级大马力纯铜电机，14种不同的模头",
	            "pdDetail": null,
	            "pdPropVids": "60,61,62",
	            "pdOriginalPrice": 1599,
	            "pdPrice": 799,
	            "pdFtId": null,
	            "pdFtName": null,
	            "pdWeight": null,
	            "pdVolume": null,
	            "pdLabelVids": null,
	            "pdIsDelete": 0,
	            "pdNumber": 50,
	            "pdEnableNum": 50,
	            "pdLockNum": 0,
	            "pdSalesVolumes": 0,
	            "pdVirtualNumber": 100,
	            "pdIsNew": true,
	            "pdIsHot": true,
	            "pdCommentNum": null,
	            "productSkus": [
	                {
	                    "orderBy": null,
	                    "descOrAsc": null,
	                    "idIn": null,
	                    "currentDoSearchUser": null,
	                    "page": null,
	                    "psId": 68,
	                    "psCreateTime": 1453706433000,
	                    "psUpdateTime": 1454053936000,
	                    "psCode": null,
	                    "psCustomCode": "",
	                    "psProductId": 11,
	                    "psOriginalPrice": 1599,
	                    "psPrice": 799,
	                    "psNumber": 50,
	                    "psEnableNum": 50,
	                    "psLockNum": 0,
	                    "psIsUsed": 1,
	                    "psPropVids": "",
	                    "psVirtualNumber": 100,
	                    "psSalesVolumes": 0,
	                    "product": null,
	                    "productProps": [],
	                    "propsNameAndValues": ""
	                }
	            ],
	            "props": null,
	            "skuProps": null,
	            "prop": null,
	            "productCategory": null,
	            "freightPrice": null,
	            "sortCondition": "comprehensive",
	            "categoryNode": null,
	            "skuId": null
	        }
	    }
	]


###1.4查询商品对应的sku是否收藏过了

> **请求url：**http://192.168.1.168/shiwu/mobile/member/collection/exists

> **请求方式：**get

> **参数：** <br/>
pdId ：商品pdId <br/>

> **返回结果:**
	true    :     代表已经添加过了
	false     :     代表没有添加过
	
	
###1.5获取我的商品收藏列表（重构数据结构）

> **请求url：**http://192.168.1.168/shiwu/mobile/member/collection/get_list

> **请求方式：**get

> **参数：** <br/>
showCount ：每页显示记录数 <br/>
currentPage ：当前页，主要靠这个进行分页<br/>

> **返回结果:**
[
    {
        "productSku": {
            "psSalesVolumes": 0,
            "psId": 68,
            "psNumber": 42,
            "psLockNum": 10,
            "psEnableNum": 32,
            "propsNameAndValues": "容量:一次1000g面粉 ， 型号:SG-NM-0001G ， 品牌:时物1 ， ",
            "product": {
                "pdShId": 1,
                "pdCode": "P14537061880191102",
                "pdVirtualNumber": 1000,
                "pdOnline": 1,
                "pdIsNew": true,
                "sortCondition": "comprehensive",
                "pdShortname": "NM-0001全自动家用面条机",
                "pdCreateTime": 1453706433000,
                "pdSalesVolumes": 0,
                "pdPrice": 799,
                "pdFtId": 0,
                "pdOnlineTime": 1453706731000,
                "pdNumber": 42,
                "pdGalleryImg": "/product/null/1454051056095.png",
                "pdLockNum": 10,
                "pdOriginalPrice": 1599,
                "pdMainImg": "/product/null/1459408734941.jpg",
                "pdIsHot": true,
                "pdId": 11,
                "pdDetail": "<img src=\"/upload/shiwu/product/null/1454053804761.jpg\" title=\"Image: /upload/shiwu/product/null/1454053804761.jpg\" style=\"display: block;\">",
                "pdIsDelete": 0,
                "pdCategoryId": 22,
                "pdEnableNum": 32,
                "pdUpdateTime": 1459409098000,
                "pdPropVids": "60,61,62",
                "pdDescription": "大容量，一次能做2斤面，高级大马力纯铜电机，14种不同的模头",
                "pdCommentNum": 1
            },
            "psCustomCode": "",
            "psPropVids": "60,61,62",
            "productProps": [
                {
                    "ppIsKey": 0,
                    "propValues": [
                        {
                            "ppvIsDelete": 0,
                            "ppvValue": "一次1000g面粉",
                            "ppvPpId": 69,
                            "ppvCreateTime": 1453962627000,
                            "ppvUpdateTime": 1464677675000,
                            "ppvShId": 0,
                            "ppvId": 60
                        }
                    ],
                    "ppShId": 0,
                    "ppUseAsFilter": 0,
                    "ppUpdateTime": 1457077192000,
                    "ppFormStyle": "radio",
                    "ppName": "容量",
                    "ppCreateTime": 1453962627000,
                    "ppId": 69,
                    "ppIsDelete": 0,
                    "ppCategoryId": 22
                },
                {
                    "ppIsKey": 0,
                    "propValues": [
                        {
                            "ppvIsDelete": 0,
                            "ppvValue": "SG-NM-0001G",
                            "ppvPpId": 70,
                            "ppvCreateTime": 1453962846000,
                            "ppvUpdateTime": 1464677675000,
                            "ppvShId": 0,
                            "ppvId": 61
                        }
                    ],
                    "ppShId": 0,
                    "ppUseAsFilter": 0,
                    "ppUpdateTime": 1464677512000,
                    "ppFormStyle": "radio",
                    "ppName": "型号",
                    "ppCreateTime": 1453962846000,
                    "ppId": 70,
                    "ppIsDelete": 0,
                    "ppCategoryId": 22
                },
                {
                    "ppIsKey": 0,
                    "propValues": [
                        {
                            "ppvIsDelete": 0,
                            "ppvValue": "时物1",
                            "ppvPpId": 71,
                            "ppvCreateTime": 1453962865000,
                            "ppvUpdateTime": 1464677675000,
                            "ppvShId": 0,
                            "ppvId": 62
                        }
                    ],
                    "ppShId": 0,
                    "ppUseAsFilter": 0,
                    "ppUpdateTime": 1464677512000,
                    "ppFormStyle": "radio",
                    "ppName": "品牌",
                    "ppCreateTime": 1453962865000,
                    "ppId": 71,
                    "ppIsDelete": 0,
                    "ppCategoryId": 22
                }
            ],
            "psVirtualNumber": 1000,
            "psCreateTime": 1453706433000,
            "psUpdateTime": 1463467903000,
            "psPrice": 799,
            "psOriginalPrice": 1599,
            "psIsUsed": 1,
            "psProductId": 11
        },
        "tcSkuId": 68,
        "tcProductId": 11,
        "tcId": 3,
        "tcMemberId": 5
    },
    {
        "productSku": {
            "psId": 95,
            "psNumber": 16,
            "psEnableNum": 8,
            "propsNameAndValues": "",
            "product": {
                "pdShId": 1,
                "pdCode": "P14545082063091251",
                "pdVirtualNumber": 100,
                "pdFtName": "terer21",
                "pdOnline": 1,
                "pdIsNew": false,
                "sortCondition": "comprehensive",
                "pdShortname": "卡通创意 通用情侣迷你便携1",
                "pdCreateTime": 1454508732000,
                "pdSalesVolumes": 3,
                "pdPrice": 8930,
                "pdFtId": 20,
                "pdOnlineTime": 1454513177000,
                "pdNumber": 16,
                "pdGalleryImg": "/product/P14545082063091251/1454508470748.jpg,/product/null/1459492136314.jpg,/product/P14545082063091251/1454508450446.jpg,/product/P14545082063091251/1454508486882.jpg,/product/P14545082063091251/1454508457719.jpg,/product/P14545082063091251/1454508475306.jpg",
                "pdLockNum": 5,
                "pdOriginalPrice": 7958,
                "pdMainImg": "/product/P14545082063091251/1459836248789.jpg",
                "pdIsHot": false,
                "pdId": 36,
                "pdDetail": "<img src=\"/upload/shiwu/product/P14545082063091251/1454508557666.jpg\" title=\"Image: /upload/shiwu/product/P14545082063091251/1454508557666.jpg\" style=\"display: block;\">",
                "pdIsDelete": 0,
                "pdCategoryId": 65,
                "pdEnableNum": 8,
                "pdUpdateTime": 1463632891000,
                "pdPropVids": "150,151,152,153,154,155",
                "pdDescription": "",
                "pdCommentNum": 2
            },
            "psCustomCode": "UP33",
            "psPropVids": "",
            "psVirtualNumber": 100,
            "psCreateTime": 1454508732000,
            "psUpdateTime": 1463632891000,
            "psPrice": 8930,
            "psOriginalPrice": 7958,
            "psIsUsed": 1,
            "psProductId": 36
        },
        "tcSkuId": 95,
        "tcProductId": 36,
        "tcId": 2,
        "tcMemberId": 5
    }
]
