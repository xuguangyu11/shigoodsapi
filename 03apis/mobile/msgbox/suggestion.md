# 手机移动端

## 1.投诉建议接口

###1.1获取投诉建议分类

> **请求url：**http://192.168.1.168/shiwu/mobile/member/msgbox/suggestion/get_classification

> **请求方式：**get

> **参数：** <br/>
无 <br/>

> **返回结果:**

	{"1":"订单问题","2":"物流问题","3":"客户问题","4":"商品问题","5":"价格问题","6":"网站功能","7":"建议","8":"其他"}

失败的时候为null


###1.2提交投诉建议

> **请求url：**http://192.168.1.168/shiwu/mobile/member/msgbox/suggestion/add

> **请求方式：**post

> **参数：** <br/>
tsClassification : 投诉建议分类id<br/>
tsOrderNo : 涉及的订单<br/>
tstText : 投诉建议内容<br/>

> **返回结果:**

	{"code":"200","msg":"操作成功"}

失败的时候为: {"code":"201","msg":"操作失败"} 或为 其他提示语


###1.3获取我的投诉建议列表

> **请求url：**http://192.168.1.168/shiwu/mobile/member/msgbox/suggestion/list

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
	        "tsId": 5,
	        "tsCreateTime": 1456815584000,
	        "tsMemberId": 250,
	        "tsClassification": 3,
	        "tsOrderNo": "",
	        "tstText": "道路次陌陌",
	        "tsType": null,
	        "tsProcessingStatus":0,
	        "tsReply":"斯蒂芬",
	        "member": {
	            "orderBy": null,
	            "descOrAsc": null,
	            "idIn": null,
	            "currentDoSearchUser": null,
	            "page": null,
	            "tmId": 250,
	            "tmMemberLoginname": null,
	            "tmMemberNickname": "yoyo",
	            "tmRealName": "yaoyaoyao",
	            "tmIdCard": "123456789123",
	            "tmMemberEmail": "964779067@qq.com",
	            "tmMemberPwd": "28523cef149d7b4a9722eb3eca2b18a9",
	            "tmMemberImg": null,
	            "tmSex": "W",
	            "tmBirthday": 1244304000000,
	            "tmMemberPhone": "15030121852",
	            "tmMemberAddress": null,
	            "tmMemberGrade": "0",
	            "tmMemberType": 1,
	            "tmVip": "0",
	            "tmQualification": null,
	            "tmRegisterType": "1",
	            "tmMemberCreatetime": 1456214919000,
	            "tmMemberUpdatetime": 1456475837000,
	            "tmMemberActivate": 1,
	            "tmMemberSecretkey": null,
	            "tmMemberOuttime": null,
	            "tmQqOpenid": null,
	            "tmWeixinOpenid": null,
	            "tmMobileqqOpenid": null,
	            "tmWxgzhOpenid": null,
	            "tmMemberEnable": 1,
	            "tmMemberIsdelete": 0,
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
	        }
	    },
	    {
	        "orderBy": null,
	        "descOrAsc": null,
	        "idIn": null,
	        "currentDoSearchUser": null,
	        "page": null,
	        "tsId": 4,
	        "tsCreateTime": 1456815553000,
	        "tsMemberId": 250,
	        "tsClassification": 2,
	        "tsOrderNo": "",
	        "tstText": "新",
	        "tsType": null,
	        "tsProcessingStatus":0,
	        "tsReply":"斯蒂芬",
	        "member": {
	            "orderBy": null,
	            "descOrAsc": null,
	            "idIn": null,
	            "currentDoSearchUser": null,
	            "page": null,
	            "tmId": 250,
	            "tmMemberLoginname": null,
	            "tmMemberNickname": "yoyo",
	            "tmRealName": "yaoyaoyao",
	            "tmIdCard": "123456789123",
	            "tmMemberEmail": "964779067@qq.com",
	            "tmMemberPwd": "28523cef149d7b4a9722eb3eca2b18a9",
	            "tmMemberImg": null,
	            "tmSex": "W",
	            "tmBirthday": 1244304000000,
	            "tmMemberPhone": "15030121852",
	            "tmMemberAddress": null,
	            "tmMemberGrade": "0",
	            "tmMemberType": 1,
	            "tmVip": "0",
	            "tmQualification": null,
	            "tmRegisterType": "1",
	            "tmMemberCreatetime": 1456214919000,
	            "tmMemberUpdatetime": 1456475837000,
	            "tmMemberActivate": 1,
	            "tmMemberSecretkey": null,
	            "tmMemberOuttime": null,
	            "tmQqOpenid": null,
	            "tmWeixinOpenid": null,
	            "tmMobileqqOpenid": null,
	            "tmWxgzhOpenid": null,
	            "tmMemberEnable": 1,
	            "tmMemberIsdelete": 0,
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
	        }
	    }
	]

###1.4删除投诉建议

> **请求url：**http://192.168.1.168/shiwu/mobile/member/msgbox/suggestion/del

> **请求方式：**post

> **参数：** <br/>
tsId: 投诉建议id <br/>

> **返回结果:**

	{"code":"200","msg":"操作成功"}

失败的时候为: {"code":"201","msg":"操作失败"} 或为 其他提示语

