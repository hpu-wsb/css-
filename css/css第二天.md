#    css的复合选择器

### 后代选择器 

ol li {

color:   

}只改变ol中的li 

即 元素一  元素二{样式}

### 子选择器 

元素一>元素二{样式}

dic>p{}    选择div里面所有最近一级p标签元素

### 并集选择器

元素一，元素二{样式 }

### 伪类选择器

a：link 选择所有未被访问过的链接

a：visitef 选择所有已被访问的链接

a：hover 选择鼠标指针位于其上的链接

a：active  选择活动链接（鼠标点击未抬起）

a:  empty	选择空标签

a:  focus	选择当前获得焦点的表单元素

a:  enabled	选择当前有效的表单元素

a:  disabled	选择当前无效的表单元素

a:  checked	选的当前已经勾选的单选按钮或者复选框

a:  root	选择根元素，即<html>标签

### focus选择器

把有光标的选择出来

input:focus{

background-color:         :

}

### 属性选择器

[alt] 有这个属性

[alt = "abc"] 精确匹配	

[alt ^="abc"] 开头匹配

[alt $="abc"] 结尾匹配

[alt *="abc"] 任意位置匹配

[alt |="abc"] abc-开头

[alt ~="abc"] abc为空格分开的独立部分

### 伪元素

::before{  content: " " ; }创建一个伪元素，其将成为匹配选中的元素的第一个子元素，必须设置content属性表示其中的内容

::after创建一个伪元素，其将成为匹配选中的元素的最后一个子元素，必须设置content属性表示其中的内容

::selection 应用于文档中被用户高亮的部分（使用鼠标圈中的部分）

::first-letter  会选中某元素中（必须是块级元素）第一行的第一个字母

::first-line会选中某元素（必须是块级元素）第一行全部文字 

### 层叠性：多个选择器可以同时作用于同一个标签，效果叠加 

选择器权重计算，id选择器#>类名选择器.>标签选择器{    }

!important  提升权重，，写在属性后面

### 常用文本样式属性

color   可以设置文本内容的前景色

color: rgb(  ，  ， )    rgb表示法

color: rgba( ,  ,   ，.x)    rgba表示法，最后一个参数表示透明度，介于0到1之间，0表示纯透明，1表示纯实心

font-size：30px；   用来设置字号，通常单位为px 

font-weight:     ;    用来设置字体得粗细程度，通常就用normal和bold两个值

font-style    设置字体的倾斜，，normal,italic,oblique

text-decoration  用来设置文本的修饰线外观（下划线：underlinne，删除线:through）

font-family  用于设置字体     可用中文，也可用英文，字体可以是列表形式，一般英语字体放到前面，后面的字体是前面的字体的“后备”字体，字体必须用引号包裹

line-height 用于定义行高，可以以px为单位，也可以是没有单位的数值，表示字号的倍数

text-align:center  水平居中

line-height:        垂直居中，行高等于盒子高

font:    apx/1.5 Arial,可以用来合写字号，行高，字体

cursor:pointer 鼠标为小手

### 盒模型

盒子的总高度 = height + 上下padding + 上下border

width 表示盒子内容的宽度，单位通常是px 

height表示盒子内容的高度，单位通常是px

padding是盒子的内边框，即盒子边框内壁到文字的距离

padding是四个方向的，都可以用小属性进行设置

padding-top,上padding     -right右   -bottom下   -left左

padding: 上     右     下     左；

padding:  上   左右     下；

padding：上下   左右；

margin是盒子的外边距，一些元素有默认的margin

margin和padding一样

box-sizing: border-box,盒子的width，height数字就表示盒子实际占有的宽高（不含margin）    了，即padding，border变为“内缩”的，不再“外扩”

###  块元素特点

1.自己独占一行，如div,section,header,h,li,ul等

2.高度，宽度，外边距以及内边距都可以控制

3.宽度默认是容器的100%

