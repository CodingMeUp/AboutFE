# jQuery 复习--by 传智前端与移动开发学院

## 1. jQuery是什么？(了解)
+ www.github.com
+ jQuery 其实就是一堆的js函数，是普通的js，只不过应用广泛，形成了行业标准。
+ 参考书：锋利的jQuery
+ 学习参考：http://www.w3school.com.cn/jquery/
+ 官网：http://jquery.com/
+  <img src="" >

##2. jQuery的重点
+ 2.1 jQuery入口函数(全球都会)
+ 2.2 jQuery的选择器(其实就是CSS的选择器)
+ 2.3 jQuery的Dom操作
+ 2.4 jQuery的样式操作
+ 2.5 jQuery的动画
+ 2.6 jQuery的事件处理


## 3.jQuery的入口函数
+ 3.1 语法
    * jQuery(document).read(function(){  });
    * $(function(){ });// **
    * window.onlaod = function(){}
    * $ === jQuery // $是jQuery全局函数的别名。
+ 3.2注意事项： **（重点）**
    * document ready:  是html文档准备就绪，也就是dom树创建完成了。可以进行dom操作了。     
     *重要的是：html页面下载完成，并准备就绪*
    
    * window.onload: 是整个页面所有的资源都加载完成，图片、js、css等...

+ 3.3 文档加载顺序： **（重点）**         
    - 下载html页面，解析html标签，遇到link标签加载css，遇到script加载js..

## 4. jQuery 选择选取元素
### 4.1 jQuery选择器
+ 4.1.1 ID选择器（js一般尽量用ID选择器，效率最高） **（重点）**
    * $("#id").html();
+ 4.1.2 类选择器 **（重点）**
    * $(".className").text();
+ 4.1.3 标签选择器 **（重点）**
    * $('p').click();
+ 4.1.4 属性选择器
    * $("li[id]")、 $("li[id='link']").fadeIn();
+ 4.1.5 层级选择器 **（重点）**
    * $("li .link").show();
+ 4.1.6 父子选择器
    * $("ul > li")
+ 4.1.7 伪类选择器
    * $("p:first") 
    * $("ul li:eq(3)")
+ 4.1.8 表单选择器
    *  $(":text") 
    *  $(":checkbox")
    *  $(":checked")
    
### 4.2 选择器汇总
```
*               $("*")              所有元素
#id             $("#lastname")      id="lastname" 的元素
.class          $(".intro")         所有 class="intro" 的元素
element         $("p")              所有 <p> 元素
.class.class    $(".intro.demo")    所有 class="intro" 且 class="demo" 的元素
```

```         
:first  $("p:first")    第一个 <p> 元素
:last   $("p:last")     最后一个 <p> 元素
:even   $("tr:even")    所有偶数 <tr> 元素
:odd    $("tr:odd")     所有奇数 <tr> 元素
```

```           
:eq(index)      $("ul li:eq(3)")    列表中的第四个元素（index 从 0 开始）
:gt(no)         $("ul li:gt(3)")    列出 index 大于 3 的元素 greater than
:lt(no)         $("ul li:lt(3)")    列出 index 小于 3 的元素 less than
:not(selector)  $("input:not(:empty)")  所有不为空的 input 元素
         
:header         $(":header")        所有标题元素 <h1> - <h6>
:animated       所有动画元素
```

```            
:contains(text)     $(":contains('W3School')")  包含指定字符串的所有元素
:empty              $(":empty")                 无子（元素）节点的所有元素
:hidden             $("p:hidden")               所有隐藏的 <p> 元素
:visible            $("table:visible")          所有可见的表格
         
s1,s2,s3            $("th,td,.intro")            所有带有匹配选择的元素
```

```            
[attribute]         $("[href]")         所有带有 href 属性的元素
[attribute=value]   $("[href='#']")     所有 href 属性的值等于 "#" 的元素
[attribute!=value]  $("[href!='#']")    所有 href 属性的值不等于 "#" 的元素
[attribute$=value]  $("[href$='.jpg']") 所有 href 属性的值包含以 ".jpg" 结尾的元素
```

```            
:input      $(":input")         所有 <input> 元素
:text       $(":text")          所有 type="text" 的 <input> 元素
:password   $(":password")      所有 type="password" 的 <input> 元素
:radio      $(":radio")         所有 type="radio" 的 <input> 元素
:checkbox   $(":checkbox")      所有 type="checkbox" 的 <input> 元素
:submit     $(":submit")        所有 type="submit" 的 <input> 元素
:reset      $(":reset")         所有 type="reset" 的 <input> 元素
:button     $(":button")        所有 type="button" 的 <input> 元素
:image      $(":image")         所有 type="image" 的 <input> 元素
:file       $(":file")          所有 type="file" 的 <input> 元素
```

```            
:enabled    $(":enabled")   所有激活的 input 元素
:disabled   $(":disabled")  所有禁用的 input 元素
:selected   $(":selected")  所有被选取的 input 元素
:checked    $(":checked")   所有被选中的 input 元素
```


