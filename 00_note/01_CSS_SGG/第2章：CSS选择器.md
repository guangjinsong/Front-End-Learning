# 1. 选择器分类

* 基本选择器

  1. 通配选择器

  2. 元素选择器

  3. 类选择器

  4. id选择器

* 复合选择器
  1. 交集选择器
  2. 并集选择器
  3. 后代选择器
  4. 子元素选择器
  5. ......

* 总结
  1. 复合选择器建立在基本选择器之上, 由多个基础选择器通过不同的方式组合而成
  2. 复合选择器可以在复合结构中, 快速而准确的选中元素



# 2. 基本选择器

## 2.1. 通配选择器

* **作用**

  * 可以选中所有的HTML元素

* **语法**

  ```css
  * {
  	属性名: 属性值;
  }
  ```

* **总结**
  1. 一般用来清除样式

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>01_通配选择器</title>
          <style>
              * {
                  color: red;
                  font-size: 40px;
              }
          </style>
      </head>
      <body>
          <h1>欢迎来到土味官网, 土的味道我知道</h1>
          <h2>土味情话</h2>
          <h3>作者: 优秀的网友们</h3>
          <p>万水千山总是情, 爱我多点行不行!</p>
          <p>草莓, 蓝莓, 蔓越莓, 今天你想我了没?</p>
          <p>我心里给你留了一块地, 我的死心塌地</p>
  
      </body>
  </html>
  ```



## 2.2. 元素选择器

* **作用**

  * 为页面中某种元素统一设置样式

* **语法**

  ```css
  标签名 {
  	属性名: 属性值;
  }
  ```

* **总结**

  * 元素选择器无法实现差异化设置，例如上面个的代码中， 所有的p元素效果一样

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8">
      <title>02_元素选择器</title>
      <style>
        h1 {
          color: bisque;
        }
        h2 { /*元素选择器*/
          color: aqua;
        }
        h3 {
          color: antiquewhite;
        }
        p {
          color: green;
        }
      </style>
    </head>
    <body>
      <h1>欢迎来到土味官网, 土的味道我知道</h1>
      <h2>土味情话</h2>
      <h3>作者: 优秀的网友们</h3>
      <p>万水千山总是情, 爱我多点行不行!</p>
      <p>草莓, 蓝莓, 蔓越莓, 今天你想我了没?</p>
      <p>我心里给你留了一块地, 我的死心塌地</p>
      <br>
      <h2>反杀土味情话</h2>
      <h3>作者: 更优秀的网友们</h3>
      <p>一寸光阴一寸金, 劝你死了这条心</p>
      <p>西瓜, 南瓜, 哈密瓜, 把你打成大傻瓜</p>
      <p>我的心里只有一块地, 我的玛莎拉蒂</p>
    </body>
  </html>
  ```



## 2.3. 类选择器

* **作用**

  * 根据元素的class值，来选中某些元素

* **语法**

  ```css
  .类名 {
      属性名: 属性值;
  }
  ```

