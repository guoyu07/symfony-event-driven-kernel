# 核心组件
了解核心的构成组件实现的功能，学习如何单独使用它们，为了解Symfony的事件核心做准备。这一章只是简短介绍各个组件的功能，你需要自己引入这些组件进行相应的学习和练。

Symfony的核心由几个组件组成：HttpFoundation、HttpKernel、DependencyInjection、EventDispatcher等。这些组件实现了Symfony的事件驱动核心的大部分功能。

你可以通过[组件的官方文档](http://symfony.com/doc/current/components/index.html)来了解和使用它们，你可以根据文档编写一些测试脚本来熟悉组件的用法和用途，帮助自己更好的了解组件的功能。

## HttpFoundation
Symfony的[`HttpFoundation`](http://symfony.com/doc/current/components/http_foundation/index.html)组件对PHP默认的一些全局参数以及生成响应数据的一些函数做了一层面向对象方式的封装，替代默认的PHP对`Request`和`Response`的操作方式。本段大部分内容摘抄自[官方文档](http://symfony.com/doc/current/components/http_foundation/introduction.html)。

针对`Request`中的`HTTP请求头`、`URL数据`、`POST数据`、`COOKIE数据`、`SESSION据`、`文件上传`和`SERVER参数`进行了封装，可以通过`Symfony\Component\HttpFoundation\Request`类的实例化对象取得这些参数。对于[`Session`](http://symfony.com/doc/current/components/http_foundation/sessions.html)管理也同样进行了封装，统一处理。

针对`Response`进行了统一的封装处理，使原本PHP散乱的无法管理各处响应的问题得以解决，通过构建一个`Symfony\Component\HttpFoundation\Response`对象来统一管理响应数据。可以控制`响应的HTTP头`、`响应内容`、`COOKIE`等等。可以响应`html内容`、`JSON数据`、`托管静态文件`、`数据流形式响应`等等常见的给客户端响应的数据形式。

## HttpKernel
