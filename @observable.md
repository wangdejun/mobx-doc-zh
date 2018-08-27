```js
import {observable, computed} from 'mobx'

class OrderLine{
	@observable price = 0;
	@observalbe amount = 1;
	
	@computed get total(){
		return this.price * this.amount
	}
}
```
