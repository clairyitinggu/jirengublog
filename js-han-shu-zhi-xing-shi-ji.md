# JS 函数的执行时机

1.  解释为什么如下代码会打印 6 个 6

```
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```

因为这里的i是一个全局变量，会在`setTimeout`循环结束之后才会打印出来，当循环结束的时候，i已经是6了，因此会打印出6个6

2. 写出让上面代码打印 0、1、2、3、4、5 的方法

   ```
   
   for(let i = 0; i<6; i++){
     setTimeout(()=>{
       console.log(i)
     },0)
   }
   ```

   因为JS在for和let一起用的时候会加东西，每次循环会多创建一个i

3. （可选内容）除了使用 for let 配合，还有什么其他方法可以打印出 0、1、2、3、4、5

   第一种：使用闭包

   ```
   let i 
   for(i = 0; i<6; i++){
     !function(j){
         setTimeout(()=>{
           console.log(j)
         },0)
     }(i)
   }
   ```

   第二种：利用const关键字

   ```
   let i
   for(i = 0; i<6; i++){
       const x = i
       setTimeout(()=>{
         console.log(x)
       })
   }
   ```

   第三种：for in

   ```
   let arr=[1, 2, 3，4，5]
   for(i in arr){
   console.log(i)
   }
   ```

   

