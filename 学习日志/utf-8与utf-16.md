##### Q:UTF-8和UTF-16是什么？

A:是对Unicode字符集的编码方式



##### Q:Unicode是什么？

Unicode，统一码，其中使用二进制映射了各种字符。JavaScript程序是使用Unicode字符集编写的。

Unicode将字符分为17组，其中每组最多有2的16次方个字符。其中最重要的一组为基本多文种平面，简称BMP



##### Q:JS如何表示Unicode呢？

*JS定义了转义序列，从而可以使用ASCII字符来表示Unicode字符,这些Unicode转义序列以\u开头，后跟4位十六禁止数字。*JS能够以两个\uxxxx\uxxxx的形式表示码点大于\uFFFF的字符。但是JS如何知道将两个\uxxxx当作一个字符解析呢？

![1653661736987](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653661736987.png)

根据以上的范围，JS将根据情况以一个双字节还是两个双字节进行解析。

*ES6新增的表达Unicode字符的方法\u{xxxxxx},目的是更好的支持大于16位的Unicode码点*（也只支持3字节）

Q: UTF-8的编码方式。

A:UTF-8能够



##### UTF-8编码规则

![1653672874805](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653672874805.png)

##### UTF-16编码规则

![1653674197608](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653674197608.png)

![1653674229411](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653674229411.png)



##### UTF-32编码规则

![1653674842927](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653674842927.png)

通过UTF-32可以看出，Unicode字符集最多包含2的32次方个字符，实际上目前远远少于这个数量，还有很多数维对应字符。

##### 知乎详解

https://zhuanlan.zhihu.com/p/386511092