### 4.3 jQuery选择方法
+ 4.3.1 获取父级元素
```
    * $(selector).parent();     //获取直接父级
    * $(selector).parents('p'); //获取所有父级元素直到html   
```

+ 4.3.2 获取子代和后代的元素
```
    * $(selector).children();   //获取直接子元素
    * $(selector).find("span"); //获取所有的后代元素
    * find方法 可能用的多。
```

+ 4.3.3 获取同级的元素
```
    * $(selector).siblings()    //所有的兄弟节点
    * $(selector).next()        //下一个节点
    * $(selector).nextAll()     //后面的所有节点
    * $(selector).prev()        //前面一个的兄弟节点
    * $(selector).prevAll()     //前面的所有的兄弟节点
```

+ 4.3.4 过滤方法
```
    * $("div p").last();        //取最后一个元素
    * $("div p").first();       //取第一个元素
    * $("p").eq(1);             //去第n个元素
    * $("p").filter(".intro");  //过滤，选择所有p标签带有 .intro类
    $('p.intro')
    * $("p").not(".intro");     //去除，跟上面的filetr正好相反
```

## 5.jQuery的Dom操作
### 5.1 获取html的内容
    $(selector).text() - 设置或返回所选元素的文本内容
    $(selector).html() - 设置或返回所选元素的内容（包括 HTML 标记）
    $(selector).val()  - 设置或返回表单字段的值
+ 获取和设置相同方法名,通过不同参数来确定是获取还是设置值
```
    $("#blin").text("传智播客");
    var txt = $("#blin").text();
```

+ 使用html来创建dom的方式效率比较高。  远大于： document.createElement();

+ 案例：02动态创建表格.html

### 5.2 样式操作
+ 5.2.1 基本样式操作
```
    $(selector).css("color","red") |css({})  设置或返回匹配元素的样式属性。
    $(selector).height()        设置或返回匹配元素的高度。
    $(selector).offset().left   => { left:99, top: 22}     返回第一个匹配元素相对于文档的位置。left,top
    $(selector).offsetParent()  返回最近的定位祖先元素。
    $(selector).position()      返回第一个匹配元素相对于父元素的位置。
    $(window).scrollLeft()    设置或返回匹配元素相对滚动条左侧的偏移。
    $(window).scrollTop(0)     设置或返回匹配元素相对滚动条顶部的偏移。
    <!-- onscroll -->
    $(selector).on("scroll",function(){});

    $(selector).width()         设置或返回匹配元素的宽度。
```
+ 5.2.2 样式类操作*尽量操作样式类，少直接操作css属性*
```
    $(selector).addClass('class');     向匹配的元素添加指定的类名。
    $(selector).removeClass('class');  从所有匹配的元素中删除全部或者指定的类。
    $(selector).toggleClass('class')   从匹配的元素中添加或删除一个类。
    $(selector).hasClass('class')      检查匹配的元素是否拥有指定的类。
```

### 5.3 属性操作
```
    $(selector).attr("id")      设置或返回匹配元素的属性和值
    $(selector).removeAttr()从所有匹配的元素中移除指定的属性。
```
### 5.4 动态创建
```
    $(selector).append()    - 在被选元素的结尾插入内容
        $(selector).append(node) 
        $(selector).append('<div></div>')    
    $(selector).appendTo(); - 追加到..



    $(selector).prepend()   - 在被选元素的开头插入内容
    $(selector).after()     - 在被选元素之后插入内容
    $(selector).before()    - 在被选元素之前插入内容
```
案例04城市选择案例.html

## 6. 事件处理
### 6.1 简单事件绑定方法
+ .click(hander)  .click() //绑定事件 或者触发 click事件
+ .blur()  //失去焦点事件，同上
+ .hover(mousein, mouseleave) //鼠标移入，移出

+ mouseout： 当鼠标离开元素及它的子元素的时都会触发。
+ 
+ mouseleave: 当鼠标离开自己时才会触发，子元素不触发。

+ .dbclick() 双击
+ change 改变,比如：文本框发送改变，下来列表发生改变等...
+ focus 获得焦点
+ keyup, keydown, keypress :  键盘 键被按下。
+ mousedown, mouseover         

### 6.2 绑定事件的方式 bind方式（不推荐，1.7以后的jQuery版本被on取代）
+ 语法格式：.bind( eventType [, eventData ], handler )   
+ 参数说明
   * 第一个参数：事件类型
   * 第二个参数：传递给事件响应方法的数据对象，可以省略。
   * 事件响应方法中获取数据方式： e.data
   * 第三个参数：事件响应方法
   **第二个参数可以省略。**

```
    例如：    
    $("p").bind("click", function(e){
        //事件响应方法
    });

    $("p").on('click',function(e){
        //事件响应方法
    })
```


