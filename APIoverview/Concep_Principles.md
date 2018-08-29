
## 1 状态State
## 2 衍生和计算值 Derivations
	* Ther user inteface
	* Derived data, such as the number of todos left
	* Backend integrations like sending changes to the server.
two kinds of derivations
	* Computed values.
	* Reactions


## 3.show the code Illustration
```js
import {observable, autorun} from 'mobx'

var todoStore = observable({
	todos:[],
	get completedCount(){
		return this.todos.filter(todo => todo.completed).length;
	}
})

autorun(function(){
	console.log("Completed %d of %d items", 
		todoStore.completedCount, 
		todoStore.todos.length
	);
})

```
