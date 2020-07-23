---
title: swiper 分页器样式
date: :year/:month/:day/
tags:
	- swiper
	- 前端开发
---

> ### 基础设置
```html
<div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide">slider1</div>
      <div class="swiper-slide">slider2</div>
      <div class="swiper-slide">slider3</div>
    </div>
    <div class="pagination"></div>
  </div>
```
```javascript
new Swiper('.swiper-container', {
    loop: true,
    pagination: {
        el: ".pagination", //给分页器一个容器，css类名选择器
        type: "bullets",   //bullets 圆点| custom 自定义 | fraction 分式 | progressbar 进度条 | 
        bulletElement: "li"
    }
})
```

> ### bullets 圆点样式

```css
//默认状态
.swiper-pagination-bullet {
    background: #ffffff;
    opacity: 1;
}
//焦点状态
.swiper-pagination-bullet-active {
    background: #00a0e9;
}
```

