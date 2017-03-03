# WEB 运费接口


## 1. 根据SKUID，请求对应的运费

> 
**请求url：**http://192.168.1.168/sigoods/web/freight/getFreightInfo

> **请求方式：**get <br/>

>**请求说明：**<br/> 
`   `如果是不明确商品运送方式（如首次进入确认订单页），可以把参数deliveryWay=0，后台进过处理后会返回可用的运送方式
<br/>

> **参数：** <br/>
skuIds ：  skuId字符串，逗号分隔<br />
numbers ： 购买数量字符串，逗号分隔<br />
deliveryWay ： 运费方式：1快递、2EMS、3平邮<br />
locationId ： 地址ID<br />

> **返回结果:**

	{"data":{"deliveryWay":4,"freightPrice":6.00,"isReach":0},"code":200,"msg":"获取运费成功"}

> **结果说明:**<br/>
  code=200 为操作成功，300失败，<br />
  msg ：提示信息，<br />
  freightPrice 失败的时候为0，成功的时候是具体费用<br />
  isReach 是否可达  ：0是，1否 如果不可达，取消订单 <br />
  deliveryWay 运送方式：1快递、2EMS、3平邮、4默认、5包邮  ，返回的是商品模板公共运费方式列表第一个，如果是*包邮*或*默认*状态，建议前端限制用户不能选择运送方式
  
## 2. 根据SKUID，请求可用运送方式

> 
**请求url：**http://192.168.1.168/sigoods/web/freight/availDelivery

>**请求说明：**<br/>
`   `此接口可以获取对应skuId下可用运送方式列表

> **请求方式：**get <br/>

> **参数：** <br/>
skuIds ： skuId字符串，逗号分隔<br />

> **返回结果:**
     
     {"data":[1],"code":"200","msg":" 操作成功 "}
     
> **结果说明:**<br/>
  code=200 为操作成功，300失败，<br />
  msg ：提示信息，<br />
  data ：运送方式列表编码 ：1快递、2EMS、3平邮、4默认<br />
  