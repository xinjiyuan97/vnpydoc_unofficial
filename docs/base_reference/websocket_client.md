# WebsocketClient

**WebsocketClient.init(host, proxy_host, proxy_port, ping_interval, header)**

初始化网络接口。

参数：

- host: 目标服务器地址
- proxy_host: 代理服务器地址
- proxy_port: 代理服务器端口

------

**WebsocketClient.start()**

启动网络接口。

------

**WebsocketClient.stop()**

终止网络接口。

------

**WebsocketClient.join()**

等待所有线程结束。

------

**WebsocketClient.send_packet(packet)**

向API地址发送请求。

首先将dict函数转化为json格式文件，然后发送给服务器。

参数：

- packet: 一个dict类型，为所需要传递的参数。

------

**unpack_data(data)**

将得到的data数据序列化为dict类型。

参数：

- data: 一个str类型，为需要序列化的字符串。
