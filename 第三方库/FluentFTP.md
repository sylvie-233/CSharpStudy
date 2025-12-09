# FluentFTP


## 基础介绍

FTP客户端库


## 核心内容
```yaml
FluentFTP:
    FtpClient: # ftp客户端
        Config:
            DataConnectionType: # 连接类型（主动模式、被动模式）
            IsConnected:
            LogToConsole: # 日志输出
            Connect(): # 连接
            DeleteFile():
            Disconnect():
            DownloadFile():
            GetListing(): # 列出目录
            UploadFile():
```