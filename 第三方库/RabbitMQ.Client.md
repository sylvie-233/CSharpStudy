# RabbitMQ.Client



## 基础介绍

C# RabbitMQ客户端库
`dotnet add package RabbitMQ.Client`


## 核心内容
```yaml
RabbitMQ.Client:
    Events:
        BasicDeliverEventArgs: # 消息事件参数
        EventingBasicConsumer: # 消费者事件
            Received: # 事件消费回调 (model, ea)
    ConnectionFactory: # 连接工厂
        CreateConnection():
    IBasicProperties: # 消息属性（持久化、过期等）
    IConnection: # 连接
        CreateModel():
    IModel: # 连接通道
        BasicConsume: # 消息接收
            queue:
            autoAck:
            consumer: # 绑定消费者事件
        BasicPublish(): # 消息发布
            exchange:
            routingKey:
            basicProperties:
            body:
        QueueDeclare(): # 队列声明
            queue:
            durable:
            exclusive:
            autoDelete:
            arguments:
```