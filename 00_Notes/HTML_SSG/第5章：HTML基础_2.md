# 表格

## 基本结构



<img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041455545.png" alt="image-20231104145553471" class =".pics"/>

1. **表格组成：**标题、头部、主体和脚注（脚注可以不写）
2. **涉及到的标签：**
   - `table`：表格
   - `caption`：标题
   - `thead`：头部
   - `tbody`：主体
   - `tfoot`：注脚
   - `tr`：每一行
   - `th`、`td`：每一个单元格。注意，表格头部用`th`，表格主体或表格脚注用`td`

​		<img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041502200.png" alt="image-20231104150239170" style="zoom:80%;" />

​	        <img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041503232.png" alt="image-20231104150315196" style="zoom:80%;" class =".pics"/>

​		<img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041503402.png" alt="image-20231104150343358" style="zoom:80%;" />

3. **具体编码**

```html
<table>
    <!--标题-->
    <caption>学生信息</caption>

    <!--头部-->
    <thead>
        <tr>
            <th>姓名</th>
            <th>性别</th>
            <th>年龄</th>
            <th>民族</th>
            <th>政治面目</th>
        </tr>
    </thead>

    <!--主体-->
    <tbody>
        <tr>
            <td>张三</td>
            <td>男</td>
            <td>18</td>
            <td>汉族</td>
            <td>团员</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>男</td>
            <td>20</td>
            <td>满族</td>
            <td>群众</td>
        </tr>
        <tr>
            <td>王五</td>
            <td>男</td>
            <td>19</td>
            <td>回族</td>
            <td>团员</td>
        </tr>
        <tr>
            <td>赵六</td>
            <td>女</td>
            <td>26</td>
            <td>壮族</td>
            <td>团员</td>
        </tr>
    </tbody>

    <!--脚注-->
    <tfoot>
        <td></td>
        <td></td>
        <td></td>
        <td></td>
        <td>共计: 4人</td>
    </tfoot>
</table>
```

## 常用属性

### 简介

![image-20231104154016702](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041540765.png)

1. `table`

   * `border`：可以控制表格边框，但不能控值单元格边框的宽度（可以通过CSS控制）。即，只改变最外围边框的宽度。

     ​                     ![image-20231104155842388](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041558419.png)

     ​		     ![image-20231104160006407](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041600439.png)

   * `width`：改变表格的宽度

     <img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041603007.png" alt="image-20231104160345972">

     ![image-20231104160424653](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041604683.png)

   * `height`：设置表格的最小高度，表格的最终高度可能比设置的值大，而且不能改变头部和脚注的高度

     <img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041617187.png" alt="image-20231104161711146" style="zoom:80%;" />

     <img src="https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041617840.png" alt="image-20231104161745793" style="zoom: 80%;" />

   * `cellspacing`：设置单元格之间的间距

     ![image-20231104162212849](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041622887.png)

     ![image-20231104162400101](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041624137.png)

### 总结

1. 单元格间距为0于单元格合并的区别

![HTML_SGG.drawio](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311041554070.png)



2. 给某个`th`或`td`设置了宽度之后，他们所在的那一列的宽度就确定了

3. 给某个`th`或`td`设置了高度之后，他们所在的那一列的高度就确定了

   

## 跨行跨列

1. 简介：

   * `rowspan`：指定要跨的行数
   * `colspan`：指定要跨的列数

2. 实例：

   * 课程表

     ![image-20231104214428641](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311042144711.png)

   * 编写思路

     ![image-20231104214448725](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311042144761.png)

   * 代码

