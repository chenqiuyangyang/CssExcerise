# **现代Web布局**

## 1 web布局技术演进：了解Web布局发展史

##### 1）Web布局演变过程

##### 2）无任何布局模式

##### 3）表格布局模式

##### 4）浮动、定位和框架布局模式

​       1.浮动布局

​       2.定位布局

​       3.框架布局

##### 5）响应式Web布局（RWD）

##### 6）内在Web设计（IWD）

​        什么是内在Web设计？

##### 7）组件驱动式Web设计（Component-Driven Web Design，CDWD）

## 2 现代web布局技术术语

##### 1）Web坐标轴

坐标轴不只是存在于数学中，它同样存在于 Web 世界中。在 Web 中，我们常称之为 **Web** **坐标轴** 或 **CSS** **坐标系统** 。

在 Web 中，默认原点是给定上下文的左上角，也就是元素盒子的左上角，它分为 `x` 轴（也称为水平轴），向右为正值，向左为负值；`y` 轴（垂直轴），向上为负值，向下为正值：

![image-20230109025603794](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230109025603794.png)

除了大家熟悉的平面画布中的 `x` 和 `y` 轴之外，还有控制第三维度的 `z` 轴。比如使用 CSS 的 `transform` 绘制 3D 图形或使用第三维度从前往后对对象进行分层：

![image-20230109030208200](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230109030208200.png)

##### 2）容器和容器空间

HTML 的每一个元素在 CSS 中都是一个盒子，这个盒子又被称为 **容器** 。

- `block` 时称为块容器；

- `inline` 时称为内联容器；

- `flex` 或 `inline-flex` 时称为Flexbox容器；

- `grid` 或 `inline-grid` 时称为 Grid 容器（网格容器）。

每个容器的大小（空间）又有**可用空间** （也称为 **剩余空间** ）和 **不可用空间** （也称为 **不足空间** ）：

![image-20230109030048754](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230109030048754.png)

##### 3）间距

在 Web 布局中，我们常常是使用 CSS 的 `margin` 、`padding` 和 `gap` 三个属性来设置间距。不同的是：

- 框与框（也就是元素与元素）之间的间距一般采用 `margin` 或 `gap` 属性来设置，也常称为 **外距** ；

- 内容与框的边缘（元素内容与元素框边缘）之间的间距一般采用 `padding` 来设置，也常称为 **内距**。

特别要提出来的是，CSS 中的 `margin` 和 `gap` 表现形式是有较大差异的，它们之间的差异用下图来阐述：

![image-20230109025351237](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230109025351237.png)

##### 4）对齐方式

在以往，我们控制对齐方式主要是依赖于 CSS 的 `text-align` （水平方向文本对齐）和 `vertical-align` （垂直方向文本对齐）两个属性，对于块的对齐方式主要依赖于 `float` 属性。它们是无法满足 Web 布局中的对齐控制。

庆幸的是，随着 CSS Flexbox 特性出现之后，CSS 新增了像 `justify-content` 、`align-content` 、`align-items` 、`justify-items` 和 `justify-self` 以及 `align-self` 等属性，用来控制 Web 布局上的对齐方式。

## 3 Flexbox布局基础使用（一维）

##### 先讲：CSS中的常用长度单位：

​    px   像素大小       在页面中所代表的大小是固定为1像素点

​    %    相对父节点尺寸

​    em   相对父元素字体大小

​    rem  相对根元素字体大小   【例子】

​    vw   将视窗宽度分为100份，1vw=视窗宽度的百分之1

​    vh   将视窗高度分为100份，1vh=视窗高度的百分之1

##### 1）Flexbox布局简介

Flexbox 布局是一种布局机制，用于在一个维度上为项目组设置布局。

##### 2）一些术语和概念

Flex容器

Flex项目

主轴

侧轴

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/573539dfa0a4447bba9e78a5f676bb63~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

##### 3）Flexbox布局模块相关特性

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/584b5a15ed2b45bba8615773ca4291cc~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2d832f3e72844710b90bfb3f067cb0c7~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

##### 4）控制Flex项目的方向 `flex-direction`

##### 5）Flex项目换行 `flex-wrap`

##### 6）Flex项目排序`order`