* **总结**    

  * 元素的class属性值不带`.`，但定义类选择器要带`.`

  * class值，是我们自定义的，按照标准：不要使用纯数字，不要使用使用中文，尽量使用英文于数字的组合，若由多个单词组成，使用`.`做连接，例如：`left-menu`，且命名要有意义，做到见名知意

  * 一个元素不可以写多个class属性，错误示例如下

    ```html
    <!-- 该写法错误，元素的属性不能重复，后写的会失效 -->
    <h1 class="speak" class="big">你好啊</h1>
    ```

  * 一个元素的class属性可以写多个值，要用空格隔开，例如：

    ```html
    <!-- 该写法正确，class属性，能写多个值 -->
    <h1 class="speak big">你好啊</h1>
    ```

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>03_类选择器</title>
          <style>
              .speak {
                  color: aqua;
              }
              .answer {
                  color: green;
              }
              .big {
                  font-size: 50px;
              }
          </style>
      </head>
      <body>
          <h1>欢迎来到土味官网, 土的味道我知道</h1>
          <h2>土味情话</h2>
          <h3>作者: 优秀的网友们</h3>
          <!-- 一个标签里不可以多个相同的属性, 但一个属性可以有多个值, 多个值中间有空格 如下 -->
          <p class="speak big">我对你说: 万水千山总是情, 爱我多点行不行!</p>
          <p class="speak">我对你说: 草莓, 蓝莓, 蔓越莓, 今天你想我了没?</p>
          <p class="speak">我对你说: 我心里给你留了一块地, 我的死心塌地</p>
          <br>
          <h2>反杀土味情话</h2>
          <h3>作者: 更优秀的网友们</h3>
          <p class="answer">你回答我: 一寸光阴一寸金, 劝你死了这条心</p>
          <p class="answer">你回答我: 西瓜, 南瓜, 哈密瓜, 把你打成大傻瓜</p>
          <p class="answer">你回答我: 我的心里只有一块地, 我的玛莎拉蒂</p>
  
      </body>
  </html>
  ```



## 2.4. id选择器

* **作用**

  * 根据元素的id属性值，来精准第选中某个元素

* **语法**

  ```css
  #id值 {
  	属性名: 属性值;
  }
  ```

* **总结**

  * id 属性值：尽量由**字母、数字、下划线（_）、短杠(** **-** **)**组成，最好以字母开头、不要包含空格、区分大小写
  * 一个元素只能拥有一个 id 属性，多个元素的 id 属性值不能相同
  * 一个元素可以同时拥有 id 和 class 属性

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>04_id选择器</title>
          <style>
            #earthy {
              color: red;
            }
            #turn-earthy {
              color: aqua;
            }
            .speak {
              font-size: 60px;
            }
          </style>
      </head>
      <body>
        <!-- 可以同时拥有class和id属性 -->
        <h1 id="earthy" class="speak">欢迎来到土味官网, 土的味道我知道</h1>
        <h2>土味情话</h2>
        <h3>作者: 优秀的网友们</h3>
        <p>万水千山总是情, 爱我多点行不行!</p>
        <p>草莓, 蓝莓, 蔓越莓, 今天你想我了没?</p>
        <p>我心里给你留了一块地, 我的死心塌地</p>
        <br>
        <h2 id="turn-earthy">反杀土味情话</h2>
        <h3>作者: 更优秀的网友们</h3>
        <p>一寸光阴一寸金, 劝你死了这条心</p>
        <p>西瓜, 南瓜, 哈密瓜, 把你打成大傻瓜</p>
        <p>我的心里只有一块地, 我的玛莎拉蒂</p>
      </body>
  </html>
  ```



## 2.5. 基本选择器总结

| 基本选择器 |                        特点                         |         用法          |
| :--------: | :-------------------------------------------------: | :-------------------: |
| 通配选择器 |           选中所有标签，一般用于清除样式            |    `* {color:red}`    |
| 元素选择器 |        选中所有同种标签，但是不能差异化选择         |   `h1 {color:red}`    |
|  类选择器  | 选中所有特定类名（ class 值）的元素 —— 使用频率很高 |  `.say {color:red}`   |
| ID 选择器  |         选中特定 id 值的那个元素（唯一的）          | `#earthy {color:red}` |



# 3. 复合选择器

## 3.1. 交集选择器

* **作用**
  
  * 选中同时复合多个条件的元素
  
* **语法**

  ```css
  选择器1选择器2选择器3...选择器n {}
  ```

