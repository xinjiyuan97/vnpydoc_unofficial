# Trader.engine
这个包里包含了vnpy的核心引擎`MainEngine`，以及交易用的三个功能类引擎，分别为，`LogEngine`，`OmsEngine`，`EmailEngine`。

## MainEngine
这个类是VNPY的核心类，用来协调各个模块。

**MainEngine**
```Python
mainEngine = Trader.engine.MainEngine(event_engine)
```
创建一个主引擎。

参数：

- event_engine: 一个事件引擎，参见`vnpy.event.EventEngine`，默认为空，使用预设的事件引擎。

**MainEngine.add_engine(engine_class)**
```Python
funcEngine = mainEngine.add_engine(BaseEngine)
```
给主引擎添加一个功能引擎。

参数：

- engine_class: 需要添加的功能引擎的类别。

返回值：

- engine: 添加的事件引擎。

**MainEngine.add_gateway(gateway_class)**
```Python
gateway = mainEngine.add_gateway(BaseGateway)
```
给主引擎添加一个gateway。

参数：

- gateway_class: 需要添加的gateway的类别。

返回值：

- gateway: 所添加的gateway。

**MainEngine.add_app(app_class)**
```Python
app = mainEngine.add_app(BaseApp)
```
给主引擎添加一个功能类App。

参数：

- app_class: 需要添加的app的类别。

返回值：

- app: 所添加的app。

**MainEngine.init_engines()**

添加全部的内置功能引擎。创建时自动调用，无需手工调用。

**MainEngine.write_log(msg, source)**
```Python
msg = "Hello World!"
source = "Human"
mainEngine.write_log(msg, source)
```
添加日志信息。

参数：

- msg: 所需要添加的信息内容，字符串。
- source: 信息的发送者，默认为空。


**MainEngine.get_gateway(gateway_name)**

在主引擎的接口表中寻找名为`gateway_name`的接口。若不存在则返回空。

**MainEngine.get_engine(engine_name)**

在主引擎的接口表中寻找名为`engine_name`的功能引擎。若不存在则返回空。

**MainEngine.get_default_setting(gateway_name)**

在主引擎的接口表中寻找名为`gateway_name`的底层接口，并返回其默认设置。若不存在则返回空。

**MainEngine.get_all_gateway_names()**

返回一个`list`，内容为主引擎中的全部底层接口名称。

**MainEngine.get_all_apps()**

返回一个`list`，内容为主引擎中的全部app（对象）。

**MainEngine.get_all_exchanges()**

返回一个`list`，内容为所有账户的现金？

**MainEngine.connect(setting, gateway_name)**

按照设定的参数`setting`连接指定的接口。
```Python
```

**MainEngine.subscribe(req, gateway_name)**

订阅名为`gateway_name`的接口的`req`的行情信息。
```Python
```

**MainEngine.send_order(req, gateway_name)**

向名为`gateway_name`的接口下单。
```Python
```

**MainEngine.cancel_order(req, gateway_name)**

向名为`gateway_name`的接口取消订单。
```Python
```

**MainEngine.send_orders(reqs, gateway_name)**

向名为`gateway_name`的接口进行批量下单。
用法同`MainEngine.send_order`。

**MainEngine.cancel_orders(reqs, gateway_name)**

向名为`gateway_name`的接口进行批量取消订单。
用法同`MainEngine.cancel_order`。

**MainEngine.query_history(reqs, gateway_name)**

查询通过接口`gateway_name`的全部订单情况。
```Python
```

**MainEngine.stop()**
关闭依次关闭全部功能引擎，关闭接口，关闭主引擎。

## BaseEngine
一个抽象类，用以实现功能类。

## LogEngine

## OmsEngine

## EmailEngine