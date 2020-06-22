## HTTP协议中关于压缩传输的规定
```
客户端向服务器请求中带有：Accept-Encoding:gzip, deflate 字段，向服务器表示，客户端支持的压缩格式（gzip或者deflate)，如果不发送改消息头，服务器是不会压缩的
服务端在收到请求之后，如果发现请求头中含有Accept-Encoding字段，并且支持该类型的压缩，就对响应报文压缩之后返回给客户端，并且携带Content-Encoding:gzip消息头，表示响应报文是根据该格式压缩过的
客户端接收到请求之后，先判断是否有Content-Encoding消息头，如果有，按该格式解压报文。否则按正常报文处理
```