* **总结**

  * 有标签名，标签名必须写在前面。

  * id 选择器、通配选择器，理论上可以作为交集的条件，但实际应用中几乎不用 —— 因为没

    有意义

  * 交集选择器中**不可能**出现**两个元素选择器**，因为一个元素，不可能即是 p 元素又是 span 元素
  * 用的最多的交集选择器是：元素选择器配合类名选择器，例如： `p.beauty` 

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>01_交集选择器</title>
          <style>
              .rich {
                  color: gold;
              }
              .beauty {
                  color: red;
              }
              p.beauty {
                  color: green;
              }
              /*id选择器一般不写*/
              p.beauty#pq {
                  color: darkmagenta;
              }
              .rich.beauty {
                  color: orange;
              }
          </style>
      </head>
      <body>
          <h2 class="rich"> 土豪张三 </h2>
          <h2 class="beauty"> 明星李四 </h2>
          <h2 class="rich beauty">土豪明星王五</h2>
          <hr>
          <p class="beauty" id="wc">小狗旺财</p>
          <p class="beauty" id="pq">小猪佩奇</p>
      </body>
  </html>
  ```



## 3.2. 并集选择器

* **作用**
  * 选中多个选择器对应的元素，又称：**分组选择器**

* **语法**

  ```css
  选择器1, 选择器2, 选择器3, ... 选择器n {}
  ```

* **总结**
  * 并集选择器，我们一般竖着写。
  * 任何形式的选择器，都可以作为并集选择器的一部分 。
  * 并集选择器，通常用于集体声明，可以缩小样式表体积

* **举例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>02_并集选择器</title>
          <style>
              .rich {
                  color: gold;
              }
              .beauty {
                  color: red;
              }
              .dog {
                  color: blue;
              }
              .pig {
                  color: pink;
              }
              .rich,
              .beauty,
              .dog,
              .pig {
                  font-size: 40px;
                  background: orange;
                  width: 200px;
              }
          </style>
      </head>
      <body>
          <h2 class="rich"> 土豪张三 </h2>
          <h2 class="beauty"> 明星李四 </h2>
          <h2 >破产王五(不加任何样式)</h2>
          <hr>
          <p class="dog">小狗旺财</p>
          <p class="pig">小猪佩奇</p>
      </body>
  </html>
  ```



## 3.3. HTML元素间的关系

### 3.3.1. 分类

1. 父元素
2. 子元素
3. 祖先元素
4. 后代元素
5. 兄弟元素



### 3.3.2. 父元素

* **简介**
  * 直接包裹某个元素的元素，就是该元素的父元素

* **举例**

  ![image-20231114160219745](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141602843.png)



### 3.3.3. 子元素

* **简介**

  * 被父元素**直接**包含的元素（简记：儿子元素）

* **举例**

  ![image-20231114160307899](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141603955.png)



### 3.3.4. 祖先元素

* **简介**

  * 父亲的父亲......，一直往外找，都是祖先
  * 父元素，也算是祖先元素的一种

* **举例**

  ![image-20231114160358157](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141603210.png)



### 3.3.5. 后代元素

* **简介**

  * 儿子的儿子......，一直往里找，都是后代
  * 子元素，也算是后代元素的一种

* **举例**

  ![image-20231114160440504](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141604562.png)



### 3.3.6. 兄弟元素

* **简介**

  * 具有相同父元素的元素，互为兄弟元素

* **举例**

  ![image-20231114160538662](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141605716.png) 



## 3.4. 后代选择器

* **简介**
  * 选中指定元素中，符合要求的后代元素

* **语法**
  * 选择器1 选择器2 选择器3 ...... 选择器n {} （先写祖先，再写后代）
  * 选择器之间，用空格隔开，空格可以理解为：" xxx 中的"，其实就是后代的意思
  * 选择器 1234....n ，**可以是我们之前学的任何一种选择器**。

* **总结**

  * 后代选择器，最终选择的是后代，不选中祖先
  * 儿子、孙子、重孙子，都算是后代
  * 结构一定要符合之前讲的 HTML 嵌套要求，例如：不能 p 中写 `h1 ~ h6` 

* **程序**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>03_后代选择器</title>
          <style>
              /*ul后代元素名为li的元素*/
              ul li {
                  color: red;
              }
              ul li a {
                  color: orange;
              }
              ol li {
                  color: green;
              }
              ol li a {
                  color: pink;
              }
              .subject li {
                 color: aqua;
              }
              .subject #front-end {
                  color: darkmagenta;
              }
              .subject li.front-end {
                  color: gold;
              }
              .subject li#front-end {
                  color: bisque;
              }
          </style>
      </head>
      <body>
          <ul>
              <li>读书</li>
              <li>运动</li>
              <li>
                  <a href="#">美食</a>
              </li>
          </ul>
          <hr>
          <ol>
              <li>张三</li>
              <li>李四</li>
              <li>王五</li>
          </ol>
          <hr>
          <ol class="subject">
              <li class="front-end">前端</li>
              <li id="front-end">学科介绍: 学好前端, 挂帅扬帆! </li>
              <li>java</li>
              <li>python</li>
          </ol>
          <hr>
  
          <!-- <p>标签中不能写<h1>到<h6>的标签-->
          <p>
              <h2>hello</h2>
          </p>
  
      </body>
  </html>
  ```



## 3.5. 子代选择器

* **简介**
  * 选中指定元素中，符合要求的**子**元素（**儿子元素**）
  * 子代选择器又称：子元素选择器、子选择器
* **语法**
  * 选择器1 > 选择器2 > 选择器3 > ...... 选择器n {}
  * 选择器之间，用 > 隔开， > 可以理解为：" xxx 的子代"，其实就是儿子的意思
  * 选择器 1234....n ，可以是我们之前学的任何一种选择器。

* **总结**

  * 子代选择器，最终选择的是子代，不是父级。

  * 子、孙子、重孙子、重重孙子 ...... 统称后代！，这里的**子**就是指**儿子**

    ![image-20231115164002717](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311151640799.png) 

* **程序** 

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>04_子代选择器</title>
          <style>
              /*这里的子是指儿子,不是其他子 */
              div>a {
                  color: pink;
              }
              div>p>a {
                  color: gold;
              }
          </style>
      </head>
      <body>
          <div>
              <a href="#">张三</a>
              <a href="#">李四</a>
              <a href="#">王五</a>
              <p>
                  <a href="#">赵六</a>
              </p>
          </div>
      </body>
  </html>
  ```



