# let命令与const
<p>
在let命令所在的代码块内有效</br>
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
</p>

# 变量赋值
<p>
let a = 1;let b = 2;let c = 3;  =>  let [a, b, c] = [1, 2, 3];
</p>