4.是一个容器及盒子，里面可以放行内或块级元素

### 行内元素

1.相邻行内元素在一行上，一行可以显示多个 ,如a,span,em,b,u,i等等

2.高，宽直接设置是无效的

3.默认宽度就是它本身内容的宽度

4.行内元素只能容纳文本或其他行内元素

### 行内块元素

1.和相邻行内元素在一行上，但是他们之间会有空白缝隙，一行可以显示多个（行内元素特点）

2.默认宽度就是它本身内容的宽度（行内元素特点）

3.高度，行高，外边距以及内边距都可以控制（块级元素特点）

display:block；把行内元素转换为块级元素

display:inline;把块级元素转换为行内元素

display:inline-block转换为行内块

display:none;把元素隐藏，元素将彻底放弃位置，如同没有写它的标签一样

visibility:hidden;把元素隐藏，但是元素不放弃自己的位置

### 浮动

浮动最本质功能：用来实现并排   float:  left    ;

浮动使用要点：要浮动，并排的盒子都要设置浮动

父盒子要有足够的宽度，否则子盒子会掉下去

浮动的顺序贴靠特性：子盒子会按顺序进行贴靠，如果没有足够空间，则会寻找再前一个兄弟元素 

浮动的元素一定能设置宽高：浮动的元素不再区分块级元素，行内元素，

垂直显示的盒子，不要设置浮动，只有并排显示的盒子才要设置浮动

大盒子带着小盒子跑，一个大盒子中，又是一个小天地，内部可以继续使用浮动

### BFC规范和浏览器差异

BFC是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素，反之亦然

如何创建BFC：

1.：float的值不是none

2.：position的值不是static或者relative

3.：display的值是inline-block，flex或者inline-flex

4.：overflow：hidden，，表示溢出隐藏，溢出盒子边框的内容将会被隐藏

清除浮动方法1：让内部有浮动的父盒子形成BFC，它就能关闭住内部的浮动。此时最好的方法就是overflow:hidden属性

清除浮动方法2：给后面的父盒子设置clear：both属性。clear表示清楚浮动对自己的影响，both表示左右浮动都清除

清除浮动方法3：使用：：after伪元素给盒子添加最后一个子元素，并且给：：after设置clear：both

清除浮动方法4：在两个父盒子之间“隔墙”，隔一个携带clear：both

### 相对定位

相对定位：盒子可以对自己原来的位置进行位置调整，称为相对定位

left向右移动，right向左移动，top向下移动，bottom向上移动，值可以为负

相对定位的元素，会在“老家留坑”，本质上仍是在原来的位置，只不过渲染在新的地方而已，渲染的图形可以比喻成“影子”，不会对页面其他元素产生任何影响

相对定位用来微调元素位置

相对定位的元素，可以当做绝对定位的盒子

### 绝对定位

盒子可以在浏览器中以坐标进行位置精准描述，拥有自己的绝对位置

left到左边的距离，right到右边的距离，top到上边的距离，bottom到下边的距离

绝对定位的元素脱离文档流，将释放自己的位置，对其他元素不会产生任何干扰，而是对他们进行压盖

脱离标准文档流的方法：浮动，绝对定位，固定定位

绝对定位的盒子会以自己祖先元素中，离自己最近的拥有定位属性的盒子，当作基准点。这个盒子通常是相对定位的，所以这个性质也叫作“子绝父相”   position:relative

绝对定位的盒子垂直居中：position:absolute;

​                                               top:50%；

​												margin-top:-自己高度一半；

堆叠顺序z-index属性是一个没有单位的正整数，数值大的能够压住数值小的

绝对定位用来制作“压盖”，“遮罩”效果

绝对定位用来结合CSS精灵使用

绝对定位可以结合JS实现动画

### 固定定位

不管页面如何卷动，它永远固定在那里

position:fixed;

top:100px；

left:100px;   

固定定位只能以页面为参考点，没有子固父相这个性质

固定定位脱离标准文档流

