模块化

https://zhuanlan.zhihu.com/p/451284087

（编写思路：每个实现方式的特点以及如何使用。实现中遇到的问题以及如何解决，如循环依赖。异步加载的实现方式。引入顺序问题。）

早期通过简单的IIFE实现模块化。如果要达到一个模块依赖另一个模块，则需要将被依赖模块作为参数传入依赖模块。

关于模块化的规范的实现细节以及使用方式暂时没有深入了解，以后再进行了解。



##### Common JS 模块化

node所制定的模块化，使用时需要依赖Node环境

特点：同步依赖；服务器端

使用方式：通过module和exports来暴露模块，通过require来引入模块



##### AMD（asynchronous module definition）规范

这是一种规范，该模块化是要达到异步加载的效果，requireJs以该规范实现了模块化。

特点：异步依赖和同步依赖；模块命名；依赖前置

requier JS使用方式：通过define来定义模块，通过require来加载模块，define在定义模块时也可以依赖其它模块。

define([String], [Array2], Object|Function), 第一个参数为模块名(可选)，第二个参数为所依赖的模块(可选)，第三个参数为模块内容



##### CMD（common module definition）规范

特点：按需加载；依赖就近；同步依赖



##### Common JS 引入模块的顺序问题

先加载核心模块（node的内置模块）

然后按照路径加载，以此查找后缀名.js,.json,然后查找子目录是否有/index

再往查找父目录的node_modules对NPM包的查找，父目录找不到就往父目录的父目录找,直到没有为止



##### AMD如何处理循环依赖

A、B为两个模块如果A依赖B，B也依赖A，那么B中的A为undefined.



##### 一个require多次依赖相同的模块

AMD使用requiere依赖模块时，如果依赖一个模块两次，那么则会执行该模块一次，将依赖结果保留，第二次依赖时直接获取依赖结果

删除缓存的方法 https://blog.csdn.net/weixin_39579483/article/details/118241417


