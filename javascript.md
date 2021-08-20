# javascript

## 深入理解 Error

https://zhuanlan.zhihu.com/p/25338849

https://zh.javascript.info/error-handling

## 原型链

为什么父类的 prototype 不能直接赋值给子类的 prototype？

修改子类的 prototype 时也会影响父类的 prototype，违背了继承的原则。

new 和 Object.create 的区别？

同样都是返回一个实例，区别在于 Object.create 的原型有使用者指定

Object.create 相当于

```js
//实现一个隐藏函数
function F() {}
//函数的原型设置为参数传进来的原型
F.prototype = proto;
// 返回一个F函数的实例，即此实例的__proto__指向为参数proto
return new F();
```
![image](https://user-images.githubusercontent.com/13379027/130176378-7912fbcb-c437-4097-b5dc-9af3265f193c.png)

