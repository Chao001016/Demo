Q: Web Worker的作用是什么？

Web Work用于创建子线程，子线程与主线程执行互不影响。



Q: Web Worker的局限性是什么？

①Worker开启的进程无法使用File协议来访问资源。

②Woker进程需要与主线程文件同源。

③Woker线程的环境与主线程的环境不一致。

④Worker线程与主线程交互的方式过于单一且交互方式不够好，不利于一些数据格式