## 3.6. 兄弟选择器

### 3.6.1. 相邻兄弟选择器

* **简介**
  * 选中指定元素后，符合条件的**相邻兄弟**元素
  * 所谓相邻，就是**紧挨着**他的下一个，简记：睡在我下铺的兄弟
* **语法**
  * 选择器1+选择器2 {} 

### 3.6.2. 通用兄弟选择器

* **简介**
  * 选中指定元素后，符合条件的**所有兄弟**元素
  * 简记：睡在我下铺的所有兄弟
* **语法**
  * 选择器1~选择器2 {}
* **总结**
  * 两种兄弟选择器，选择的是**下面**的兄弟

* **程序**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>05_兄弟选择器</title>
          <style>
              /*选择div后紧紧相邻向下p元素的兄弟(睡在我下铺的兄弟) - 相邻兄弟选择器*/
              div+p {
                  color: gold;
              }
              /*选中div后所有的兄弟p元素(睡在我下铺的所有的兄弟) - 通用兄弟选择器*/
              div~p {
                  color: red;
              }
              li+li {
                  color: bisque;
              }
          </style>
      </head>
      <body>
          <p>前端</p>
          <div>尚硅谷</div>
          <p>Java</p>
          <p>大数据</p>
          <p>UI</p>
          <ul>
              <li>主页</li>
              <li>秒杀</li>
              <li>订单</li>
              <li>我的</li>
          </ul>
      </body>
  </html>
  ```



## 3.7. 属性选择器

* **简介**

  * 选中属性值符合一定要求的元素

* **语法**

  1. [属性名] 选中**具有**某个属性的元素

  2. [属性名="值"] 选中包含某个属性，且属性值**等于**指定值的元素

  3. [属性名^="值"] 选中包含某个属性，且属性值以指定的值**开头**的元素

  4. [属性名$="值"] 选中包含某个属性，且属性值以指定的值**结尾**的元素

  5. [属性名*=“值”] 选择包含某个属性，属性值**包含**指定值的元素

* **程序**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>06_属性选择器</title>
          <style>
              /*第一种写法: 选中具有title属性的元素*/
              [title] {
                  color: red;
              }
              /*第二种写法: 选中具有title属性, 且属性值为guigu3的元素*/
              [title="guigu3"] {
                  color: gold;
              }
              /*第三种写法: 选中具有title属性, 且属性值以字母a开头的元素*/
              [title^="a"] {
                  color: pink;
              }
              /*第四种写法: 选中具有title属性, 且属性值以字母u结尾的元素*/
              [title$="4"] {
                  color: blue;
              }
              /*第五种写法: 选中具有title属性, 且属性值包含字母u的元素*/
              [title*="4"] {
                  color: blue;
              }
  
  
          </style>
      </head>
      <body>
          <div title="atguigu1">尚硅谷1</div>
          <div title="atguigu2">尚硅谷2</div>
          <div title="guigu3">尚硅谷3</div>
          <div title="guigu4">尚硅谷4</div>
      </body>
  </html>
  ```



## 3.8. 伪类选择器

