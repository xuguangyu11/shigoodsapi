# 部分自定义js的修改

--------

* [1. ajax链接的处理](#1)
	* [1.1. 菜单栏的a标签](#1.1)
	* [1.2. 内容页的a标签](#1.2)
	* [1.3. 查找带回](#1.3)
* [2. 异步提交表单](#2)
* [3. 表单分页搜索](#3)

--------

<h2 id="1"> 1.ajax链接的处理</h2>

<h3 id="1.1">1.1.菜单栏的a标签</h3>

菜单栏的a标签要实现异步加载content页面的内容，只需要加上 class="ajaxify" 就行，即有 *ajaxify* class 就可以了，实现部分在app.js 里面 * handleSidebarMenu * 中有实现

<h3 id="1.2">1.2.内容页的a标签</h3>

主要实现方式是加上data-ajax属性
content部分的a标签实现的两个部分功能：

1.异步的替换content的页面，例如点击添加和修改的时候，返回添加修改页面，此情况使用方式

	<a href="xxxx" data-ajax="page">

2.异步的在content的页面请求数据，接收返回的json数据 ，例如点击点击页面的修改

	<a href="xxxx" data-ajax="done">

<h3 id="1.3">1.3查找带回</h3>

实现方式是 custom.js 里面的handleSerachBack() 方法
使用方式：

	<a href="xxxx" searchback></a>

例如：

	<div class="form-group">
				<label class="control-label col-md-3">上级</label>
				<div class="col-md-9">
					<div class="input-group">
						<input type="text" placeholder="请输入上级" name="upper" class="form-control"/>
						<span class="input-group-addon">
							<a href="${ctx}/admin/menu/" searchback><i class="fa fa-search"></i></a>
						</span>
					</div>
					<div class="input-group">
						<span class="help-block">
						不指明上级则为第一级显示
						</span>
					</div>
				</div>
			</div>


这样就会把href加载的页面已对话框的方式弹出来，在弹出框操作需要的元素即可,弹出的操作的页面中调用  $.bringBack(data)就可以了，其中参数data是一个json

源码在custom.js 中：

	jQuery.extend({
		/**
		 * 查找待会，把查找带回的值设置到对应的操作表单元素上面
		 * @param data 需要被带回的对象 例如：{'username':'Jobs','age':50}
		 * @return 如上面的返回值的时候会设置页面中 input[name="username"] 
		 * 的value=Jobs,input[name="age"] 的value=50
		 */
		bringBack: function(data) {
			 var $targetBtn = $(".current-search-back");//当前活动的查找待会按钮
			 //设置当前活动按钮的name值的表单元素的值为data中的值
			 $.each(data,function(i,v){
				 $targetBtn.siblings('[name="'+i+'"]').val(v);
			 });

		}
	});

-------

<h2 id="2">2.异步提交表单</h2>

表单的onsubmit 指定为Custom.divAjaxSubmitForm，次方法的源码在custom.js 内部实现的

	<form action="${ctx}/admin/role/" method="POST" id="form_sample_1"
	onsubmit="return Custom.divAjaxSubmitForm(this,'content-frame',Custom.divSubmitCallback);"
	class="form-horizontal">

--------

<h2 id="3"> 3.表单分页搜索</h2>

表单的onsubmit 指定为Custom.divSubmitPageForm，次方法的源码在custom.js 内部实现的

	<form action="${ctx}/admin/ad/list" rel="page" 
	onsubmit="return Custom.divSubmitPageForm(this,'content-frame');">

在form内的表单的表格下引入

	<jsp:include page="../layout/pagetool.jsp" />


在controller里面需要传入一个page实体，并将此page set进需要传入后台的实体里面

	public String list(User user,Page page,Model model){
		user.setPage(page);

