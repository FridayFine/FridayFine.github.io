## 链接

[markdown语法](https://www.jianshu.com/p/191d1e21f7ed)

[hexo官方文档](https://hexo.io/zh-cn/)


## 引入vuep，在边编辑边预览

目前使用到的模板是`hexo-theme-yilia`, 在该模板的基础上引入`vuep`，使得在页面上可以边编辑，边预览效果

需要做的是：

1. 在`themes/hexo-theme-yilia/layout/_partial/css.ejs`中加入引入的CSS文件

```
<link rel="stylesheet" type="text/css" href="<%=config.root%>./vuep-css/vuep.css">
```

2. 在`themes/hexo-theme-yilia/layout/_partial/footer.ejs`中加入引入的js文件

 ```
    <script src="/vuep-js/babel.min.js"></script>
    <script src="/vuep-js/vue.min.js"></script>
    <script src="/vuep-js/vuep.min.js"></script>
    <script>
        new Vue({
            el: '#js-content'
        })
    </script>
 ```

 3. 在`themes/hexo-theme-yilia/source/`目录下放入两个文件夹`vuep-css`和`vuep-js`，用来存放上面引入的css和js文件
```
|-- vuep-css
|      |-- vuep.css
|-- vuep-js
|      |-- babel.min.js
|      |-- vue.min.js
|      |-- vuep.min.js
```
