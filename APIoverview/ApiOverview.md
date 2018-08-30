## 核心API

### 创建observable
observalbe(value)

Observable值可以是JS原始类型，引用类型，plain object, class instance,array and maps

注意:
* 1. 如果value是一个ES6Map, 一个新的ObservableMap会被返回，如果你想对入口也生效，那么使用ES6Map很不错。
* 2. array
* 3. object without a prototype, clone its current
* 4. if value is object with a prototype, a JavaScript primitive, or function, there will no change made to the value. if you need Boxed Observable, you can do the following
  * 1. Call observable.box(value)
  * 2. @observalbe in the class defination
  * 3. Call decorate()
  * 4. Use extendObservable() to introduce properties on a class defination

注意:
* 1. to create dynamically keyed object, always use maps! Only initially existing properties on an object will be made observalbe, although new ones can be added using extendObservable 