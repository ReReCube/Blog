# let命令与const

在let命令所在的代码块内有效
  
  
 ```
var a = [];
for (var i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 10

var a = [];
for (let i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 6
```

const常量

# 变量赋值
```
let a = 1;let b = 2;let c = 3;  =>  let [a, b, c] = [1, 2, 3];
```
# 箭头函数
eg.
```
//----------------------------------------
//我们来写个闭包函数。实现个简单的记数器。
//用两种方式：1、普通的匿名函数，2、吊炸天的箭头函数 =>
//初始从 1 起步，步长就用 ++ 好了。 
var init = 1;

//这是一个闭包函数。 匿名函数写法
var closure = function(n) {
    //本例中内层函数是调用了外层函数的参数来实现的闭包。
    //当然你也可以向往常那样在这一层里声明局部变量，给下面的内层函数用。
    //var n = 100;
    return function() {
        return n++;
    };
}(init);

//这是对应的箭头函数
var closure = (n => (() => n++))(init);

//----------------------------------------
// 下面我们跑个循环，测试下输出的效果,正常来说会看到 1到20 这些数字。
var arr = [];
for (var i = 0; i < 20; i++) {
    arr.push(closure());
}
alert(arr);
```
## 匿名函数与箭头函数
```
//这是一个普通的匿名函数
var foo = (function() {
    return "hello world1!";
});

//这是对应的箭头函数
var foo = () => "hello word2-1!";
//也可以写成这样:
var foo = (() => "hello word2-2!");
//或这样：
var foo = (() => 
    "hello word2-3!"
);
//测试
alert(foo());//弹窗：hello word！
```
## 带参数的匿名函数 与 箭头函数 
```
//这是一个带参数的匿名函数
var foo = (function(n) {
    return n*10;
});

//这是对应的箭头函数
var foo = (n) => n*10;
//顺便说一句：向上面没有参数的情况，括号是一定要的。但是如果只有一个参数可以省掉,像这样：
var foo = n => n*10;

//测试
alert(foo(1));// 10
alert(foo(2));// 20
alert(foo(3));// 30
```
## 多行语句
```
//匿名函数
var name = function name(str) {
   str = "---------" + str + "-----------";
   return str;
};

//对应的箭头函数
var name = str => {
   str = "---------" + str +"-----------";
   return str; 
}
```
## 返回一个对象
```
//匿名函数
var boy = function boy(str) {
  return { name: str };
};

//对应的箭头函数
var boy = str => ({name:str}); 

//测试
var boy = str => ({name:str}); 
var me = boy("recube");
alert(me.name);
```



