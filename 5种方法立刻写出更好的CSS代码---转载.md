1.重置
首先，很认真的告诉你，总是要重置某些分类。无论你是使用 Eric Meyer Reset、YUI Reset
或者你自己编写的重置代码，只要使用就对了。
它能很简单的移除所有元素的填充（padding）和边距（margin）：
html, body, div, h1, h2, h3, h4, h5, h6, ul, ol, dl, li, dt, dd, p, blockquote, 
pre, form, fieldset, table, th, td { margin: 0; padding: 0; }  

Eric Meyer Reset和YUI Reset都是非常强大的，但是对于我而言，它们走的太远了。我觉得你最终需要重置一切，然后重新定义所有元素的属性。这就是为什么Eric Meyer推荐更有效的使用（重置样式表），而你不要只是使用他的重置样式表，将它拖放到你的项目中。调整它（的重置样式表），建立属于自己的重置样式表。
噢，请停止使用：
   * { margin: 0; padding: 0; } 
花更多的时间去制作它，当你移除了填充（padding）你认为单选按钮会发生什么变化？表单元素有时能够做些时髦的事情，所以最有效的方式就是将他们独立。
2.排序
一个小的测试
这个例子就是要让你思考如何更快的找到右边距属性？
Example#1
div#header h1 {  
    z-index: 101;  
    color: #000;  
    position: relative;  
    line-height: 24px;  
    margin-right: 48px;  
    border-bottom: 1px solid #dedede;  
    font-size: 18px;  
} 
Example#2
div#header h1 {
	border-bottom: 1px solid #dedede;
	color: #000;
	font-size: 18px;
	line-height: 24px;
	margin-right: 48px;
	position: relative;
	z-index: 101;
}
你不能告诉我Example#2不能更快的找到右边距属性。根据字母排序你的元素属性。一致的创建你的CSS，将帮助你节省花费在寻找一个特殊属性的时间。
我知道一些人用这样的方法去组织代码，其他人又用另一种方法去组织，但是在我的公司，我们协商一致做出决定，所有的代码都将按照字母排序来组织。通过这样组织代码与其他人协同工作一定是有帮助的。当我碰到属性没有按照字母排序的层叠样式表我每一次都会退缩。
3.组织
你应该组织你的样式表以致相关的内容靠在一起，更简单的找到想要的。使用更有效的注解。举个例子，这是我如何构造我的层叠样式表：
/*****Reset*****/
移除元素的填充（padding）和边距（margin）。

/*****Basic Elements*****/
定义基本元素的样式: body, h1-h6, ul, ol, a, p, 等.

/*****Generic Classes*****/
定义简单的风格，好像浮动的某一侧, 移除元素的下边距, 等
当然，它们大部分都与我们希望的语义不相关,但是它们是高效处理代码所必须的。

/*****Basic Layout*****/
定义基本的模板: header, footer等. 帮助定义网页布局的基本元素

/*****Header*****/
定义所有Hearder元素

/*****Content*****/
定义所有内容框内的元素

/*****Footer*****/
定义所有Footer的元素
/*****Etc*****/
定义其他的选择器。
通过注解和归类相似元素的分组，将更快的找到你想要的。
4.一致性
无论你决定使用什么方式去编写代码，保持一致。我已经对全部放在1行VS多行的CSS编写编写方式的争论感到乏味和疲倦。这是不需要争辩的。每个人都有自己的观点，所以选择一种你喜欢的工作方式，并在所有的样式表中保持一致。
就我个人而言，我将使用两者结合的方式。如果一个选择器超过了3个属性，我将截断它采用多行的方式编写。
div#header { float: left; width: 100%; }  
div#header div.column {  
    border-right: 1px solid #ccc;  
    float: rightright;  
    margin-right: 50px;  
    padding: 10px;  
    width: 300px;  
}  
div#header h1 { float: left; position: relative; width: 250px; }  
所以找到你喜欢的工作方式然后保持一致。
 
5.从正确的地方开始
在完成标记语言之前不要去尝试靠近你的样式表。
当我准备分割一张网页的时候，创建CSS文件之前，我需要预览并且标记body开标签到body的闭合标签之间的所有文档。我不会增加额外的DIV ,ID,或者类选择器。我将会添加一些一般的DIV，就好像hearder、content、footer.因为我知道这些东西是现实存在的。
通过先标记文档，你将不会碰到本已注定的divities1和classitis2麻烦!/*You only need to add in that stuff once you have begun to write the CSS and realize that you are going to need another hook to accomplish what you are trying to achieve.*/(原文未译）。
利用CSS子选择器指定子元素；不要只是机械的给元素添加类或者ID选择器。记住：没有一个良好的格式化文档（或者标记结构）CSS是无价值的。
总结
这些Tips能够帮助我更好的完成CSS代码的编写。但是这并不意味着这张列表的结束，接下来我将会去带来一些其他的与大家分享。
你有什么更好的Tips帮助我们完善CSS代码？
