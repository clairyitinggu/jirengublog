# JS 对象基本用法

## 内容1：声明对象的两种语法

```
let obj = {'name': 'frank','age':18}
let obj = new Object({'name':'frank'})
console.log({'name':'frank','age':18})
```



## 内容2：如何删除对象的属性

delete obj.xxx或delete obj['xxx']即可删除obj的xxx属性

请区分**属性值为undefined**和**不含属性名**

```javascript
var obj = {name:'frank', age:18}
obj.name = undefined
obj 
>{name:undefined, age:18}
var obj2 = {name:'frank',age:18}
delete obj.name
>true
obj
>{age:18}
delete obj['name']
>true//<======'name'这个属性被删除，js不会报错
'name' in obj <=======看name在不在obj中
>false
'age' in obj
>true
name in obj
>false<========name没有被声明过，是个空值，所以是false

```

## 内容3：如何查看对象的属性

读属性也叫查看所有属性

## 查看自身所有属性

```
Object.keys(obj)//查看所有keys
Object.values(obj)//查看所有values
Object.entries//茶蛋所有keys和values
```

## 查看自身+共有属性

```
console.dir(obj)
或者自己依次用Object.keys打印出obj.__proto__
```

判断一个属性是自身的还是共有的

```
'toString' in obj //true in不管是自己的还是共有的
obj.hasOwnProperty('toString')//false
```

## 内容4：如何修改或增加对象的属性

### 修改或增加属性（写属性）

### 直接赋值

```
let obj = {name: 'frank'}//name是字符串
obj.name = 'frank' //name 是字符串
obj['name'] = 'frank'
obj[name] = 'frank' //错， 因name值不确定
obj['na' + 'me'] = 'frank'
let key = 'name'; obj[key] = 'frank'
let key = 'name'; obj.key = 'frank' //错
因为obj.key等价于obj['key']
```

### 批量赋值

批量赋值是ES6新出的语法

```
Object.assign(obj,{age:18, gender:'man'})
//这段代码的意思是把{age:18, gender:'man'}赋值给obj
```

### 修改或增加共有属性

### 无法通过自身修改或增加共有属性

```
let obj = {}, obj2 = {}//共有toString
obj.toString = 'xxx'只会在改obj自身属性
obj2.toString还是在原型上
```

### 我偏要修改或增加原型上的属性

```
obj.__proto__.toString = 'xxx'//不推荐用__proto__
Object.prototype.toString = 'xxx'
```

上面这两个指向同一个地址

一般来说，不要修改原型，会引起很多问题

### 修改隐藏属性

不推荐使用\_\_proto\_\_

```
let obj = {name:'frank'}
let obj2 = {name:'jack'}
let common = {kind:'human'}
obj.__proto__ = common
obj2.__proto__ = common
```

### 推荐使用Object.create

```
let obj = Object.create(common)
obj.name = 'frank'
let obj2 = Object.create(common)
obj2.name = 'jack'
```

规范大概的意思是，要改就已开始就改，别后来再改

## 内容5：'name' in obj和obj.hasOwnProperty('name') 的区别

'name' in obj判断不管是自己的还是共有的属性,而obj.hasOwnProperty('name') 只判断自己有的属性