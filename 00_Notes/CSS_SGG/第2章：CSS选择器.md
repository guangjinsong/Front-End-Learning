# 选择器分类

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
  2. 复合悬着器可以在复合结构中, 快速而准确的选中元素



# 基本选择器

## 通配选择器

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



## 元素选择器

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



## 类选择器

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



## id选择器

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



## 基本选择器总结

| 基本选择器 |                        特点                         |         用法          |
| :--------: | :-------------------------------------------------: | :-------------------: |
| 通配选择器 |           选中所有标签，一般用于清除样式            |    `* {color:red}`    |
| 元素选择器 |        选中所有同种标签，但是不能差异化选择         |   `h1 {color:red}`    |
|  类选择器  | 选中所有特定类名（ class 值）的元素 —— 使用频率很高 |  `.say {color:red}`   |
| ID 选择器  |         选中特定 id 值的那个元素（唯一的）          | `#earthy {color:red}` |



# 复合选择器

## 交集选择器

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



## 并集选择器

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



## HTML元素间的关系

### 分类

1. 父元素
2. 子元素
3. 祖先元素
4. 后代元素
5. 兄弟元素



### 父元素

* **简介**
  * 直接包裹某个元素的元素，就是该元素的父元素

* **举例**

  ![image-20231114160219745](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141602843.png)



### 子元素

* **简介**

  * 被父元素**直接**包含的元素（简记：儿子元素）

* **举例**

  ![image-20231114160307899](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141603955.png)



### 祖先元素

* **简介**

  * 父亲的父亲......，一直往外找，都是祖先
  * 父元素，也算是祖先元素的一种

* **举例**

  ![image-20231114160358157](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141603210.png)



### 后代元素

* **简介**

  * 儿子的儿子......，一直往里找，都是后代
  * 子元素，也算是后代元素的一种

* **举例**

  ![image-20231114160440504](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141604562.png)



### 兄弟元素

* **简介**

  * 具有相同父元素的元素，互为兄弟元素

* **举例**

  ![image-20231114160538662](https://dawn1314.oss-cn-beijing.aliyuncs.com/typoraimg/202311141605716.png) 