### 6.3 delegate方式（推荐，性能高，支持动态创建的元素）
    * 语法格式：$(selector).delegate( selector, eventType, handler )
    * 语法说明：
        - 第一个参数:selector， 子选择器
        - 第二个参数：事件类型
        - 第三个参数：事件响应方法

    ```
        例如：   
        $(".parentBox").delegate("p", "click", function(){
            //为 .parentBox下面的所有的p标签绑定事件
        });

        $(".parentBox").on("click","p", function(){
            //为 .parentBox下面的所有的p标签绑定事件
        });
    ```
    *优势：效率较高*

### 6.4  one绑定一次事件的方式
    * .one( events [, data ], handler )
```
    例如：
    $( "p" ).one( "click", function() {
      alert( $( this ).text() );
    });

    $("p").on("click",function(){
        $(this).off('click');//事件方法执行了一次后，就立即解绑事件
    })
```


### 6.5 on绑定的方式（整合了bind、delegate  烈建议使用的方式））
+ jQuery1.7版本后，jQuery用on统一了所有的事件处理的方法
+ 语法格式：$(selector).on( events [, selector ] [, data ], handler )
+ 参数介绍：
    * 第一个参数：events，事件名
    * 第二个参数：selector,类似delegate
    * 第三个参数: 传递给事件响应方法的参数
    * 第四个参数：handler，事件处理方法
```
    例如：
    //绑定一个方法
    $( "#dataTable tbody tr" ).on( "click", function() {
      console.log( $( this ).text() );
    });

    //给子元素绑定事件
    $( "#dataTable tbody" ).on( "click", "tr", function() {
      console.log( $( this ).text() );
    });

    //绑定多个事件的方式
    $( "div.test" ).on({
      click: function() {
        $( this ).toggleClass( "active" );
      }, mouseenter: function() {
        $( this ).addClass( "inside" );
      }, mouseleave: function() {
        $( this ).removeClass( "inside" );
      }
    });
```

### 6.6 解绑
+ unbind解绑 bind方式绑定的事件( 在jQuery1.7以上被 on和off代替)
    * $(selector).unbind();         //解绑所有的事件
    * $(selector).unbind("click");  //解绑指定的事件

+ undelegate解绑delegate事件
    * $( "p" ).undelegate();            //解绑所有的delegate事件
    * $( "p" ).undelegate( "click" );   //解绑所有的click事件

+ off解绑on方式绑定的事件
    * $( "p" ).off();
    * $("P").off('click');
    * $( "p" ).off( "click", "**" );    // 解绑所有的click事件，两个\*表示所有
    * $( "body" ).off( "click", "p", foo );  
    
### 6.7 触发事件

+ 6.7.1 简单事件触发
    * $(selector).click(); //触发 click事件
+ 6.7.2 trigger方法触发事件
    * $( "#foo" ).trigger( "click" );
+ 6.7.3 triggerHandler触发 事件响应方法，不触发浏览器行为
    * $( "input" ).triggerHandler( "focus" );
    
### 6.8 event对象的简介
+ event.data            //传递的额外事件响应方法的额外参数

+ event.currentTarget === this   //在事件响应方法中等同于this，当前Dom对象

+ **event.target **         //事件触发源，不一定===this

+ **event.pageX**           //The mouse position relative to the left edge of the document
+ **event.pageY**

+ **event.stopPropagation()**//阻止事件冒泡
+ **e.preventDefault();**    //阻止默认行为

+ event.type                 //事件类型：click，dbclick...
+ event.which                //鼠标的按键类型：左1 中2 右3
+ keydown : a,b,c
+ event.keyCode// code的c是大写

## 7. jQuery动画系统
### 7.1隐藏显示
    * $(selector).show(speed,callback);
    * $(selector).hide(1000);
    * $(selector).toggle("slow");
    
    * 三个方法的语法都一致，参数可以有两个，第一个是动画的速度，第二个是动画执行完成后的回调函数。
    * 第一个参数是：可以是单词或者毫秒数
### 7.2淡入淡出

    $(selector).fadeIn(speed, callback)
    $(selector).fadeOut(1000)
    $(selector).fadeToggle('fast',function(){})
    参数等同于 7.1

    * $(selector).fadeTo(.5); //淡入到  0透明，1不透明

### 7.3滑动
    * $(selector).slideDown(speed,callback);
    * $(selector).slideUp(speed,callback);
    * $(selector).slideToggle(speed,callback);
### 7.4动画
    * $(selector).animate({params},speed,callback);
```
    $("button").click(function(){
      $("div").animate({
        left:'250px',
        opacity:'0.5',
        height:'150px',
        width:'150px'
      },2000);
    }).animate({},1000); 
```


### 7.5结束动画
    * $(selector).stop()
    * $(selector).stop(stopAll,goToEnd);
+ 案例：

## 8. jQuery补充
+ 8.1 each函数
    * 全局的
        - $.each(array, function(index, object){})
    * 普通jQuery对象的each方法
        - $("li").each(function(index, element){} )
        - 参数的顺序是一致的。
