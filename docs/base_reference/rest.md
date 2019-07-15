# Rest_client

## RequestStatus
`RequestStatus`是一个枚举类，包含了请求所返回的各种状态。

枚举值：

- ready: 请求被创建，值为0。
- success: 请求成功(请求返回值为2xx)，值为1。
- failed: 请求失败(请求返回值不为2xx)，值为2.
- error: 请求错误，值为3。

## Request
** vnpy.api.rest.Request()**

创建一个新请求。

参数：

- method: 请求方法，一个字符串，如`"POST"`。
- path: 请求的路径，一个字符串。
- params: 请求的参数，一个字典。
- data: 发送的数据，一个字典。
- header: 请求头，一个字典。
- callback: 回调函数，默认为空。
- on_failed: 请求失败时的回调函数，默认为空。
- on_error: 请求错误的回调函数，默认为空。
------

## RestClient
** vnpy.api.rest.RestClient() **

创建一个`RestClient`客户端。
------

** vnpy.api.rest.RestClient.init(url_base, proxy_host, proxy_port) **
初始化客户端。

参数：

- url_base: api基础地址。
- proxy_host: 代理服务器地址。
- proxy_port: 代理服务器端口。
-----
