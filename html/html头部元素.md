
#### [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)

`<head>` 元素是所有头部元素的容器。`<head>` 内的元素可包含脚本，指示浏览器在何处可以找到样式表，提供元信息，等等。

以下标签都可以添加到 head 部分：`<title>`、`<base>`、`<link>`、`<meta>`、`<script>` 以及 `<style>`


#### [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)

`<link>` 标签最常用于连接样式表

```html
<link href="style.css" rel="stylesheet">
```

#### [`<title>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

`<title>` 用于定义文档的标题

```html
<title>Awesome page title</title>
```

#### [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)

`<style>` 用于为html文档定义样式

```html
<style type="text/css">
body {
  color:red;
}
</style>
```
注: *如果不设置type，则默认为text/css*


#### [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base)

`<base>` 标签为页面上的所有链接规定默认地址或默认目标（target）

```html
<base href="http://www.baidu.com">
```
*设置页面上所有链接为`http://www.baidu.com`*

```html
<base href="http://www.baidu.com" target="_blank">
```
*设置页面上所有链接为`http://www.baidu.com`，并且在新标签页打开*


#### [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)

`<meta>` 标签提供关于 HTML 文档的元数据。元数据不会显示在页面上。

* meta 元素被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据
* `<meta>`标签始终位于 head 元素中
* 元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务

*一些例子:*

```html
<!-- 定义html4文档的字符编码为utf-8 -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

<!-- charset是html5中特有属性，用来定义字符编码 -->
<meta charset="utf-8">

<!-- 3秒后页面跳转到http://www.baidu.com -->
<meta http-equiv="refresh" content="3; url=http://www.baidu.com">

<!-- 设置页面每隔10秒刷新一次 -->
<meta http-equiv="refresh" content="10">

<!-- 定义页面的描述 -->
<meta name="description" content="Free Web tutorials on HTML, CSS, XML">

<!-- 定义页面的关键字 -->
<meta name="keywords" content="HTML, CSS, XML">

<!-- 定义作者 -->
<meta name="author" content="ttian226">
```

*设置IE浏览器兼容模式，[参考链接](http://wenrunchang123.iteye.com/blog/1397507)*

```html
<meta http-equiv="X-UA-Compatible" cotent="IE=edge,chrome=1">
```

*可以让部分国产浏览器默认采用高速模式渲染页面*

```html
<meta name="renderer" content="webkit">
```

