## 选择器
![简单选择器](./imgs/css简单选择器.png)

### 全体选择器
```
* {
    font-size: 0;
}
```

### 类选择器
```
div {
    color: #fff;
}
```

### id选择器
```
#id {
    color: #f2f4f6;
}
```

### 类选择器
```
.cls {
    color: #fff;
}
```

### 属性选择器
```
/* 存在title属性的<a> 元素, 如下选择 */
a[title] {
  color: purple;
}

/* 存在href属性并且属性值匹配"https://example.org"的<a> 元素, 如下选择 */
a[href="https://example.org"] {
  color: green;
}

/* 存在href属性并且属性值包含"example"的<a> 元素, 如下选择 */
a[href*="example"] {
  font-size: 2em;
}

/* 存在href属性并且属性值结尾是".org"的<a> 元素, 如下选择 */
a[href$=".org"] {
  font-style: italic;
}

/* 存在href属性并且属性值以"#"开始的<a> 元素, 如下选择 */
a[href^="#"] {
  background-color: gold;
}

/* 所有包含`lang`属性并且属性值是以空格为间隔的值列表, 值列表中包含"en-us"的<div> 元素, 
设置css color:blue. */
div[lang~="en-us"] {
  color: blue;
}

/* 所有包含`lang`属性并且属性值匹配"zh"或 以"zh-"为开头的<div> 元素, 设置css color:red, 无论
   简体中文 (zh-CN) 或者 繁体中文 (zh-TW). */
div[lang|="zh"] {
  color: red;
}
```

### 伪类选择器
* 树结构关系伪类选择器
```
/* 匹配文档树的根元素 随着scope css等的出现还是很有用的 */
:root {
  --main-color: hotpink;
  --pane-padding: 5px 42px;
}

/* 没有子元素的元素 子元素只可以是元素节点或文本（包括空格） */
div:empty {
  background: lime;
}


:nth-child(an+b)
/* 与nth-child基本一样，只是从从结尾处反序计数，而不是从开头处 */
:nth-last-child(an+b)

element:nth-of-type(an+b) => nth-child(an+b of element)

:nth-last-of-type(an+b)

:first-child()

:last-child()

/* 属于某个父元素的唯一一个子元素 */
:only-child()
```
* 链接与行为伪类选择器
```
:link

:hover

:active

:focus

/* 浏览器hash指定元素 */
:target
```
* 逻辑伪类选择器
```
:not(X)

/* 类名不是 `.fancy` 的 <p> 元素 */
p:not(.fancy) {
  color: green;
}

/* 非 <div> 或 <span> 的元素 */
body :not(div):not(span) {
  font-weight: bold;
}
```
* 其他伪类选择器