toStream

Converts an expression to an observable stream( TC39 Observalbe/RxJS observable). 只要有订阅者，就提供对表达式的跟踪

Parameters
* expression
* fireImmediately boolean(by default false)

Examples

const user = observable({firstName:"C.S", lastName:"Lewis"})
Rx.Observable.from(mobxUtils.toStream(()=>user.firstName + user.lastName))
.scan(nameChanges => nameChanges+1,0).subscribe(nameChanges=>console.log("Changed name", nameChanges, "times"))

Returns IObservableStream<T>
