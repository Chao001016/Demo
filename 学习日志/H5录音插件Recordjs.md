------

#### 使用须知

使用局限：需要http协议，https以及其他未试过，但是file协议不行。可以部署到Nginx上面。

使用前注意：由于用到了浏览器的录音权限，因此确保网页能够拥有录音权限

------



从http://www.jq22.com 下载源码后，dist和lib下面都有recorder.js，script引入dist下的recorder.js

require lib下的index即可使用



dist下面是打包后的文件，lib下面是开发用的文件。

源码中包含_createClass和 _classCallCheck，应该是ES6转ES5的代码。

该功能的实现包含两个大类：Record和InlineWorker。

Record类为对外访问类。该类包含了对外访问方法和属性。

![1653465414328](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653465414328.png)

record,stop,exportWAV,clear为常用的方法，其他属性和方法目前尚未发现利用价值。

该功能用到了worker开启子进程，从而与主线程进行交互。

录音的实现原理：

当recorder被初始化后，便一直运行onaudioprocess函数，从而监听isrecording，如果recording为真，则进行录音操作。将录音数据储存到recBuffers，调用exportWAV的时候将录音数据转为Blob对象返回。

![1653473664419](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653473664419.png)

dist文件下的InlineWorker有自己手动实现，而lib下则通过npm包实现。



​	