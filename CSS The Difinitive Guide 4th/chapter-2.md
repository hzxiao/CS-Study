## 选择器

###  基本样式规则

`h2 {color: gray;}`

### 元素选择器

- 元素选择器大多时候是HTML元素，但不全是这样。
- 文档元素是最基本的选择器。

### 分组选择器

多个选择器使用同个样式，选择器间逗号分隔，如`h2, p{color: gray;}`

### 分组声明

```css
h1 {font: 18px Helvetica;} 
h1 {color: purple;}
h1 {background: aqua;}
```

可以写成如下写法：

```css
h1{
	font: 18px Helvetica; 
    color: purple; 
    background: aqua;
}
```


### 类选择器和ID选择器

除了文档元素的选择器外，还有类选择器和ID选择器，它们是独立于文档元素的方式来指定样式。

#### 类选择器

为了将一个类选择器的样式和元素关联，必须将class属性指定为一个适当的值。为元素应用样式时需要在类名前加一个点号（.）。如下所示

```html
<p class="warning">When handling plutonium, care must be taken to avoid
the formation of a critical mass.</p>
<p>With plutonium, <span class="warning">the possibility of implosion is very real, and must be avoided at all costs</span>. This can be accomplished by keeping the various masses separate.</p>
```

```css
.warning {font-weight: bold;}
```

```css
p.warning {font-weight: bold;}
```

#### ID选择器

ID选择器和类选择器类似，但也有一些重要的区别：

1. ID选择器前面是井号（#）。
2. ID选择器引用id属性中的值，该值在文档中唯一。

#### 属性选择器

可以根据属性和属性的值选择元素进行样式应用。如下：

```css
h1[class] {color: silver;}
```



### 文档结构

树形结构

#### 理解父子关系

根据树形结构理解节点的父子关系等。

#### 后代选择器

```css
h1 em {color: gray;}
```

#### 选择子元素

```css
h1 > strong {color: red;}
```

#### 选择相邻兄弟元素

```css
h1 + p {margin-top: 0;}
```

选择紧接在一个h1元素后出现的所有段落，h1要和p元素有共同的父元素。

#### 选择后面兄弟元素

```css
h2 ~ol {font-style: italic;}
```

两个元素不用相邻

### 伪类选择器

#### 组合伪类选择器

```css
a:link:hover {color: red;} 
a:visited:hover {color: maroon;}
```

#### 结构化伪类

结构化伪类选择器是基于DOM元素在DOM树中的结构特性(跟父节点或者兄弟节点的关系)进行匹配选择，比如某个元素的第一个子节点，最后一个节点等等。

##### 选择根元素

```css
:root {border: 10px dotted gray;}
```

##### 选择空元素

```css
p:empty {display: none;} 
```

##### 选择唯一子元素

```css
img:only-child {border: 1px solid black;}
```

It selects elements when they are the only child element of another element. 

##### 选择第一和最后一个子元素

The pseudo-class :first-child is used to select elements that are the first children of
other elements. 

```css
p:first-child {font-weight: bold;} 
li:first-child {text-transform: uppercase;}
```

The pseudo-class :last-child is used to select elements that are the last children of
other elements. 

```css
p:last-child {font-weight: bold;}
li:last-child {text-transform: uppercase;}]
```

##### 选择第一个和最后一个类型

**:first-of-type**表示一组兄弟元素中其类型的第一个元素。

**:last-of-type**表示一组兄弟元素中其类型的最后一个元素。

**:only-of-type** 代表了任意一个元素，这个元素没有其他相同类型的兄弟元素

##### 选择第n个子元素

**:nth-child(an+b)** 首先找到所有当前元素的子元素，然后按照位置先后顺序从1开始排序，选择的结果为第（an+b）个元素的集合（n=0，1，2，3...

```css
p:nth-child(1) {font-weight: bold;} 
li:nth-child(1) {text-transform: uppercase;}
```

##### 选择第n个类型

**:nth-of-type()** 匹配文档树中在其之前具有 `*a*n+*b*-1` 个相同兄弟节点的元素，其中 n 为正值或零值。简单点说就是，这个选择器匹配那些在相同兄弟节点中的位置与模式 *an+b* 匹配的相同元素。

```html
/* 在每组兄弟元素中选择第四个 <p> 元素 */
p:nth-of-type(4n) {
  color: lime;
}
```

#### 动态伪类

##### 超链接

**:link**伪类选择器是用来选中元素当中的链接。它将会选中所有尚未访问的链接，包括那些已经给定了其他伪类选择器的链接（例如:hover选择器，:active选择器，:visited选择器）

**:visited** 表示用户已访问过的链接。

##### 用户动作

`:focus`表示获得焦点的元素（如表单输入）。当用户点击或触摸元素或通过键盘的 “tab” 键选择它时会被触发。

`:hover` 用于用户使用指示设备虚指一个元素（没有激活它）的情况。:hover伪类可以任何伪元素上使用。

`:active` 匹配被用户激活的元素。

##### target伪类

**:target** 代表一个唯一的页面元素(目标元素)，其`id` 与当前URL片段匹配 .

```css
/* 选择一个ID与当前URL片段匹配的元素*/
:target {
  border: 2px solid black;
}
```

例如, 以下URL拥有一个片段 (以#标识的) ，该片段指向一个ID为section2的页面元素:

```html
http://www.example.com/index.html#section2
```

若当前URL等于上面的URL，下面的元素可以通过 :target选择器被选中：

```html
<section id="section2">Example</section>
```