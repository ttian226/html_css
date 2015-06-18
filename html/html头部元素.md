
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

