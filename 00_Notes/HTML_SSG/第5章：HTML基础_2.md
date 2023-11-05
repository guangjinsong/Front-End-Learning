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
