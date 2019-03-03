---
title: BFC的产生与应用
date: 2018-11-17 19:57:41
tags: css
---

BFC, Block Formatting Context, 块级格式化上下文，它的形成源自于元素特征和常见CSS属性值的设置，在一些前端问题的处理方面也有着重要的应用
<!-- more -->

## BFC的产生

当满足一下任何一个条件时，将会产生BFC：

1. 根元素(`<html>`)或其它包含它的元素
2. 浮动(`float`) : 取值left/right/inherit, 取值不为none
3. 定位(`position`) : 绝对定位元素，position取值absolute/fixed, 不为relative/static
4. `display` :    
    4.1 行内块  display: inline-block   
    4.2 表格  dispaly: table-cell   
    4.3 表格标题  dispaly: table-caption   
    4.4 弹性盒子  display: flex/inline-flex
5. `overflow` : overflow取值hidden/scroll/auto/inherit, 不为visible

综上，除了根元素`<html>`的特征外, BFC的形成受到`float, position, display, overflow`属性值的设置，这些属性的默认属性值如下：

| 属性名   | 默认属性值     |
| :------- | -------------: |
| float    | none           |
| position | static         |
| display  | 视具体元素而定 |
| overflow | visible        |

除`display`的默认属性值受限于元素类型外，其它几个属性的默认属性值都构不成形成BFC的条件。换句话说，初始时一个元素能否构成BFC取决于它的`display`值.


<span>
   {% asset_img BFC-reason.png %}
</span>