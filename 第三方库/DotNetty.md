# DotNetty


## 基础介绍

C# Netty库
.NET 平台的高性能网络通信框架，基于 Netty（Java）
```shell
dotnet add package DotNetty.Transport
dotnet add package DotNetty.Codecs
dotnet add package DotNetty.Buffers
dotnet add package DotNetty.Common
```


Bootstrap / ServerBootstrap -> EventLoopGroup -> Channel -> Pipeline -> ChannelHandler -> ByteBuf


## 核心内容
```yaml
DotNetty:
    Buffers: # 缓冲区
        IByteBuffer:
        Unpooled:
    Codecs: # 编/解码器
    Common:
        Concurrency:
    Transport: # 核心模块
        Bootstrapping: # 启动器
            Bootstrap: # 客户端启动器
                Channel(): # 设置连接通道
                ConnectAsync(): # 连接
                Group(): # 设置事件循环组
                Handler(): # 设置通道处理器
            ServerBootstrap: # 服务端启动器
                BindAsync(): # 端口绑定
        Channels: # 通道
            Sockets:
                TcpServerSocketChannel: # tcp服务端连接通道
                TcpSocketChannel: # tcp客户端连接通道
            ActionChannelInitializer:
            ChannelHandlerAdapter: # 通道处理适配器 实现IChannelHandler
                ChannelRead():
            IChannel: # 通道
                WriteAndFlushAsync(): # 发送消息
            IChannelHandler: # 处理事件的接口
            IChannelHandlerContext: # 通道处理上下文
                WriteAndFlushAsync:
            IChannelPipeline: # 通道处理管道
            MultithreadEventLoopGroup: # 事件循环组
                ShutdownGracefullyAsync(): # 关闭
```