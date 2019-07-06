# Event
 包`event`类型包含了vnpy的基础事件类型`Event`和主事件引擎`EventEngine`。

## 事件Event
**vnpy.event.Event**
`Event`是vnpy的一个基础事件类型，用于事件引擎之间传递事件信息。
```Python
event = Event(type, data)
```
生成一个Evnet对象，其中type为一个字符串，data为任意类型的数据。

## 事件引擎vnpy.event.EventEngine
`EventEngine`主要用来进行事件分发，同时提供时钟供计时使用。

**EventEngine**
```Python
eventEngine = EventEngine(interval = 1)
```
- 参数：interval产生时钟的周期，int类型，单位为秒。

**EventEngine.start()**
```Python
eventEngine.start()
```
启动事件引擎，事件引擎将会开始分发事件，并开始计时。

**EventEngine.stop()**
```Python
eventEngine.stop()
```
关闭事件引擎。

**EventEngine.put()**
```Python

engineEngine.put(event)
```
将事件插入事件队列。

**EventEngine.register(type, handler)**
```Python
def process(event: Event)
    ...
engineEngine.register('typeName', process)
```
在事件引擎中注册一个句柄，该句柄将接收所有类型为`typeName`的事件。
参数：
- type: 一个字符串，用来表明句柄所接受的事件的类型。
- handler: 一个输入为`Event`，输出为`None`的句柄。

> **注意：一个类型的句柄在同一个事件引擎中只能被注册一次。**
> 

**EventEngine.unregister(type, handler)**
在事件引擎中注销一个句柄。
参数详见`EventEngine.register`。

**EventEngine.register_general(handler)**
```Python
def process(event: Event)
    ...
engineEngine.register_general(process)
```
在事件引擎中注册一个全局句柄，所有类型的事件都会被转发给该句柄。
参数：
- handler: 一个输入为`Event`，输出为`None`的句柄。

**EventEngine.unregister_general(handler)**
在事件引擎中注销一个全局句柄，所有类型的事件都会被转发给该句柄。
详细见`EventEngine.register_general`。