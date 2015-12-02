### css问题集合

#### div中的文字如果是中文可以自动换行，如果是英文或数字不能自动换行，需要手动控制样式换行


#### 关于float

* http://www.cnblogs.com/polk6/archive/2013/07/25/3142187.html
* http://www.zhangxinxu.com/wordpress/2010/01/css-float%E6%B5%AE%E5%8A%A8%E7%9A%84%E6%B7%B1%E5%85%A5%E7%A0%94%E7%A9%B6%E3%80%81%E8%AF%A6%E8%A7%A3%E5%8F%8A%E6%8B%93%E5%B1%95%E4%B8%80/
* http://www.zhangxinxu.com/wordpress/2010/01/css-float%E6%B5%AE%E5%8A%A8%E7%9A%84%E6%B7%B1%E5%85%A5%E7%A0%94%E7%A9%B6%E3%80%81%E8%AF%A6%E8%A7%A3%E5%8F%8A%E6%8B%93%E5%B1%95%E4%BA%8C/
* 绝对定位的元素脱离了文档流，而浮动元素依旧在文档流中，而这造成的显示上的差异就是：同处于文档流中的文字实体不会与浮动元素重叠，而会与绝对定位元素重叠


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

#### word-wrap和word-break的区别

* http://www.cnblogs.com/2050/archive/2012/08/10/2632256.html

#### transition

1 配合hover使用

```css
.trans_box {
  padding: 20px;
  background-color: #f0f3f9;
}

.trans_list {
  width: 10%;
  height: 64px;
  background-color:#486AAA;
  color:#fff;
  margin: 10px 0px;
  text-align: center;
}

/*hover触发后transition才生效*/
.trans_list:hover {
  background-color: #beceeb;
  color: #333;
  border-radius: 25px;
  margin-left: 89%;
  transform: rotate(360deg);
}

/*这里ease中的transition不是立即生效的，当hover后才会生效。all代表hover里的所有属性*/
.ease {
  transition: all 4s ease;
}
```

```html
<div id="transBox" class="trans_box">
  <div class="trans_list ease">ease</div>
</div>
```