用途：返回顶部，楼层导航

### 边框的三要素

solid   实线

dashed   虚线

dotted     点状线

border-shadow:x偏移  y偏移    模糊   rgba颜色；

border-shadow：前加inset表示内阴影

 border-radius 表示圆角的半径

### css背景

背景照片background-image: url(图片路径)               或者none

背景平铺background-repeat: repeat          no=repeat

background-repeat:repeat-x         repeat-y

background-size:     ;   contain和cover是特殊的两个值

contain表示将背景图片智能改变尺寸以容纳到盒子里

cover表示将背景图片智能改变尺寸以撑满盒子

background-clip属性用来设置元素的背景裁切到哪个盒子

border-box，背景延伸至边框

border-box，背景延申至内边，不会绘制到边框处

content-box，背景被裁切至内容区

background-attachment 决定背景图像是在视口内固定还是随着它的区块滚动

fixed，自己滚动条不动，外部滚动条不动

local，自己滚动条动，外部滚动条动

scroll，自己滚动条不动，外部滚动条动（默认值）

 背景位置background-position: x     y;

参数为x坐标与y坐标

CSS精灵：将多个小图标合并制作到一张图片上，使用background-position属性单独显示一个

CSS精灵可以减少HTTP请求数，加快网页显示速度。缺点也很明显：不方便测量，后期改动麻烦

线性渐变：盒子的background-image属性可以用linear-gradient（）形式创建线性渐变背景

背景图像固定（背景附着）

径向渐变：盒子的background-image属性可以用radial-gradient（）形式创建径向渐变背景

background:rgba(0,0,0,0.3)

最后一个参数是alpha透明度，取值范围在0~1之间

### 2D与3D转换

旋转变形：将transform属性的值设置为rotate（），即可实现旋转变形

transform：rotate（45deg）；

transform-origin：    

缩放变形：将transform属性的值设置为scale（），即可实现缩放变形

transform：scale（） 

斜切变形transform:  skew(    ，  )

位移变形     transform:translate()    位移变形也会”老家留坑“

将transform属性的值设置为 rotateX()或者rotateY(),即可实现绕横轴，纵轴旋转。 

perspective属性用来定义透视强度，可以理解为”人眼到舞台的距离“单位是px

当元素进行3D旋转后，即可继续添加translateX（），translateY(), translateZ()属性让元素在空间进行移动

### 过渡

transition过渡属性是CSS3浓墨重彩的特性，过度可以为一个元素在不同的样式之间变化自动添加”补间动画“

transition：width   1s  linear  0s

width：什么属性要过度

1s  ：动画时长

linear：变化速度曲线

0s：延迟时间 

所有数值类型的属性，都可以参加过度，比如width，height，left，top，border-radius

背景颜色和文字盒子都可以被过度

所有变形（包括2D和3D）都能被过度

 如果要所有属性都参与过度，可以写all

transition-property   哪些属性要过度

transition-duration   动画时间

transition-timing-function  动画变化曲线（缓动效果）

transition-delay  延迟时间

常用缓动参数：ease    linear   ease-in  ease-out    ease-in-out

### 动画的定义

可以使用@keyframes来定义动画，keyframes表示”关键帧“，在项目上线前，要补上@-webkit-这样的私有前缀

定义动画@keyframes r动画名字{

​						

```
	from {

​									transform：rotate（0）；			

​									}

​									to{

​										transform：rotate（360deg）；

​										}

​									}
```

定义动画后，可以使用animation属性调用动画

animation：r  1s  linear  0s   x；

第五个参数是动画的执行次数，infinite为永远执行

如果想让动画的第2，4，6.....（偶数次）自动逆向执行，那么加上alternate参数即可 

animation：movelr  2s  linear  0s  infinite  alternate;

如果想让动画停止在最后结束状态，那么要加上forwards

animation:changeToCircle  1s  linear  0s  forwards;

  



​              























 





 

