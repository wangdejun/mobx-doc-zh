## define your state and make it observable
```js
import {observable} from 'mobx';

var appState = observable({
	timer: 0
})
```

## Create a view that respond to changes in the state
```js
import {observer} from 'mobx-react'

@observer
class TimerView extends React.Component{
	render(){
		return (
		<button onClick = {this.onReset.bind(this)}>
			Seconds passed: {this.props.appState.timer}
		</button>
		)
	}
	
	onReset(){
		this.props.appState.resetTimer();
	}
}
```

ReactDOM.render(<TimerView appState={appState}/>, document);

## Modify the State

* the third thing to do is to modify the state

```js
appState.resetTimer = action(function reset(){
	appState.timer = 0;
})
setInterval(action(function tick(){
	appState.timer +=1;
}), 1000)
```
