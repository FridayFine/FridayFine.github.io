---
title: 盒模型下的DOM节点尺寸
date: 2018-06-23 12:09:08
tags: html
---

本文总结了基于盒模型的元素尺寸的获取方法:总结了四种情况下(content, content+padding, content+padding+boder, content+padding+border+margin)盒子尺寸的原生JS和jQuery获取方式。

<span>
   {% asset_img border-model.jpg %}
</span>

盒模型将元素节点内容(content)由内向外逐步扩展，依次添加padding, border, margin. 从而一个小盒子逐步扩展为包含不同内容的一个个大盒子。这里为了方便表述分别称4个盒子为1~4号盒子：content(1号盒子), content+padding(2号盒子), content+padding+boder(3号盒子), content+padding+border+margin(4号盒子).

在不同场景下，需要获取不同盒子的尺寸。下表中总结了原生JavaScript和jQuery获取四种大小的盒子尺寸的方法：


| 参数 | 原生JS | jQuery |
|:-------|:------------------------------------------------------------------------|-----------------------:|
| content | currentStyle+width/height(IE) <br/> getComputedStyle+width/height(非IE) | width() <br/> height() |
| content+padding | clientWidth <br/> clientHeight | innerWidth() <br/> innerHeight() |
| content+padding+border | offsetWidth <br/> offsetHeight | outerWidth() <br/> outerHeight() |
| content+padding+border+margin | / | outerWidth(true) <br/> outerHeight(true) |

## 4号盒子的原生js获取方法
目前暂未找到由原生js直接获取包含4号盒子(content+padding+border+margin)尺寸的方法，可以通过3号盒子尺寸结合元素的margin值计算得出。

## 1号盒子的原生js获取方法
对于IE浏览器和非IE浏览器，由于浏览器内置方法不同，根据原生JS和jQuery获取内容的方法也不同，具体方法用代码表示如下：
```
var boxDOM = document.getElementById("box");
var width0, height0;
if (window.getComputedStyle) {
    width0 = window.getComputedStyle(boxDOM).width;
    height0 = window.getComputedStyle(boxDOM).height;
} else {
    width0 = boxDOM.currentStyle.width;
    height0 = boxDOM.currentStyle.height;
}
alert('width0--- ' + width0 + ';  height0--- ' + height0);
```

## 文档高度 & 窗口高度

文档高度：HTML文档的高度，获取方法：$(document).height()
<br/>
窗口高度：浏览器视口的高度，获取方法：$(window).height()
