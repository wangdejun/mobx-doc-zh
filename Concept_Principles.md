
##1 State
##2 Derivations
	* Ther user inteface
	* Derived data, such as the number of todos left
	* Backend integrations like sending changes to the server.
two kinds of derivations
	* Computed values.
	* Reactions


## Illustration
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
