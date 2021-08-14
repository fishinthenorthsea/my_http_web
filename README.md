# my_http_web



基于Linux的多线程静态Web服务器

应用技术：Linux、C、Socket、TCP

项目描述：
1.利用epoll+ET模式作为IO多路复用的实现方式，使用reactor模型，加上线程池避免线程频繁创建，销毁的开销。

2.利用有限状态机处理http报文的分割和处理，区分GET/POST，长连接和短链接

3.加入小根堆定时器处理不活跃连接，处理完所有epoll_wait返回的请求后会更新一次定时器，将超时的连接断开

4.加入数据库连接池，实现了get/post的简易登陆

