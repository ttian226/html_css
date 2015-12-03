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

#### transition & transform & animation

* http://www.zhangxinxu.com/wordpress/2010/11/css3-transitions-transforms和animation使用简介与应用展示/#two

#### transition

1. 配合hover使用，当鼠标移入指定元素生效

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

上面的例子可以这么写

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
  transition: all 4s ease;  //把transition放到这里，但不会立即生效，需要hover触发后生效
}

.trans_list:hover {
  background-color: #beceeb;
  color: #333;
  border-radius: 25px;
  margin-left: 89%;
  transform: rotate(360deg);
}
```

这里把ease类去掉

```html
<div id="transBox" class="trans_box">
  <div class="trans_list">ease</div>
</div>
```

2. 使用js控制

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
  transition: all 4s ease;
}

/*动态加入active类，可以触发transition*/
.active {
  background-color: #beceeb;
  color: #333;
  border-radius: 25px;
  margin-left: 89%;
  transform: rotate(360deg);
}
```

```html
<div id="transBox" class="trans_box">
  <div class="trans_list">ease</div>
</div>
```

```javascript
setTimeout(function () {
  $('.trans_list').addClass('active');
}, 1000);
```

* 这里通过js动态添加active类
* 不能直接`$('.trans_list').addClass('active')`不会产生动画。需要使用setTimeout动态添加才能产生动画

#### 使用animation

```css
#sport {
  position: relative;
  width: 500px;
  height: 400px;
  border: 1px solid #dddddd;
}

#staff {
  position: absolute;
  left: 10px;
  bottom: 10px;
  z-index: 3;
  width: 180px;
  height: 8px;
  overflow: hidden;
  background: #dddddd;
  border-radius: 3px;
  line-height: 20;
  animation: mystaff 3s linear;
}

#ball {
  position: absolute;
  z-index: 3;
  left: 90px;
  bottom: 20px;
  width: 30px;
  height: 30px;
  line-height: 20;
  overflow: hidden;
  background: #F6D66E;
  border-radius: 15px;
  box-shadow: 0 0 10px rgba(204, 102, 0, .8);
  animation: myball 3s linear;
}

/*自定义动画myball，这里定义了球的移动*/
@keyframes myball {
  0% {
    transform: translate(0, 0);
  }
  5% {
    transform: translate(-90px, -100px);
  }
  18% {
    transform: translate(0, -350px);
  }
  35% {
    transform: translate(200px, 0);
  }
  46% {
    transform: translate(380px, -160px);
  }
  60% {
    transform: translate(250px, -350px);
  }
  78% {
    transform: translate(60px, 0);
  }
  100% {
    transform: translate(0, 0);
  }
}
/*自定义动画mystaff，定义了滑杆的移动*/
@keyframes mystaff {
  0% {
    transform: translate(0, 0);
  }
  6% {
    transform: translate(260px, 0);
  }
  20% {
    transform: translate(300px, 0);
  }
  30% {
    transform: translate(300px, 0);
  }
  40% {
    transform: translate(200px, 0);
  }
  65% {
    transform: translate(40px, 0);
  }
  79% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(0, 0);
  }
}
```

```html
<div id="sport">
  <span id="ball">弹球</span>
  <span id="staff">滑杆</span>
</div>
```

* @keyframes用来自定义动画
* 百分比是和移动时间对应的，反应的是某个时间点的状态。例如`animation: mystaff 3s linear`的移动时间是3秒，匀速运动。
* 使用animation不像transition那样必须要hover来触发，它可以立即触发。当然也可以用hover来触发

例如使用hover触发滑杆运动

```css
#staff {
  position: absolute;
  left: 10px;
  bottom: 10px;
  z-index: 3;
  width: 180px;
  height: 8px;
  overflow: hidden;
  background: #dddddd;
  border-radius: 3px;
  line-height: 20;
}
#staff:hover {
  animation: mystaff 3s linear;
}
```
