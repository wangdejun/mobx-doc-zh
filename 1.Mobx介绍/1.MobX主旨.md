### 定义你的状态并且使其可观察
```js
import {observable} from 'mobx';

var appState = observable({
	timer: 0
})
```
### 创建视图响应状态变化
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
ReactDOM.render(<TimerView appState={appState}/>, document);
```

## 修改状态

* 第三件事你需要修改状态

```js
appState.resetTimer = action(function reset(){
	appState.timer = 0;
})
setInterval(action(function tick(){
	appState.timer +=1;
}), 1000)
```
