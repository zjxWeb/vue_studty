## vue的简介 
1. js框架
2. 简化DOm操作
3. 响应式的数据驱动
## Vue基础
1. el 挂载点
	+  vue实例的作用范围是
		+ el 命中的内部都是可以的
		+ el 也是支持其他的选择题的
		+ 建议使用id选择器
		+ 只支持双标签（body，html除外），不支持双标签
		+ 建议使用div标签
2. data：数据对象
	+ vue中用到的数据定义在data中
	+ data中可以写<span style="color:red;">复杂类型</span>的数据
	+ 渲染的复杂类型数据时，<span style="color:red;">遵守js的语法</span>即可
3. vue指令 以V-开头
	+ v-text 设置标签的文本值（textContent）
		+  `<h2 v-text="message + '!' "></h2><h2>zjx{{message + "!"}} </h2>`
		+  <span style="color:red;">部分替换的时候采用达括号的形式</span>
		+  默认写法会替换全部的内容，使用 <span style="color:red"> 差值表达式{{}}</span>可以替换指定的内容
		+  内部支持写<span style="color:red"> 表达式</span>
	+ v-html
		+ v-html 指令的作用是：<span style="color:red">设置元素的innerHTML</span>
		+ 内容中有html结构会解析为标签
		+ v-text指令无论内容是什么，只会解析为文本
	+ v-on （@）
		+ 为元素绑定事件（click，monseenter，dbclick） v-on:click="dolt" / @click="dolt"
		+ ```<input type="button" name="" id="" value="v-on指令"v-on:click="doIt" />
			<input type="button" name="" id="" value="v-on简写" @click="doIt" />
			<input type="button" name="" id="" value="双击事件"  @dblclick="doIt" /> ```
		+ 绑定的方法定义在 methods 属性中
		+ 方法内通过 <span style="color:red">this</span>关键字可以访问定义在dta中的数据
		+ <span style="color:red">传递自定义参数，事件修饰符</span>
		+ 事件绑定的方法可以写成函数调用的形式，可以传入自定义参数
		+ 定义方法时需要定义形参来接受传入的实参
		+ 事件的后面跟上<span style="color:red">.修饰符</span>可以对事件进行限制
		+ <span style="color:red">.enter</span>可以限制触发的按键为回车
	+ v-show  <span style="color:red">操作样式（对比v-if），频繁操作推荐使用</span> 
		+ v-show 指令作用是：根据真假切换元素的显示状态
		+ 原理是修改元素的display，实现显示隐藏
		+ 指令后面的内容，最终都会解析为<span style="color:red">布尔值</span>
	+ v-if <span style="color:red">操作DOM树，比较消耗性能 </span>
		+ v-if 指令的作用是：根据表达式的真假切换元素的显示状态
		+ 本质是通过操作dom元素来切换显示状态
		+ 表达式中的值为true，元素存在于dom树中，为false，从dom树中移除
		+ 频繁的切换使用v-show，反之使用v-if，前者的切换消耗小
	+ v-bind 设置元素的属性 v-bind：属性名= 表达式
		+ 建议使用对象的方式
		+ ```<img v-bind:src="imgSrc" :title="imgTitle + '!!!'"  v-bind:class="isActive?'active':''"  @click="toggleActive">
			 <img v-bind:src="imgSrc" :title="imgTitle + '!!!'"  v-bind:class="{active:isActive}"  @click="toggleActive"> ```
		+ 完整写法 v-bind 简写 ：+属性名
	+ v-for 根据数据生成列表结构
		+ 数据经常和 v-for 结合使用
		+ 语法是 <span style="color:red">（item，index） in 数据</span>
		+ item 和 index 可以结合其他指令一起使用
		+ 数组长度的更新会同步到页面上，是响应式的
	+ v-model 获取和设置表单元素的值（<span style="color:red">双向数据绑定</span>）
		+ 作用：便捷的设置和获取表单元素的值
		+ 绑定的数据回合表单元素的值相关联
		+ 绑定的数据——表单元素的值
4. axios
	+ axios.get(地址?key=value&key2=values).then(function(response){},function(err){})
	+ axios.post(地址,{key:value,key2:values}).then(function(response){},function(err){})
	+ axios 回调函数中的 this已经改变，无法访问到data中的数据
	+ 把 this 保存起来，回调函数中直接使用保存的this 即可
	+ 和本地应用最大的区别就是改变了数据来源
	+ 想要拿到上一个方法中返回的值，只需要this.方法名() 即可 
		 