`order` 初始值是 `0` ，可以是正值，也可以是负值，属性值越大，越排在主轴的后面，反之越在主轴的前面。【例子】

##### 7）Flex项目之间的间距 `margin`与`gap` 

【需要写一个实例】

## 4 Flexbox布局中的对齐方式

##### 1）沿主轴分配空间 `justify-content`

（1） `justify-content`：沿 Flex 容器的主轴分配 Flex 容器的剩余空间

（2）`justify-content` 的取值：

- `flex-start` ：主轴起点对齐；

- `flex-end` ：主轴终点对齐；

- `center` ：主轴居中对齐；（可以实现水平居中的布局效果 ）

- `space-between` 会让行上第一个 Flex 项目的起始边缘与 Flex 容器主轴起点相吻合，行上最后一个 Flex 项目的结束边缘与 Flex 容器主轴终点相吻合，其它相邻 Flex 项目之间间距相等。当 Flex 容器中只有一个 Flex 项目时，其表现行为和 `flex-start` 等同。

  ![](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230104230511025.png)

- `space-around` 会让行上第一个 Flex 项目的起始边缘与 Flex 容器主轴起点间距，和行上最后一个 Flex 项目的结束边缘与 Flex 容器主轴终点间距相等，并且等于其他相邻两个 Flex 项目之间间距的二分之一。当 Flex 容器中只有一个 Flex 项目时，其表现行为和 `center` 等同。

  ![image-20230104230357699](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230104230357699.png)

- `space-evenly` 会让行上第一个 Flex 项目的起始边缘与 Flex 容器主轴起点间距，和最后一个 Flex 项目的结束边缘与 Flex 容器主轴终点间距相等，并且等于其他相邻两个 Flex 项目之间间距。当 Flex 容器中只有一个 Flex 项目时，其表现行为和 `center` 等同。

![image-20230104230452968](C:\Users\18258\AppData\Roaming\Typora\typora-user-images\image-20230104230452968.png)

注意:如果 Flex 容器没有额外的剩余空间，或者说剩余空间为负值时， `justify-content` 属性的值表现形式和前面所述是有差异的：

- `flex-start` 会让 Flex 项目在 Flex 容器主轴终点处溢出 ；

- `flex-end` 会让 Flex 项目在 Flex 容器主轴起点处溢出；

- `center` 会让 Flex 项目在 Flex 容器两端溢出；

- `space-between` 和 `flex-start` 相同；

- `space-around` 和 `center` 相同；

- `space-evenly` 和 `center` 相同；

- `start` 和 `flex-start` 相同；

- `end` 和 `flex-end` 相同。

##### 2）沿侧轴分配空间 `align-content`

> 沿侧轴分配空间，又可以看作是 Flexbox 布局中多行（或多列）的对齐方式 ！

`align-content`：沿 Flex 容器的侧轴分配 Flex 容器的剩余空间；

`place-content`：它是 `justify-content` 和 `align-content` 的简写属性。

##### 3）沿侧轴对齐Flex项目 `align-items` 或 `align-self`

使用 `align-items` 或 `align-self` 来控制整行 Flex 项目，或单个 Flex 项目在侧轴上的对齐方式：