```html
<table border="1" cellspacing="0">
    <caption>课程表</caption>
    <thead>
        <tr>
            <th>1-1</th>
            <th colspan="5">1-2</th>
            <th colspan="2">1-8</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1-1</td>
            <td>1-2</td>
            <td>1-3</td>
            <td>1-4</td>
            <td>1-5</td>
            <td>1-6</td>
            <td>1-7</td>
            <td>1-8</td>
        </tr>
        <tr>
            <td>2-1</td>
            <td>2-2</td>
            <td>2-3</td>
            <td>2-4</td>
            <td>2-5</td>
            <td>2-6</td>
            <td>2-7</td>
            <td>2-8</td>
        </tr>
        <tr>
            <td rowspan="4">3-1</td>
            <td>3-2</td>
            <td>3-3</td>
            <td>3-4</td>
            <td>3-5</td>
            <td>3-6</td>
            <td>3-7</td>
            <td rowspan="4">3-8</td>
        </tr>
        <tr>
            <td>4-2</td>
            <td>4-3</td>
            <td>4-4</td>
            <td>4-5</td>
            <td>4-6</td>
            <td>4-7</td>
        </tr>
        <tr>
            <td>5-2</td>
            <td>5-3</td>
            <td>5-4</td>
            <td>5-5</td>
            <td>5-6</td>
            <td>5-7</td>
        </tr>
        <tr>
            <td>6-2</td>
            <td>6-3</td>
            <td>6-4</td>
            <td>6-5</td>
            <td>6-6</td>
            <td>6-7</td>
        </tr>
        <tr>
            <td rowspan="2">7-1</td>
            <td>7-2</td>
            <td>7-3</td>
            <td>7-4</td>
            <td>7-5</td>
            <td>7-6</td>
            <td>7-7</td>
            <td rowspan="2">7-8</td>
        </tr>
        <tr>
            <td>8-2</td>
            <td>8-3</td>
            <td>8-4</td>
            <td>8-5</td>
            <td>8-6</td>
            <td>8-7</td>
        </tr>
    </tbody>
</table>
```



## 补充几个常用的标签

![image-20231104215855472](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311042158515.png)

1. 不要使用`br`标签来增加文本之间的行间隔，应使用`p`标签，或`CSS`中`margin`属性
2. `hr`语义是分隔，如果不想要语义，只是想画一条水平线，那么应当使用`CSS`完成



# 表单

## 基本结构

1. 表单简介：一个包含交互的区域，用于收集用户提供的数据

   ![image-20231105110725365](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311051107453.png)

2. 示例代码

   ```html
   <form action="https://www.baidu.com/s" target="_blank">
       <input type="text" name="wd">
       <button>去百度搜索</button>
   </form>
   
   <hr>
   
   <form action="https://search.jd.com/search" target="_blank" method="get">
       <input type="text" name="keyword">
       <button>去京东搜索</button>
   </form>
   ```

3. 属性总结

   * `<form>`标签中的`action`的属性值不是通常我们认为的属性值，例如，如果使用百度搜索，那么就需要使用

     `https://www.baidu.com/s`这个带`/s`的网址（返回搜索结果），而不是`https://www.baidu.com`（不管输入的数据是什么都是返回百度的搜索页面，不返回搜索结果）

   * `<input>`标签中的`name`属性的属性值要与`<form>`标签中`action`属性所代表的网址页面的搜索框的`name`属性的属性值对应

     ![image-20231105115313190](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311051153234.png)

     ![image-20231105115258047](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311051152080.png)



## 常用表单控件

### 文本输入框

```html
<input type="text">
```

![image-20231105202147967](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052021042.png)

### 密码输入框

```html
<input type="password">
```

![image-20231105202238381](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052022416.png)

### 单选框

```html
<input type="radio" name="sex" value="female">女
<input type="radio" name="sex" value="male">男
```

![image-20231105202338060](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052023098.png)

### 复选框

```html
<input type="checkbox" name="hobby" value="reading">读书
<input type="checkbox" name="hobby" value="running">运动
<input type="checkbox" name="hobby" value="food">美食
```

![image-20231105202612565](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052026606.png)

### 隐藏域

```html
<input type="hidden" name="tag" value="100">
```

![image-20231105202657335](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052026747.png)

### 提交按钮

```html
<input type="submit" value="点我提交表单"> <!--第一种方式-->
<button>点我提交表单</button> <!--第二种方式-->
```

![image-20231105202828644](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052028683.png)

### 重置按钮

```html
<input type="reset" value="点我重置"> <!--第一种方式-->
<button type="reset">点我重置</button> <!--第二种方式-->
```



### 普通按钮

```html
<input type="button" value="普通按钮"> <!--第一种方式-->
<button type="button">普通按钮</button> <!--第二种方式-->
```

