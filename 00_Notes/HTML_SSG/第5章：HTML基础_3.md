# HTML框架标签

## 简介

![image-20231105213806003](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052138060.png)

* `iframe`标签的实际应用
  * 在网页中嵌入广告
  * 与超链接或表单的`target`配合，展示不同的内容

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