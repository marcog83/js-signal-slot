#Signal#
Signals and slots are used for communication between objects. The signals and slots mechanism is a central feature of Qt.
```signal``` is emitted when a particular event occurs. A ```slot``` is a function that is called in response to a particular ```signal```.
You can connect as many signals as you want to a single slot, and a signal can be connected to as many slots as you need.

##Usage

You create an instance of ```Signal```, connecting a ```slot``` function as callback.
```javascript
var ticked=new Signal();
ticked.connect(function(now){
 console.log(now)
})

```

then later you ```emit``` an async event

```javascript
setInterval(function(){

ticked.emit(new Date().getTime())

},500);
```

#API

* ```connect(slot,scope)``` Connects the signal this to the incoming ```slot``` function. ```scope``` is the scope where slot runs.

* ```connectOnce(slot,scope)``` Connects once the signal this to the incoming ```slot``` function. ```scope``` is the scope where slot runs.

* ```disconnect(slot,scope)``` The given ```slot``` are disconnected.. ```scope``` is the scope where slot runs.

* ```disconnectAll()``` Disconnects all slots connected to the signal.

* ```emit(*)``` Dispatches an event into the signal flow. You can pass in any Object.
