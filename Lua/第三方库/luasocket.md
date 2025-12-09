# luasocket


## 基础介绍


lua 网络连接库
`luarocks install luasocket`

要求安装openssl库，配置：
- CRYPTO_INCDIR → 指向 include 文件夹
- CRYPTO_LIBDIR → 指向 lib 文件夹


## 核心内容
```yaml
ltn12: # 流式读写（HTTP 用）
     
socket:
    ftp:
    http:
        request(): # http请求
            ---
            body:
            status_code:
            headers:
            status_text:
    smtp:
    url:
    bind(): # 服务端口绑定
        accept(): # 接收客户端连接
    select(): # 多路复用
    tcp(): # 获取tcp连接
        close():
        connect():
        receive():
        send():
        settimeout():
    udp(): # 获取udp连接
        send():
        setpeername():
```