*Proxy用于修改某些操作的默认行为，等同于在语言层面做出修改，所以属于一种‘元编程’，即对编程语言进行编程*     

[^ES6基础入门第三版]: 

​																										

Proxy能修改的默认行为有(13个)：

参数意义： tar源对象，key键名，value键值，rec Proxy实例, ctx源函数的上下文， args源函数的参数

**get(tar,key,rec )**: 拦截属性的读

**set(tar,key,value)**: 拦截属性的赋值

**apply(tar, ctx, args)**: 拦截函数的调用。拦截()、call、apply操作

**has(tar,key)**: 拦截检测属性是否存在的操作(in操作)。拦截in操作，但不拦截for in。如果源对象禁止扩展（Object.preventExtensions(obj)）或不可配置(configurable:false)，则无法隐藏目标对象的属性,否则报错。

**construct(tar, args, rec)**:拦截new操作。

**deleteProperty(tar, key)**:拦截delete操作.如果该方法抛出错误或返回false则无法删除。

**defineProperty(tar, key, decriptor)**:拦截Object.defineProperty操作.如果原对象不可扩展或某个属性不可写、不可配置，则代理器的defineProperty不可更改这两个设置。defineProperty返回false则添加新属性时抛出错误。

**getOwnPropertyDescriptor(tar,key)**:拦截Object.getOwnPropertyDescriptor()操作

**getPrototypeOf(target)**:拦截对象获取原型操作.包括Object.getPrototypeOf、属性读取原型、instanceof、Reflect.getPrototypeOf

**isExtensible()**:拦截Object.isExensible操作

**ownKeys()**:拦截自身属性的读取操作.Object.getOwnPropertyNames(),Object.getOwnPropertySymbols(),Object.keys()

**preventExtensions()**: 拦截Object.preventExtensions()操作

**setPrototypeOf()**:拦截Object.setPrototypeOf()操作

