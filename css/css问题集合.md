### css问题集合

#### div中的文字如果是中文可以自动换行，如果是英文或数字不能自动换行，需要手动控制样式换行


#### 关于float

* http://www.cnblogs.com/polk6/archive/2013/07/25/3142187.html


#### 关于line-height

* http://www.cnblogs.com/dolphinX/p/3236686.html
* 深入理解css的行高：http://www.cnblogs.com/rainman/archive/2011/08/05/2128068.html
* 设置垂直居中：http://www.zhangxinxu.com/wordpress/2009/11/css%E8%A1%8C%E9%AB%98line-height%E7%9A%84%E4%B8%80%E4%BA%9B%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3%E5%8F%8A%E5%BA%94%E7%94%A8/


#### em rem px的区别

* http://www.cnblogs.com/leejersey/p/3662612.html
* http://www.w3cways.com/1713.html


#### overflow:hidden可以清除float的影响

例如html:当子块是float时，会导致父节点宽度为0

```html
<style>
    .sub {
      width: 150px;
      height: 150px;
      float: left;
    }
</style>
<div class="parent">
  <div class="sub"></div>
  <div class="sub"></div>
  <div class="sub"></div>
  <div class="sub"></div>
</div>
```

当给父节点添加overflow:hidden时，会使得父节点重新设置高度

```html
<style>
    .parent {
        overflow: hidden;
    }
    .sub {
      width: 150px;
      height: 150px;
      float: left;
    }
</style>
<div class="parent">
  <div class="sub"></div>
  <div class="sub"></div>
  <div class="sub"></div>
  <div class="sub"></div>
</div>
```
