# jQuery功能总结
## 1.获取元素
* 选择表达式可以是CSS选择器
  ```JavaScript
  $(document) //选择整个文档对象
  $('idName')//选择ID的名字
  $('div.nameClass') // 选择class为nameClass的div元素
  $('input[name=first]') // 选择name属性等于first的input元素
  ```
* 也可以是jQuery特有的表达式
  ```JavaScript
  $('a:first') //选择网页中第一个a元素
  $('tr:odd') //选择表格的奇数行
  $('#myForm :input') // 选择表单中的input元素
  $('div:visible') //选择可见的div元素
  $('div:gt(2)') // 选择所有的div元素，除了前三个
  $('div:animated') // 选择当前处于动画状态的div元素
  ```
## 2.链式操作
* 选中网页元素以后，可以对它进行一系列操作，并且所有操作可以连接在一起，以链条的形式写出来，比如：
```JavaScript
$('div') //找到div元素
.find('p3') //选择其中的p3元素
.eq(2) //选择第3个p3元素
.html('Hello,I am LLW'); //将它的内容改为Hello,I am LLW
```
jQuery还提供了.end()的方法，目的是使结果能退到前一步的oldApi上进行操作
```JavaScript
$('div')
.find('p3')
.eq(2)
.html('Hello,I am LLW')
.end() //退回到选中所有的p3元素的那一步
.eq(0) //选中第一个p3元素
.html('World'); //将它的内容改为World
```
## 3.创建元素
* 创建新元素的方法较为简单，只要把新元素直接传入jQuery的构造函数就行了：
```JavaScript
$('<p>Hello</p>');
$('<div class="LLW">I am LLW</div>');
```
## 4.移动元素
* jQuery提供两组方法，来操作元素在网页中的位置移动。一组方法是直接移动该元素，另一组方法是移动其他元素，使得目标元素达到我们想要的位置。
```JavaScript
  .insertAfter()和.after()//在现存元素的外部，从后面插入元素
   $( "<p>Test</p>" ).insertAfter( ".inner" )
   $( ".inner" ).after("<p>Test<p>")
   //以上两者在用法上还是存在先后顺序的区别

//下面这三组类似用法
.insertBefore()和.before()//在现存元素的外部，从前面插入元素

　　.appendTo()和.append()//在现存元素的内部，从后面插入元素

　　.prependTo()和.prepend()//在现存元素的内部，从前面插入元素
```
## 5.修改元素属性
首先需获取对应的函数，再用链式结果调用addClass函数
```JavaScript
jQuery('.test').addClass('red')
```