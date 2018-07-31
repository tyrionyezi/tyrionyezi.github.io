### js中类型判断的机制
- typeof判断
```
适合基本数据类型
和函数的判断
```
- instanceof 原型链判断
```
iframe、window会失效
```
- Object.prototyObject.prototype.toString
```
适合基本数据类型和内置对象的检测，遇到null、undefined会失效
```