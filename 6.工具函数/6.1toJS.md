toJS(value, option?)

* 转化成一个js结构
* 支持observable数组，对象，map，和原始值primitive.
* 计算值和不可枚举值不会出现在结果中。
* 环可以被检测到，可以关闭这个选项提高性能