### 3.8.1. 概念

* **简介**

  * 选中特殊状态的元素
  * 伪” ? — 虚假的，不是真的
  * 解“伪类”？ — 像类( class )，但不是类，是元素的一种特殊状态

* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>07_伪类选择器_概念</title>
          <style>
              /*伪类很像类,但不是类, 是元素特殊状态的一种描述*/
              /*选择的是没有访问过的a元素*/
              a:link {
                  color: gold;
              }
              /*选择的是访问过的a元素*/
              a:visited {
                  color: pink;
              }
          </style>
      </head>
      <body>
          <a href="https://www.baidu.com/">去百度</a>
          <a href="https://www.jd.com/">去京东</a>
      </body>
  </html>
  ```




### 3.8.2. 动态伪类

* **分类**
  1. `:link` : 超链接**未被访问**的状态。
  2. `:visited` : 超链接**访问过**的状态。
  3. `:hover` : 鼠标**悬停**在元素上的状态。
  4. `:active` : 元素**激活**的状态
  5. `:focus`: 获取焦点的元素
  
* **总结**
  
  * 激活: 按下鼠标不松开
  * 遵循 LVHA 的顺序，即： link 、 visited 、 hover 、 active 
  * 表单类元素才能使用 :focus 伪类
  * 当用户户点击元素、触摸元素、或通过键盘的 “ tab ” 键等方式，选择元素时，就是获得焦点
  
* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>08_伪类选择器_动态伪类</title>
        <style>
          /*1. 下面四个选择器的顺序不可以变*/
          /*2. link和visited是a标签独有的状态*/
          /*选择的是没有访问过的a元素*/
          a:link {
            color: gold;
          }
          /*选择的是访问过的a元素*/
          a:visited {
            color: pink;
          }
          /*选中的是鼠标悬浮状态的a元素*/
          a:hover {
            color: darkmagenta;
          }
          /*选中的是激活状态(鼠标左键点击不动状态)的a元素*/
          a:active {
            color: aqua;
          }
  
          /*1. focus只有表单类元素可以用, 即可以进行输入的, 例如select input*/
          /*2. focus: 获取焦点(只要使该元素处于输入状态)*/
          input:focus, select:focus {
            color: blue;
            background-color: green;
          }
          </style>
      </head>
      <body>
        <a href="https://www.baidu.com/">去百度</a>
        <a href="https://www.jd.com/">去京东</a>
        <hr>
        <input type="text">
        <hr>
        <input type="text">
        <hr>
        <input type="text">
        <hr>
        <select>
            <option value="beijing">北京</option>
            <option value="shanghai">上海</option>
        </select>
      </body>
  </html>
  ```

  



### 3.8.3. 结构伪类

* 常见伪类
  * `:first-child`: 所有兄弟元素中的**第一个**
  * `:last-child` 所有兄弟元素中的**最后一个**
  * `:nth-child(n)` 所有兄弟元素中的**第** **n** **个**
  * `:first-of-type` 所有**同类型**兄弟元素中的**第一个**
  * `:last-of-type` 所有**同类型**兄弟元素中的**最后一个**
  * `:nth-of-type(n)` 所有**同类型**兄弟元素中的 **第n个** 
  * `:nth-last-child(n)` 所有兄弟元素中的**倒数第** **n** **个**
  * `:nth-last-of-type(n)` 所有**同类型**兄弟元素中的倒数第n个
  * `:only-child` 选择没有兄弟的元素（独生子女）
  * `:only-of-type` 选择没有**同类型**兄弟的元素
  * `:root` 根元素
  * `:empty` 内容为空元素（空格也算内容）

* **总结**
  * 0 或 不写 ：什么都选不中 —— 几乎不用
  * n ：选中所有子元素 —— 几乎不用。
  * 1~正无穷的整数 ：选中对应序号的子元素。
  * 2n 或 even ：选中序号为偶数的子元素。
  * 2n+1 或 odd ：选中序号为奇数的子元素
  * -n+3 ：选中的是前 3 个。



### 3.8.4. 否定伪类

* 简介
  * `:not(选择器)` 排除满足括号中条件的元素

