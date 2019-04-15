对象的定义：我们可以先看看 JavaScript 标准对基于对象的定义，这个定义的具体内容是：“语言和宿主的基础设施由对象来提供，并且 JavaScript 程序即是一系列互相通讯的对象集合”。在英文中是对一切事物的总称

基于类的面向对象
基于原型的面向对象

原型相比于类，没有类的继承等特性，所以采用的实现方式就是：不是真正去复制原型对象，而是使用新对象持有一个原型的引用

原型系统的标志：
1、所有对象都有私有字段[[prototype]]，就是对象的原型
2、读一个属性，如果对象本身没有，就会继续去访问原型，

对象的特点：
1、唯一标识性
2、有状态
3、有行为

对象分类：
1、宿主对象：由宿主环境提供的对象，它们的行为完全由宿主环境决定
2、内置对象：js的提供的对象
* 固有对象：随js运行时创建而自动创建的对象实例 https://www.ecma-international.org/ecma-262/9.0/index.html#sec-well-known-intrinsic-objects
* 原生对象：通过Array，RegExp等内置构造器或特殊语法创建的对象
![原生对象](./imgs/原生对象.png)

* 普通对象：由{},Object构造器或者class关键字定义类创建的对象，能被原型继承


js对象的两个属性：
 ##### 数据属性
 ```
 value：属性的值
 writable：属性是否可被赋值
 enumerable： 是否可枚举
 configurable： 属性是否能被修改
 ```

 ##### 访问属性

 ```
 getter：函数或者undefined，取值被调用
 setter：函数或者undefined，设置被调用
 enumerable： 是否可枚举
 configurable： 属性是否能被修改

 ```


 ### object构造方法

 object.assign()
 ```
 var b = object.assign({}, {a: 1});
 console.log(a); // {a: 1};
 ```

 Object.create(proto, [propertiesObject])
 ```
var o = {}; // 以字面量方式创建的空对象就相当于:o = Object.create(Object.prototype);

o = Object.create(Object.prototype, {
  // foo会成为所创建对象的数据属性
  foo: { 
    writable:true,
    configurable:true,
    value: "hello" 
  },
  // bar会成为所创建对象的访问器属性
  bar: {
    configurable: false,
    get: function() { return 10 },
    set: function(value) {
      console.log("Setting `o.bar` to", value);
    }
  }
});
 ```
 
Object.getPrototypeOf(object)
```
const prototype1 = {};
const object1 = Object.create(prototype1);

console.log(Object.getPrototypeOf(object1) === prototype1);
// expected output: true
  
```
Object.setPrototypeOf(obj, prototype)
```
// 相对于 Object.prototype.__proto__ ，它被认为是修改对象原型更合适的方法
```

Object.defineProperty(obj, prop, descriptor)
```
Object.defineProperty(obj, "key", {
  enumerable: false,
  configurable: false,
  writable: false,
  value: "static"
});
```

Object.defineProperties(obj, props)
```
var obj = {};
Object.defineProperties(obj, {
  'property1': {
    value: true,
    writable: true
  },
  'property2': {
    value: 'Hello',
    writable: false
  }
  // etc. etc.
});
```
 Object.entries()
 Object.freeze()
 Object.getOwnPropertyDescriptor()
 Object.getOwnPropertyNames()
 Object.getOwnPropertySymbols()
 Object.is()
 Object.isExtensible()
 Object.isForzen()
 Object.isSealed()
 Object.keys()
 Object.preventExtensions()
 Object.seal()
 Object.values()