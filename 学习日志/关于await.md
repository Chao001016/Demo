# await的使用

Q.await会阻塞执行进程么？

A:不会

Q：使用await后，会影响代码执行的顺序么？

A：会

Q：await是通过影响JS引擎事件轮询的顺序么？

A：不是

Q：使用await在等待结果的过程中，JS引起还能执行其他代码吗？如果能，这是否违背了JS是单线程语言的特性？

A：在等待的过程中，能够执行其他代码，但这并不违背JS是单线程语言的特性。将await语句运行完毕后，JS执行栈就算运行完了（可以轮询任务队列了），在await后的Promise状态变为fullfilled（rejected）时将await之后的代码进入了微任务队列中（不包含紧贴await之后的代码).



![image-20220517152128985](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220517152128985.png)