* 示例

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>12_伪类选择器_否定伪类</title>
          <style>
              /*选中的是div的儿子p元素, 但是排除类名为fail的元素*/
              /*div>p:not(.fail) {*/
              /*    color: red;*/
              /*}*/
  
              /*选中的是div的儿子元素, 但是排除title属性值以"你要加油"开头的*/
              /*div>p:not([title^="你要加油"]) {*/
              /*    color: red;*/
              /*}*/
  
              /*选中的是div的儿子p元素, 但排除第一个儿子p元素*/
              /*伪类是一种状态, 可以看作是多个选择器中的最后一个选择器的修饰
              不可以是其他选择器的修饰*/
              div>p:not(:first-child) {
                  color: red;
              }
  
          </style>
      </head>
      <body>
          <div>
            <p>张三: 98</p>
            <p>李四: 88</p>
            <p>王五: 78</p>
            <p>赵六: 68</p>
              <!-- title属性的作用是鼠标悬浮时有相关的提示 -->
            <p class="fail" title="你要加油">孙七: 58</p>
            <p class="fail" title="你要加油">覃八: 48</p>
          </div>
      </body>
  </html>
  ```

  

### 3.8.5. UI伪类

* **简介**
  * `:checked` 被选中的复选框或单选按钮。
  * `:enable` 可用的表单元素（没有 disabled 属性）
  * `:disabled` 不可用的表单元素（有 disabled 属性）

* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>13_伪类选择器_UI伪类</title>
          <style>
              /*选中的勾选的复选框或单选*/
              input:checked {
                  width: 100px;
                  height: 100px;
                  background-color: green;
              }
  
              /*选中的是被禁用的input元素*/
              input:disabled {
                  background-color: gold;
              }
  
              /*选中的是可用的input元素*/
              /*enable可以不写*/
              input:enabled {
                  background-color: pink;
              }
          </style>
      </head>
      <body>
          <input type="checkbox">
          <input type="radio" name="gender">
          <input type="radio" name="gender">
          <input type="text" disabled>
          <input type="text">
      </body>
  </html>
  ```



### 3.8.5. 目标伪类

* **简介**

  **`:target `**: 选中锚点指向的元素

* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>14_伪类选择器_目标伪类</title>
          <style>
              div {
                  background-color: darkgray;
                  height: 300px;
              }
              div:target {
                  background-color: green;
              }
          </style>
      </head>
      <body>
          <a href="#one">去看第1个</a>
          <a href="#two">去看第2个</a>
          <a href="#three">去看第3个</a>
          <a href="#four">去看第4个</a>
          <a href="#five">去看第5个</a>
          <a href="#six">去看第6个</a>
          <div id="one">第1个</div>
          <br>
          <div id="two">第2个</div>
          <br>
          <div id="three">第3个</div>
          <br>
          <div id="four">第4个</div>
          <br>
          <div id="five">第5个</div>
          <br>
          <div id="six">第6个</div>
          <br>
      </body>
  </html>
  ```

  

### 3.8.6. 语言伪类

* **简介**

  **`:lang() `**: 根据指定的语言选择元素（本质是看 lang 属性的值）

* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="zh-CN">
      <head>
          <meta charset="UTF-8">
          <title>15_伪类选择器_语言伪类</title>
          <style>
              div:lang(en) {
                  color: red;
              }
              div:lang(zh-CN) {
                  color: green;
              }
              /*将全部语言属性为简体中文的元素变绿*/
              :lang(zh-CN) {
                  color: green;
              }
          </style>
      </head>
      <body>
          <div>sgj</div>
          <!-- 都会变红, 语言伪类只看lang属性的属性值是否对上, 不看实际写的是什么 -->
          <div lang="en">songguagnjin</div>
          <div lang="en">宋广进</div>
          <p>java</p>
          <div>前端</div>
      </body>
  </html>
  ```

  ![image-20231122195231860](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311221952950.png)



## 3.9. 伪元素选择器

* **简介**

  选中元素中的一些特殊位置

* **常见伪元素**

  * **`::first-letter`** : 选中元素中的**第一个文字**
  * **`::first-line`**: 选中元素中的**第一行文字**
  * **`::selection`** : 选中**被鼠标选中的**内容
  * **`::placeholder `**: 选中输入框的**提示文字**
  * **`::before `**: 在元素**最开始**的位置，创建一个子元素（必须用 content 属性指定内容）
  * **`::after`** : 在元素**最后**的位置，创建一个子元素（必须用 content 属性指定内容）

