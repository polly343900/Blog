var 变量提升，一个function就是一个作用域
let,const 块作用域 {块作用域}
此外，const一旦设置就不能修改，因此const变量声明和初始化要一起。```const a;```是错误的。
TDZ简单说，

  ```js
  // 声明之前的区域都是TDZ,如果访问变量会返回ReferenceError错误
  let a = 1;
  ```

默认函数也有TDZ

  ```js
      // 正常执行,默认参数从左往右，执行到“b=a”时，a已经声明好了
    (function(a, b = a) {
        a === 1;
        b === 1;
    }(1, undefined));
  ```

  ```js
    //a的初始化尝试读取b的时候b在TDZ中
  (function(a = b, b) {}(undefined, 1)); // ReferenceError
  ```

[参考文献](http://bosn.me/articles/es6-default-param/#tdztemporal-dead-zone)
