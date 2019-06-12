## 基础准备

在使用 `swoft` 之前你需要具备一些服务端编程基础理论，在传统的`php-fpm`开发模式下 你基本不需要担心“资源释放”、“共享变量”等相关的问题。

不过你不用担心，在 2.x 版本， `swoft` 的开发和在 `php-fpm` 模式下开发一样简单，如果你有用过 `Laravel` 框架，那么你入手 `swoft` 会更快，因为 `swoft` 在 `DataBase` 和 `Redis` 的使用方法上与 `Laravel` 基本一致。


## 入门须知
在 swoole 常驻内存开发模式中，不要用超全局变量共享数据，但可以使用 `Context` 代替。也不要使用 `curl` 扩展，因为 `curl` 暂不支持协程化，具体原因你可以参考[swoole 官方文档](https://wiki.swoole.com/wiki/page/965.html)  

当然 `guzzlehttp` 底层也是 `curl` 驱动的，因此也暂不支持。不过作为替代，你可以使用 `swoft` 自带的 `httpClient` ，它和 `guzzlehttp` 一样方便快捷，还原生支持并发调用。你再也不用担心，因为某个`http`请求时间过长，导致服务器`CPU` 疯涨。

不过在接下来 swoole 会支持curl 扩展，相信不会等待太久。

当然还有很多细节在文档中有仔细描述，在这就不一一描述了。

