#### Nginx代理配置规则

![image-20220515164704030](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220515164704030.png)

Nginx代理处理规则：

通过location确定已匹配部分和基础部分，如果没有已匹配部分，则无需走代理。

已匹配部分保持不变，基础部分通过target进行适当调整

1.如果target含有 /，那么基础部分转为 target的值

2.如果target不含有/，那么基础部分转为 target连接location



#### Vue代理配置规则

![image-20220515200328478](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220515200328478.png)

Vue代理处理规则:

通过扫描请求路径，根据匹配规则，将请求路径三个部分。基础部分转化为target，可以根据pathRewrite来重写匹配关键词在转发请求中的内容。



Vue代理路径解析流程图

![image-20220515205808912](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220515205808912.png)



共同点和不同点：两者都可以做反向代理。在代理规则上，Vue有更好的匹配关键词重写配置，通俗易懂。