# 框架说明
# erazar后台管理系统

erazar后台管理系统是基于 springMVC + MyBatis + Shiro + bootstrap + jQuery-ui 实现的一套商城管理平台

## 1. 代码结构说明

![代码结构](/imgs/20160216161733.png)<br/>

项目是maven项目 

1.**src/main/java** 后台的源代码

| 目录          | 说明          |
| ------------- |:-------------:| 
|    alipay		|  	阿里支付	|
|    common		|   通用工具类	|
|    shiwu 		|   业务代码	|
| shiwu/business|   dao和service|
| shiwu/common  |   拦截器，异常处理，分页和安全控制|
| shiwu/model	|   实体 		|
| shiwu/modules	|   controllers |
| shiwu/tasks	|   自动任务 	|


2.**src/main/resources** 资源和配置文件

| 目录          | 说明          |
| ------------- |:-------------:| 
|    config		|  	配置文件	|
|    mapper		|   mybatis的sql 配置文件	|
|    spring 		|   spring的相关配置文件	|
	

3.**webRoot/static**  页面中使用静态资源 ，下面分模块存放

4.**WEB-INF/modules** 不同模块使用的页面文件