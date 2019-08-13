## hdfs创建一个文件的流程

1. 客户端通过ClientProtocol协议向RpcServer发起创建文件的RPC请求。
2. FSNamesystem封装了各种HDFS操作的实现细节，RpcServer调用FSNamesystem中的相关方法以创建目录。
3. 进一步的，FSDirectory封装了各种目录树操作的实现细节，FSNamesystem调用FSDirectory中的相关方法在目录树中创建目标文件，并通过日志系统备份文件系统的修改。
4. 最后，RpcServer将RPC响应返回给客户端。



[参考文章](<https://monkeysayhi.github.io/2018/02/07/%E6%BA%90%E7%A0%81%7CHDFS%E4%B9%8BNameNode%EF%BC%9A%E5%88%9B%E5%BB%BA%E6%96%87%E4%BB%B6%EF%BC%881%EF%BC%89/>)