* **示例**

  ```html
  <!DOCTYPE html>
  <html lang="en">
      <head>
          <meta charset="UTF-8">
          <title>16_伪元素选择器</title>
          <style>
              /*伪元素: 很像元素, 但不是元素, 是元素中的一些特殊位置*/
              /*选中的是div中的第一个文字*/
              div::first-letter {
                  color: red;
                  font-size: 40px;
              }
  
              /*选中的div中的第一行文字*/
              div::first-line {
                  background-color: gold;
              }
  
              /*选中的是被鼠标选择的文字*/
              div::selection {
                  background-color: green;
                  color: red;
              }
  
              /*选中的是input元素中的提示文字*/
              input::placeholder {
                  color: aqua;
              }
  
              /*选中的是p元素最开始的位置, 随后创建一个子元素*/
              p::before {
                  content: "$";
              }
  
              /*选中的是p元素最末尾的位置, 随后创建一个子元素*/
              p::after {
                  content: ".00";
              }
          </style>
      </head>
      <body>
          <div>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore dolorum illum iste modi nam, non obcaecati odit sed ut voluptates! Accusantium architecto at atque blanditiis consectetur, cupiditate doloremque dolorum ea eius eos eveniet expedita hic itaque laudantium mollitia necessitatibus nemo neque nesciunt non officia pariatur possimus quae quisquam reiciendis reprehenderit saepe sint tenetur ullam vero, voluptates. Dignissimos facere ratione rem!
          </div>
  
          <hr>
          <hr>
  
          <input type="text" placeholder="请输入您的用户名">
  
          <hr>
          <hr>
  
          <p>199</p>
          <p>299</p>
          <p>399</p>
          <p>499</p>
      </body>
  </html>
  ```

  ![image-20231122195546089](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311221955187.png)

   

## 4. 选择器的权重

* **简介**

  通过**不同的选择器**，选中**相同的元素** ，并且为**相同的样式名**设置**不同的值**时，就发生了样式的冲突。到底应用哪个样式，此时就需要看**优先级**了

* **优先级**

  **行内样式** > **ID选择器（1，0，0）** > **类选择器（0，1，0）** > **元素选择器（0，0，1）** > **通配选择器（0，0，0）**

* **计算规则**

  * **计算方式**

    每个选择器，都可计算出一组权重，格式为： (a,b,c), 其中abc的简介如下

    * a : **ID** 选择器的个数
    * b : **类、伪类、属性** 选择器的个数
    * c : **元素、伪元素** 选择器的个数

    |          选择器           |  权重   |
    | :-----------------------: | :-----: |
    |           ul>li           | (0,0,2) |
    |    div ul>li p a span     | (0,0,6) |
    |     \#atguigu .slogan     | (1,1,0) |
    |    \#atguigu .slogan a    | (1,1,1) |
    | \#atguigu .slogan a:hover | (1,2,1) |

  * 比较规则：按照**从左到右**的顺序，依次比较大小，当前位胜出后，后面的不再对比，例如：

    * (1,0,0) > (0,2,2)
    * (1,1,0) > (1,0,3)
    * (1,1,3) > (1,1,2)

  * 特殊规则
    * **行内样式**权重大于**所有选择器**。
    * `!important` 的权重，大于**行内样式**，大于**所有选择器**，**权重最高！**
    * 如果权重相同, 那么按照**"后来者居上"**的规则



# 5. CSS的三大特性

* **层叠性**
  * 如果发生了样式冲突，那就会根据一定的规则（选择器优先级），进行样式的层叠（覆盖）
  * 样式冲突: 元素的**同一个样式名**，被设置了**不同的值**，这就是冲突
* **继承性**
  * 元素会自动拥有**其父元素**、或**其祖先元素**上所设置的**某些样式**
  * 优先继承**离得近**的
  * 常见的可继承属性
    * `text-??` 
    * `font-??` 
    * `line-??` 
    * `color`
    *  ......
    * 

* 优先级
  * !important > **行内样式** > **ID****选择器** > **类选择器** > **元素选择器** > ***** > **继承的样式**
  * 计算权重时需要注意：**并集选择器的每一个部分是分开算的**