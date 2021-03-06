# Change log

### Version 0.1.3

- 不再受到1.99G限制;如果是大于1.99G的文件，请使用`FileDownloadLargeFileListener`作为监听器，使用对应的`getLargeFileSoFarBytes()`与`getLargeFileTotalBytes()`接口
- 性能优化: 部分接口跨进程通信不受binder thread 阻塞。
- 依赖okhttp，从2.7.0 升到2.7.1

### Version 0.1.2

- 优化线程消化能力
- 修复大队列任务暂停可能部分无效的问题
- 修复大队列并行下载时一定概率下载已经完成回调囤积延后回调的问题

### Version 0.1.1

- event线程区分敏捷线程池与其他线程池，减少资源冗余强制、内部稳定性以及消化能力与性能，
- 添加自动重试接口，新增用户指定如果失败自动重试的次数

### Version 0.1.0

- FileDownloadStatus 由`int`改为`byte`，该参数会频繁的在IPC时被拷贝
- 优化串行or并行任务时，筛选task在准备数据时就筛选好，减少冗余操作，更加安全
- 优化串行任务执行保证使用更可靠的方式

### Version 0.0.9

- 将调用start(启动任务)抛独立线程处理，其中的线程是通过共享非下载进程EventPool中的线程池(可并行8个线程)

### Version 0.0.8

- initial release