- `align-items` 用于 Flex 容器上，控制 Flex 行（所有 Flex 项目所在行）在侧轴上对齐方式；

  ![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/dc8d902da91d4367bde4efea54a17e07~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

- `align-self` 用于 Flex 项目上，控制单个 Flex 项目在侧轴上对齐方式。

  取值： `flex-start` 、`center` 、`flex-end` 、`stretch` 、`baseline` 、`start` 和 `end`   （`align-self`还有一个`auto`）

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ff98355476f7467b84c9e078f90de1c2~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

## 5 Flexbox布局中的flex属性的基础应用

##### 1）flex的基础使用  `flex-basis` 、`flex-grow` 和 `flex-shrink` 

`flex` 是一个只能用于 Flex 项目的属性，它可以**让 Flex 项目根据 Flex 容器的可用空间对自身做伸缩计算** ，它包含三个子属性：`flex-basis` 、`flex-grow` 和 `flex-shrink` 。

[1] `flex-basis` 是 在任何 Flex 容器空间（剩余空间或不足空间）分配发生之前Flex 项目的初始化宽度（尺寸） 。

[2] 当所有 Flex 项目的宽度（尺寸） 总和**大于** Flex 容器可用空间时，将会使用 `flex-shrink` 属性值作为 Flex 项目的收缩因子（收缩比率）来**收缩** Flex 项目。

[3] 当所有 Flex 项目的宽度（尺寸）总和**小于** Flex 容器可用空间时，将会使用 `flex-grow` 属性值作为 Flex 项目的扩展因子（扩展比率）来**扩展** Flex 项目。

------

如果没有在 Flex 项目设置 `flex` 属性的值，此时，浏览器在计算 Flex 项目时会视 Flex 项目的 `flex` 属性的值是其默认值，即 `flex: 0 1 auto` ，对应的就是：

- `flex-grow` 属性的初始值为 `0` ，表示 Flex 项目不扩展（即不瓜分 Flex 容器的剩余空间）；

- `flex-shrink` 属性的初始值为 `1` ，表示 Flex 项目会收缩（即 Flex 项目在原始尺寸上按比率减去 Flex 容器的不足空间）；

- `flex-basis` 属性的初始值为 `auto` ，表示 Flex 项目的基本尺寸是 Flex 项目的（最大）内容尺寸。

  

------

在使用的时候，`flex` 属性可以指定 **`1`** **个值** （单值语法）、**`2`** **个值** （双值语法）或 **`3`** **个值** (三值语法)。

(1)`flex` 属性的单值语法时，其值必须为以下其中之一：

- 一个无单位的数值，比如 `flex: 1` ，这个时候它（即`1`）会被当作 `flex-grow` 属性的值；

- 一个有效的长度值，比如 `flex: 30vw` ，这个时候它（即 `30vw`）会被当作 `flex-basis` 属性的值；

- 关键词 `none` 、 `auto` 或 `initial` （即初始值）。

  比如：

  ```css
  .item {
    flex: 1;
      
    /* 等同于 */
    flex-grow: 1;
    flex-shrink: 1; 
    flex-basis: 0%; 
  }
  
  .item {
    flex: 30vw;
      
    /* 等同于 */
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 30vw;
  }
  ```

  

(2)`flex` 属性的双值语法，其第一个值必须为 **一个无单位的数值 ，并且它会**被当作** **`flex-grow`** **属性的值** ；第二个值必须为以下之一：

- 一个无单位的数值，它会被当作 `flex-shrink` 属性的值；

- 一个有效的长度值，它会被当作 `flex-basis` 属性的值。

比如：

```css
.item {
  flex: 1 2;
  
  /* 等同于 */
  flex-grow: 1;
  flex-shrink: 2;
  flex-basis: 0%;
}

.item {
  flex: 2 30vw;
  
  /* 等同于 */
  flex-grow: 2;
  flex-shrink: 1;
  flex-basis: 30vw;
}

.item {
  flex: 30vw 2;
  
  /* 等同于 */
  flex-grow: 2;
  flex-shrink: 1;
  flex-basis: 30vw;
}
```



(3)`flex` 属性的三值语法：

- 第一个值必须是一个无单位的数值，并且它会被当作 `flex-grow` 属性的值；

- 第二个值必须是一个无单位的数值，并且它会被当作 `flex-shrink` 属性的值；

- 第三个值必须是一个有效的长度值，并且它会被当作 `flex-basis` 属性的值。

比如：

```css
.items {
  flex: 2 1 200px;
    
  /* 等同于 */
  flex-grow: 2;
  flex-shrink: 1;
  flex-basis: 200px;
}

.item {
  flex: 30vw 2 1;
  
  /* 等同于 */
  flex-grow: 2;
  flex-shrink: 1;
  flex-basis: 30vw;
}
```

(4)`flex` 属性的取值还可以是：

- `auto` ：Flex 项目会根据自身的 `width` （或 `inline-size`）和 `height` （或 `block-size`）来确定尺寸，但 Flex 项目会根据 Flex 容器剩余空间进行伸缩。其相当于 `flex: 1 1 auto` 。

  ```css
  .item {
    flex: auto;
      
    /* 等同于 */
    flex-grow: 1;     /* Flex 项目可以扩展到超过其 flex-basis */
    flex-shrink: 1;   /* Flex 项目可以收缩到小于其 flex-basis */
    flex-basis: auto; /* Flex 项目为基本大小 auto，即 max-content */
  }
  ```

  

- `initial` ： Flex 项目会根据自身的 `width` (或 `inline-size`)， 和 `height` （或 `block-size`）来确定尺寸，Flex 项目不会扩展，但会收缩来适应 Flex 容器。其相当于 `flex: 0 1 auto`。

  ```css
  .item {
    flex: initial;
    
    /* 等同于 */
    flex-grow: 0;
    flex-shrink: 1;
    flex-basis: auto;
  }
  ```

  

- `none` ：Flex 项目会根据自身的 `width` （或 `inline-size`），和 `height` （或 `block-size`）来设置尺寸，它是完全非弹性的，即不会收缩，也不会扩展来适应 Flex 容器。其相当于 `flex: 0 0 auto`。

  ```css
  .item {
    flex: none;
    
    /* 等同于 */
    flex-grow: 0;
    flex-shrink: 0;
    flex-basis: auto;
  }
  ```

  

> Demo 地址：[codepen.io/airen/full/…](https://link.juejin.cn/?target=https%3A%2F%2Fcodepen.io%2Fairen%2Ffull%2FvYjmENe)。

## 6 使用Flexbox构建经典布局：10种经典Web布局

##### 1）水平垂直居中

##### 2）等高布局

##### 3）均分列（等分列）布局

##### 4）圣杯布局

##### 5）Sticky Footer布局

##### 6）百分百无滚动布局

##### 7）12列网格布局

##### 8）九宫格布局

##### 9）具有不同对齐方式的导航栏

##### 10）灵活的弹性框

## 7 Grid布局的基础知识（二维网格的布局系统）

##### 1）什么是网格布局？

CSS 内置的网格系统除了是一个具有二维布局的系统之外，还具有以下这些特性。

- **固定的和弹性的轨道（行或列）尺寸** ：可以使用固定的轨道尺寸创建网格，比如我们熟悉的固定单位 `px` ，也可以使用百分比 `%` 或者网格系统中独有的弹性单位 `fr` 创建具有弹性尺寸的网格轨道，也可以两者相互结合来创建网格。
- **网格项目放置** ：可以使用网格线的**数字索引号**，或网格线名称，或者网格区域来精确放置网格项目。网格同时还使用一种算法来控制未给出明确网格位置的网格项目。
- **创建额外的网格轨道来放置网格项目** ：可以使用网格布局定义一个显式网格，但根据规范它会处理你加在网格外的内容，当必要时它会自增网格轨道，来尽可能多地容纳所有网格项目。
- **对齐控制** ：网格布局系统中也涵盖了对齐（Box Alignment）模块的部分特性，便于我们控制网格项目或网格轨道在内联轴或块轴方向的对齐。
- **控制层叠内容** ：一个网格单元或网格区域中可以放置多个网格项目，并且它们可以部分相互重叠，而且可以通过 `z-index` 属性来控制它的层级权重。
- **网格的嵌套（或子网格）** ：网格布局和早期的表格布局非常的相似，在网格布局中还可以让网格与网格相互嵌套，甚至还可以使用子网格。
- **网格顺序** ：在网格布局中，除了通过网格线或网格区域来调整网格顺序之外，还可以像 Flexbox 布局中一样，使用 `order` 属性来调整网格项目的排列顺序。

##### 2）网格布局术语

###### 1.坐标轴

列轴和行轴

###### 2.网格容器和网格项目

在 CSS 的网格布局中，显式声明了 `display` 属性的值为 `grid` 或 `inline-grid` 的元素被称为 **网格容器（Grid 容器）** ，该元素的直接子元素（包括其文本节点和伪元素）都被称为**网格项目（Grid 项目）** 。

同样的，如果在网格项目上显式设置 `display` 的值为 `grid` 或 `inline-grid` ，它就既是一个网格容器也是一个网格项目。

###### 3.网格线

列网格线

行网格线

网格布局中未显式给网格线命名的情况下，默认是以数字索引号命名，并且从`1` 开始叠加，同时它的反方向则从 `-1` 开始命名。

而且，网格线的数量是由网格轨道来决定的：

- 列网格线数量由 `grid-template-columns` 来决定；
- 行网格线数量由 `grid-template-rows` 来决定。

需要注意的是，使用 `grid-template-columns` 、`grid-template-rows` 以及 `grid-template-areas` 属性定义的网线名称，都被称为显式网格线名称。也就是说，在 CSS 网格中还有隐式被命名的网格线名称。可以使用 `grid-row` 、`grid-column` 或 `grid-area` 将网格项目放置在显式网格之外时创建的网格线，被称为隐式网格线名称，它们会在显式网格线上累加。

###### 4.网格单元格

网格中 **相邻的两条行和列网格线所围绕着的区域，被称为网格单元格** （有点类似于表格单元格），它是网格中的最基本单位（空间）。网格单元格可以被用来放置网格项目。

###### 5.网格轨道

（1）网格轨道：是 CSS Grid 布局中独有的一种术语，把网格中的列和行统称为网格轨道。**它是两条相邻网格线之间的空间。**简单说，就是它控制着网格的列宽或行高（即网格轨道尺寸）。

（2）网格沟槽：相邻网格线（不是同一个项目的）可以用**网格沟槽**（即 `gap` 属性）来隔开。

Grid 布局中的网格轨道尺寸是由 `grid-template-columns` 和 `grid-template-rows` 属性来指定的，其中：

- `grid-template-columns` 指定列网格轨道尺寸，即列宽；
- `grid-template-rows` 指定行网格轨道尺寸，即行高。

另外，还可以使用 `grid-auto-columns` 和 `grid-auto-rows` 属性来指定隐式网格轨道尺寸：

- `grid-auto-columns` 指定隐式列网格轨道尺寸；
- `grid-auto-rows` 指定隐式行网格轨道尺寸。

###### 6.网格区域

网格区域的作用和网格单元格一样，主要用来放置一个或多个网格项目的逻辑空间。它可以使用 `grid-template-areas` 属性显式命名，然后使用 `grid-area` 来引用已命名好的网格区域，还可以通过它的边界网格线隐式引用。

【案例演示】

###### 7.显式网格和隐式网格

- `grid-template-rows` 、`grid-template-coluns` 和 `grid-template-areas` 定义显式网格；
- `grid-template-rows` 和 `grid-template-columns` 可以用来指定显式网格轨道固定数量和网格轨道尺寸；
- `grid-auto-rows` 、`grid-auto-columns` 和 `grid-auto-flow` 定义隐式网格；
- `grid-auto-rows` 和 `grid-auto-columns` 可以用来指定隐式网格轨道尺寸；
- `grid-row` 、`grid-column` 和 `grid-area` 将网格项目放置在显式网格之外，也会创建隐式网格。

###### 8.网格间距（沟槽）

使用 `gap` 属性来设置网格轨道之间的间距，其中：

- `column-gap` 用来设置列网格轨道之间的间距；
- `row-gap` 用来设置行网格轨道之间的间距。

##### 3）网格布局中的属性

1.可用于网格容器的属性

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/50c8f03b12654f308d0a2978aa9ad4d2~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

其中一部分是用来创建（或定义）网格的，比如 `grid-template-*` 和 `grid-auto-*` 等；另外一部分是用来设置网格对齐方式的，比如 `justify-content` 、`align-content` 等。

2.可用于网格项目的属性

用于网格项目的属性，主要有 `grid-row` （分为 `grid-row-start` 和 `grid-row-end`）、`grid-column` （分为 `grid-column-start` 和 `grid-column-end`）、`grid-area` 等属性，它们主要用来**放置网格项目位置**的。还有就是用来设置网格项目对齐方式的，比如 `justify-self` 和 `align-self` 等。

##### 4）网格容器尺寸

##### 5）网格项目的尺寸

## 8 定义一个网格布局

##### 1）定义网格的类型

##### 2）使用 grid-template-columns 和 grid-template-rows 定义网格

- 定义了网格线；

- 定义了网格轨道数量；

- 定义了网格轨道尺寸。

  ```css
  grid-template-columns: [列网格线1] [列网格轨道1尺寸] [列网格线2] [列网格轨道2尺寸] [...] [列网格轨道N的尺寸] [列网格线N+1]
  grid-template-rows: [行网格线1] [行网格轨道1尺寸] [行网格线2] [行网格轨道2尺寸] [...] [行网格道M的尺寸] [行网格线M+1]
  ```

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/fd1430c677f34753898cdf963e34f034~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

注意：

从前面的课程中可以得知，在网格容器中设置 `gap` 属性时，可以给网格轨道之间设置间距。如果你使用浏览器调试工具查看带有 `gap` 设置的网格时，你会发现相邻两个网格轨道有两条线网格线存在。很多初学者会误认为这是两条网格线，其实它就是一条网格线，因此，你可以以 `-end` 和 `-start` 给同一条网格线命名：

```css
grid-template-columns: [列网格线1 列网格线1-start] 列网格轨道1的尺寸 [列网格线1-end 列网格线2-start] 列网格轨道2尺寸 [列网格线2-end 列网格线N-start] 列网格轨道N的尺寸 [列网格线N-end 列网格线(N+1)-start]
grid-template-row: [行网格线1 行网格线1-start] 行网格轨道1的尺寸 [行网格线1-end 行网格线2-start] 行网格轨道2尺寸 [行网格线2-end 行网格线M-start] 行网格轨道M的尺寸 [行网格线M-end 行网格线(M+1)-start]
```

CSS 网格布局中，使用 `grid-template-columns` 和 `grid-template-rows` 属性定义好一个网格时，它的子元素（网格项目）默认情况之下**只会按照自动放置算法来放置网格项目** 。

但要真正构建一个符合需求的 Web 布局时，还需要通过 `grid-column` 、`grid-row` 或 `grid-area` 属性来指定网格项目放置在什么位置。

##### 3）使用 grid-template-areas 定义网格

该属性可以用来给网格区域命名，并且指定了命名的网格区域不与任何特定的网格项目关联，但可以将已命名好的网格区域名称用在 `grid-row` 、`grid-column` 和 `grid-area` 属性上，这些属性会按照网格区域名称来放置网格项目。

 `grid-template-areas` 属性给网格区域命名的六条规则：

- 规则① ：必须描述一个完整的网格，即网格上的每一个单元格都必须被填充；
- 规则② ：一连串的空白，代表什么都没有，将造成 `grid-template-areas` 语法错误；
- 规则③ ：在网格命名中可以使用一个或多个`.`（`U+002E`），代表一个空单元格；
- 规则④ ： 多个相同单元格命名（令牌）创建一个具有相同名称的命名网格区域。简单地说，跨行或列命名相同的网格区域名称，可以达到合并单元格的作用；
- 规则⑤ ：任何其他字符的序列，会代表一个垃圾标记（Trash Token），会使声明无效；
- 规则⑥ ：当序列化 `grid-template-areas` 的 `<string>` 值是指定值或计算值时，相邻两字符串（网格区域命名）被一个空格（`U+0020`）隔开，当两者之间有多个空格符时，会被视为一个，其他空格将会被忽略。

##### 4）使用 grid-auto-columns 和 grid-auto-rows 定义网格

显式行网格轨道尺寸按照 `grid-template-rows` 属性值计算，隐式行网格轨道尺寸按照 `grid-auto-rows` 属性值计算。

##### 5）使用 grid-auto-flow 改变网格排列方向

## 9 Grid布局中的计算

##### 2）网格中 fr 的计算 

fr网格系统中独有的弹性单位。

 非负值，用单位 `fr` 来定义网格轨道大小的弹性系数，有点类似于 Flexbox 布局中的 `flex` 属性，**按比例分配网格容器的剩余空间。**

## 10 可用于Grid布局中的函数

##### 1）repeat() 函数

 表示网格轨道的重复部分，以一种更简洁的方式去表示大量而且重复列的表达式。

##### 3）minmax() 函数

是一个来定义大小范围的函数，大于等于 min 值，并且小于等于 max 值。

## 11 网格项目的放置和层叠 `z-index`

## 12 Grid布局中的对齐方式

##### 1）网格布局中的轴线

行轴和列轴

##### 2）网格布局中的对齐方式

- **对齐网格项目** ：`justify-items` 和 `justify-self` 沿着内联轴方向对齐网格项目，而`align-items` 和 `align-self` 沿着块轴方向对齐网格项目，其中 `justify-items` 和 `align-items` 被运用于网格容器，而 `justify-self` 和 `align-self` 被运用于网格项目。

- **对齐网格轨道** ：`align-content` 沿着块联轴方向对齐网格轨道，`justify-content` 沿着内联轴方向对齐网格轨道，它们都被运用于网格容器。

  注意：

  用于网格容器：`justify-content` `align-content` `justify-items` 和 `align-items` 

  用于网格项目： `justify-self` 和 `align-self`

######  1.网格项目

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/34f95b07e31d4bfe9805b51a6d2cc1e1~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

######       2.网格轨道对齐

- **内联轴方向** ：`justify-content` 控制列网格轨道在内联轴方向的对齐方式，即控制网格列的对齐；

  ![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3db8586d00914a5db8fe5c825f38676b~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

- **块轴方向** ：`align-content` 控制行网格轨道在块轴方向的对齐方式，即控制网格行的对齐。

  ![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/89c6b387290941e2935ba6535e347df8~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

##### 3）网格项目的 `margin:auto`

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/12da10c18ec84b17ba78fe1e6fe807e2~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

## 13 使用Grid构建经典布局：10种经典布局

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5edff371fb0644d99f4b34dd2dcfaccb~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

##### 1）水平垂直居中

##### 2）等高布局

##### 3）均分列

##### 4）圣杯布局

**5)响应式圣杯布局**

##### 6）Sticky Footer 布局

##### 7）百分百无滚动布局

**8）百分百有滚动布局**

##### 9）12列网格布局

##### 10）九宫格布局

## 14 Flexbox or Grid：如何选择合适的布局？

##### 1）Grid 布局会替代 Flexbox 布局吗？

##### 2）CSS Grid vs. CSS Flexbox

###### 1.二维 vs. 一维

###### 2.布局优先（外在）vs. 内容优先（内在）

###### 3.页面布局（宏观布局） vs. 组件布局（微观布局）

###### 4.对齐方式

###### 5.`z` 轴上的层叠

###### 6.项目的伸缩扩展

```css
.flex-container {
    display: flex;
}

.flex-item {
    flex: 1 1 0%;
    min-width: 0;
 }
///////////////////
.grid-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
}

.grid-item {
    min-width: 0;
}

++++++++++
.grid-container {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr)); 
}
```



###### 7.排列方向与换行

1.排列方向

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f108c3ea67354b889be6660ec2794994~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0a0c5ad5b86f4390890db8ebcadc99dd~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

不同的是，CSS Grid 布局还可以使用 `grid-template-rows` 或 `grid-template-columns` 来改变网格排列。

还可以在网格项目上使用 `grid-row` 、`grid-column` 或 `grid-area` 来改变网格项目的默认排列位置。这是在 CSS Flexbox 布局中做不到的。

2.换行

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2eff76cdc0404d0d98f6a32b746b4e6e~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

在 CSS Grid 布局中要实现自动换行（列），就需要采用网格布局中的 RAM 布局技术，即 `repeat()` 、`minmax()` 函数结合起来，并且指定列（行）网格轨道数量时，不能使用具体的数值，要使用 `auto-fit` 或 `auto-fill` 关键词：

![img](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/074bd93a9c6c416a92c09b5bda09b25f~tplv-k3u1fbpfcp-zoom-in-crop-mark:3024:0:0:0.awebp)

###### 8.改变顺序和间距

##### 3）什么时候使用 CSS Grid 和 CSS Flexbox?

当出现以下情况时，你应该考虑选择使用 CSS Flexbox：

- 当你需要实现一个小的布局时，可以考虑 Flexbox；
- 当你需要对齐元素时，Flexbox 非常适合；
- 当你需要一个内容优先的设计，尤其是你不知道你的内容看起来是什么样子的，那么 Flexbox 是完美的选择；
- 当你需要实现的布局就是一个一维布局，可以考虑 Flexbox。

当出现以下情况时，你应该考虑选择使用 CSS Grid：

- 当你需要实现一个复杂的设计，可以考虑 Grid；
- 当你需要一个布局优先时，尤其是在你的脑海中已经有了布局设计结构，使用 CSS Grid 更容易构建；
- 当你的布局上元素相互交叉和层叠较多时，CSS Grid 更完美，更简单；
- 当你需要实现的布局是一个二维布局，那最好是选择 CSS Grid。



【重叠与子网格   与min-width】