1. 普通按钮和非普通按钮的区别：如果会提交或者重置表单为普通按钮，否则是非普通按钮



### 文本域

```html
<textarea name="msg" rows="22" cols="3">我是文本域</textarea>
```

![image-20231105203619604](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052036645.png)



### 下拉框

```html
<select name="from">
    <option value="黑">黑龙江</option>
    <option value="辽">辽宁</option>
    <option value="吉">吉林</option>
    <option value="粤" selected>广东</option>
</select>
```

![image-20231105203824018](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052038065.png)



## 禁用表单控件

* 给表单控件的标签设置 `disabled` 既可禁用表单控件。

* `input`、`textarea`、button、`select`和`option`都可以设置`disabled`属性

### 

### `label`标签

* `label`标签可以表单控件相关联，关联之后点击文字，与之对应的表单控件就会获取焦点。简单来说，就是点击“文字”就可以获取焦点

* 两种与`label`关联的方式如下：

  * 让`label`标签的`for`属性的值等于表单控件的id
  * 把表单控件套在`label`标签中

* 示例代码

  ```html
  <body>
      <!--label标签：当点击“文字”时，也可以获取焦点-->
      <!--第一种方式-->
      <label for="acc">账户：</label>
      <input id="acc" type="text" name="account" value="空气炸锅" maxlength="10"> <br>
  
      <!--第二种方式-->
      <label >
          密码：
          <input type="password" name="pwd" value="123456" maxlength="10"> <br>
      </label>
  
      <!--单选框-->
      性别：
      <input id="nan" type="radio" name="sex" value="female" checked>
      <label for="nan">女</label>
      <label>
          <input type="radio" name="sex" value="male"> 男
      </label>
  </body>
  ```



### `fieldset` 与 `legend` 的使用

* `fieldset`可以为表单控件分组；`legend`是分组的标题

* 示例代码

  ```html
          <form action="https://search.jd.com/search">
             <!--主要信息-->
              <fieldset>
                 <legend>主要信息</legend>
                  <!--文本输入框-->
                  账户：
                  <input type="text" name="account" value="空气炸锅" maxlength="10"> <br>
  
                  <!--密码输入框-->
                  密码：
                  <input type="password" name="pwd" value="123456" maxlength="10"> <br>
  
                  <!--单选框-->
                  性别：
                  <input type="radio" name="sex" value="female" checked> 女
                  <input type="radio" name="sex" value="male"> 男    <br>
              </fieldset>
              <br>
  
              <!--附加信息-->
              <fieldset>
                  <legend>附加信息</legend>
                  爱好：
                  <input type="checkbox" name="hobby" value="reading" checked> 读书
                  <input type="checkbox" name="hobby" value="running" checked> 跑步
                  <input type="checkbox" name="hobby" value="food"> 美食   <br>
  
                  <!--文本域-->
                  <!--不能编写type属性，其他属性与普通文本输入框一致-->
                  其他：
                  <textarea name="msg" rows="5" cols="20">我是文本域</textarea> <br>
  
                  <!--下拉框-->
                  籍贯：
                  <select name="from">
                      <option value="济宁">济宁</option>
                      <option value="柳州">柳州</option>
                      <option value="武汉">武汉</option>
                      <option value="深圳" selected>深圳</option>
                  </select>
                  <br>
              </fieldset>
              <br>
  
              <!--提交按钮-->
              <!--两种方法都不可以写name属性-->
              <button>确定</button>   <!--提交按钮第一种写法-->
              <!--<input type="submit" value="点我提交表单">  &lt;!&ndash;提交按钮第二种写法&ndash;&gt;-->
  
              <!--重置按钮-->
              <!--两种方法都不可以写name属性-->
              <button type="reset">点我重置</button>
              <!--<input type="reset" value="点我重置">-->
  
              <!--普通按钮-->
              <button type="button">检测账户是否被注册</button> <br>
              <!--<input type="button" value="普通按钮">-->
          </form>
  ```

  

## 总结

![image-20231105205013131](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052050195.png)

![image-20231105205041011](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311052050063.png)
