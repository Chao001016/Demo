## ES6声明变量的新方式let和const

两者共有的特点（相较于var和function）

①不存在变量提升

②暂时性死区

③不允许重复声明



关于这两个输出结果不一样，除了有let块级作用域的问题，还有for循环执行的问题

```
for(let i=1; i<10; i++;) {
	setTimeout(()=>{
		console.log(i)
	})
}
上面for循环的执行过程类似以下
    {
        let i=0;
        {
            setTimeout(() => {
                console.log(i)
            })
        }
    }
    {
        let i=1;
        {
            setTimeout(() => {
                console.log(i)
            })
        }
    }
```

```
for(var i=1; i<10; i++;) {
	setTimeout(()=>{
		console.log(i)
	})
}
上面代码执行过程类似以下，只有var和let关键字的区别
    {
        var i=0;
        {
            setTimeout(() => {
                console.log(i)
            })
        }
    }
    {
        var i=1;
        {
            setTimeout(() => {
                console.log(i)
            })
        }
    }
```

