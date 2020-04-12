# markdown

[markdown语法](https://www.jianshu.com/p/191d1e21f7ed)


# 引入vuep，实现边编辑边预览

## `hexo-theme-yilia`模版

在`hexo-theme-yilia`模板中引入`vuep`，使得在页面上可以边编辑，边预览效果，需要做的是：

1. 在`themes/hexo-theme-yilia/layout/_partial/css.ejs`中加入引入的CSS文件

``` html
<link rel="stylesheet" type="text/css" href="<%=config.root%>./vuep-css/vuep.css">
```

2. 在`themes/hexo-theme-yilia/layout/_partial/footer.ejs`中加入引入的js文件

 ``` html
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

## `hexo-theme-next`模版

在`hexo-theme-next`模板中引入`vuep`，使得在页面上可以边编辑，边预览效果，需要做的是：

1. 在`themes/hexo-theme-next/layout/_macro/post.swig`中，class为`post-body`的节点上加入代码`id="post-body"`, 如下：

``` html
<div id="post-body" class="post-body……
```

2. 在`themes/hexo-theme-next/layout/_partial/css.ejs`中引入CSS文件

``` html
<link rel="stylesheet" type="text/css" href="/vuep-css/vuep.css">
```

3. 在`themes/hexo-theme-next/layout/_partial/footer.swig`中引入js文件, 并加入挂载节点

 ``` html
    <script src="/vuep-js/babel.min.js"></script>
    <script src="/vuep-js/vue.min.js"></script>
    <script src="/vuep-js/vuep.min.js"></script>
    <script>
        new Vue({
            el: '#post-body'
        })
    </script>
 ```

4. 在`themes/hexo-theme-next/source/`目录下放入两个文件夹`vuep-css`和`vuep-js`，用来存放上面引入的css和js文件
```
|-- vuep-css
|      |-- vuep.css
|-- vuep-js
|      |-- babel.min.js
|      |-- vue.min.js
|      |-- vuep.min.js
```




# hexo

## 相关链接

[hexo官方文档](https://hexo.io/zh-cn/)

## 【问题】使用table表格正常格式，出现一些空行

有以下两种解决方案： 

1. `<table>`标签之间不换行书写，写在一起，牺牲可读性

2. `<table>`标签外面用代码包括

``` html
{% raw %}
    html tags & content
{% endraw %}
```

参考资料：

[[BUG]-hexo中插入HTML表格出现过多空白](https://www.zhaokangbing.com/posts/programming/2017-02-04-too-much-whitespace-for-html-table-in-hexo/)

[上面链接作者提到的issue](https://github.com/hexojs/hexo/issues/2391)