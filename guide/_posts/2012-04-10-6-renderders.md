---
layout: post
title: RENDERDERS
caption: 自定义模板辅助方法
---

为组件模板渲染提供增强方法

{% highlight js %}
HelloWorld.RENDERERS = {
    xx: {
        yy: function(context) {
            //参数context 当前实例
            return "xx_" + context.get('name') + "_yy"
        }
    }
};
{% endhighlight %}

### html代码:

模板中对应的渲染增加方法为"\{\{id_xx_yy\}\}"

{% highlight html %}
{% raw %}
<div id="container1">
</div>
<script type="text/template" id="tmpl_helloword1">
    <div id="helloworld1">
        <span>Hello
            <span>{{helloworld1_xx_yy}}</span>
        </span>
    </div>
</script>
{% endraw %}
{% endhighlight %}

### js代码:

{% highlight js %}
KISSY.use('helloworld',function(S,HelloWorld){
    var helloworld = new HelloWorld({container:'#container1',tmpl:S.one('#tmpl_helloword1').html()});
    helloworld.render();
});
{% endhighlight %}

### demo：

{% demo guide/renderders %}

