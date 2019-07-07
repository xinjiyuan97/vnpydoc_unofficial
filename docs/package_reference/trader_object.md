# Object
`vnpy.trader.Object`包里面包含了vnpy中使用的各类数据交换对象。

## BaseData
`vnpy.trader.Object.BaseData`是vnpy基础的数据对象类型，是其余数据类型的父类。

## TickData
`vnpy.trader.Object.TickData`是vnpy中的Tick数据类型。

`TickData`中包含的数据有

- 上一笔成交信息
- 订单快照
- 日内交易统计信息

## BarData
`vnpy.trader.Object.BarData`保存了每个交易周期内的蜡烛图信息。

## OrderData
`vnpy.trader.Object.OrderData`存储的是最近一笔的订单信息。

**OrderData.is_active()**

检测订单状态，若订单仍有效则返回`True`否则返回`False`。

**OrderData.create_cancel_request()**

## TradeData
`vnpy.trader.Object.TradeData`用来保存所有的订单信息。

## PositionData
`vnpy.trader.Object.PositionData`用来保存用户的持仓信息。

## AccountData
`vnpy.trader.Object.AccountData`用来保存平衡？冻结资金和可用资金。

## LogData
`vnpy.trader.Object.LogData`用来记录日志信息，显示在GUI界面或日志文件中。

## ContractData
`vnpy.trader.Object.ContractData`记录了每一个合约的基础信息。

## SubscribeRequest
`vnpy.trader.Object.SubscribeRequest`向某个接口订阅Tick数据。

## OrderRequest
`vnpy.trader.Object.OrderRequest`向某个接口发送下单请求。

** OrderRequest.create_order_data(orderid, gateway_name) **

根据下单请求创建一个订单数据。

根据订单产生一个新的撤单请求。

参数：

- orderid: 订单的id。
- gateway_name: 接口名称
返回值

- OrderData

## CancelRequest
`vnpy.trader.Object.CancelRequest`向某个接口发送撤单请求。

## HistoryRequest
`vnpy.trader.Object.HistoryRequest`查找通过某个接口的历史订单。