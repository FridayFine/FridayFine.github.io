---
title: 前端开发的长度单位
date: 2018-06-24 12:22:43
tags: css
---

参考《CSS世界》一书，本文将总结前端开发中遇到的一些单位（相对单位和绝对单位），有待进一步扩充。

<table class="showline bg-none">
<tr>
    <td rowspan="7" class="vertical-mid"> 长度单位 </td>
    <td rowspan="6" class="vertical-mid"> 相对长度单位 </td>
    <td rowspan="4" class="vertical-mid"> 相对字体长度单位 </td>
    <td> ex: 小写字母x的高度 </td>
</tr>
<tr>
    <td> em: '中'等汉字的高度，相对自己</td>
</tr>
<tr>
    <td> rem(CSS3单位): 相对根元素</td>
</tr>
<tr>
    <td> ch(CSS3单位): 阿拉伯数字0的宽度</td>
</tr>
<tr>
    <td> 相对视区长度单位：</td>
    <td> vh, vm, vmin, vmax</td>
</tr>
<tr>
    <td> 其它相对长度单位： </td>
    <td> rpx </td>
</tr>
<tr>
    <td> 绝对长度单位 </td>
    <td colspan="2"> px, pt, cm, mm, pc</td>
    
</tr>
</table>

## 1em, 1ch
1em：当前一个font-size的大小，即：当前元素中，如果有汉字时，汉字的高度<br/>
1ch: 1个0的宽度<br/>
6ch: 6个0的宽度

## em & rem

|    |        参照物 |         应用场景         |
|:---|:--------------|:-------------------------|
| em | 相对于当前元素 | 适用于图文内容展示的场景，对此进行弹性布局 <br/> eg:设置margin单位em,随着字号的变化，margin值不同   |
| rem| 相对于根元素   | 适用于带缩放性质的弹性布局 |

## rpx(小程序开发用到的单位)
小程序规定：所有设备的屏幕宽度均为750rpx<br/>
那么，对于iPhone6(375*667)：750rpx = 375px, 1rpx = 0.5px<br/>
所以，小程序开发时常使用iphone6, iphone7, iphoneX(它们的宽度均为375)的模拟器