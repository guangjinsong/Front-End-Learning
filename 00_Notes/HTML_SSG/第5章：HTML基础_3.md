# HTML框架标签

## 简介

![image-20231105213806003](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052138060.png)

* `iframe`标签的实际应用
  * 在网页中嵌入广告
  * 与超链接或表单的`target`配合，在当前网页展示不同的内容

## 程序

```html
<body>
    <!--利用iframe嵌入一个普通网页-->
    <iframe src="https://www.baidu.com/" width="900" height="300" frameborder="0"></iframe>
    <!--利用iframe嵌入一个本地网页-->
    <iframe src="油画.jpg" width="900" height="300" frameborder="0"></iframe>

    <!--<iframe>可以与<a>的target属性联合使用-->
    <a href="美丽的天空.jpg" target="container">点我看风景</a>
    <!--<iframe>可以与表单的target属性联合使用-->
    <form action="https://so.toutiao.com/search" target="container">
        <input type="text" name="keyword">
        <input type="submit" value="搜索">
    </form>

    <iframe name="container" frameborder="0" width="900" height="300"></iframe>
</body>
```



# 字符实体

1. **简介** 

   在 HTML 中我们可以用一种特殊的形式的内容，来表示某个符号，这种特殊形式的内容，就是 HTML 实体

2. 常见字符实体总结

   ![image-20231107205117186](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311072051245.png)

3. 程序:

   ```html
   <body>
       <div>
           qxy&nbsp;&nbsp;&nbsp;sgj
       </div>
   
       <!--下面的h1标签的大于和小于号如果不用字符实体来表示,-->
       <!--h1标签就会生效(即使没写h1的结束标签, 浏览器会帮-->
       <!--补充). 这就像编程中的转义字符一样-->
       <div>
           学习过很多标题标签, 其中<h1>是其中一个
       </div>
       <!--可以使用< 和 >对应的字符实体-->
       <div>
           学习过很多标题标签, 其中&lt;h1&gt;是其中一个
       </div>
   </body>
   ```

   > [完整实体列表](https://html.spec.whatwg.org/multipage/named-characters.html#named-character-references)

   

# 全局属性

1. 简介: 在很多标签中都能添加的属性

2. 常见的全局属性

   ![image-20231107204151406](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311072041471.png)

3. 相关程序

   ```html
    <!--全局属性: 很多标签都可以写的属性-->
   <!--id属性: 唯一的标记每个元素-->
   <div id="hello1">你好啊1</div>
   <div id="hello2">你好啊2</div>
   
   <!--class属性: 为元素分类-->
   <div class="student">sgj</div>
   <div class="student">qxy</div>
   
   <!--style属性: 样式标签-->
   <div style="color:green">大树</div>
   
   <!--dir属性: 内容方向-->
   <div dir="rtl">你是年少的欢喜</div>  <!--不改变文字的顺序, 改变阅读顺序-->
   <bdo dir="rtl">你是年少的欢喜</bdo>  <!--改变文字的顺序, 不改变阅读顺序-->
   
   <!--title属性: 鼠标悬浮在相关内容上时有相关的提示-->
   <img src="美丽的天空.jpg" title="天空">
   
   <!--lang属性: 给标签制定语言. 如果在html标签写有lang属性,那么整体会被会设置,-->
   <!--同时在body标签中的某个标签需要单独制定语言,可以单独在该标签上添加lang属性-->
   ```

   > [更多的全局属性(MDN)](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes)



# meta元信息

## 简介

1. 配置字符编码

   ```html
   <meta charset="utf-8">
   ```

2. 针对IE浏览器的兼容性配置

   ```html
   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   ```

3. 针对移动端的配置

   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

4. 配置网页关键字：当搜索引擎按照用户输入的关键字搜索时, 搜索引擎就根据网页的关键字
   决定是否展示该网页

   ```html
   <meta name="keywords" content="8-12个以英文逗号隔开的单词/词语">
   ```

5. 配置网页描述信息：让搜索引擎知道该网页是干什么的

   ```html
   <meta name="description" content="80字以内的一段话，与网站内容相关">
   ```

6. 针对搜索引擎爬虫配置

   ```html
   <meta name="robots" content="此处可选值见下表">
   ```

   ![image-20231107210327532](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311072103580.png)

7. 配置网页作者

   ```html
   <meta name="author" content="tony">
   ```

8. 配置网页生成工具

   ```html
   <meta name="generator" content="Visual Studio Code">
   ```

9. 配置网页版权信息

   ```html
   <meta name="copyright" content="2023-2027©版权所有">
   ```

10. 配置网页自动刷新

    ```html
    <meta http-equiv="refresh" content="10;url=http://www.baidu.com">
    ```



## 程序

```html
<!-- 配置字符编码 -->
<meta charset="UTF-8">
<!--针对IE浏览器的一个兼容性设置-->
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<!-- 针对移动端的配置 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- 配置网页的关键字: 当搜索引擎按照用户输入的关键字搜索时, 搜索引擎就根据网页的关键字
决定是否展示该网页-->
<meta name="keywords" content="网上购物, 电商购物">
<!-- 配置网页描述: 让搜索引擎知道该网页是干什么的 -->
<meta name="desciption" content="小玉购物网成立于2003年, 致力于打造....">

<!-- 配置网页自动刷新 -->
<meta http-equiv="refresh" content="3"> <!--三秒钟后原地刷新, 且不能回退-->
<!-- <meta http-equiv="refresh" content="3; url=https://baidu.com"> &lt;!&ndash;三秒钟后跳到百度, 且不能回退&ndash;&gt; -->
```

> [文档级元数据元素|MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)

