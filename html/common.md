## HTTP协议中关于压缩传输的规定
> 客户端向服务器请求中带有：Accept-Encoding:gzip, deflate 字段，向服务器表示，客户端支持的压缩格式（gzip或者deflate)，如果不发送改消息头，服务器是不会压缩的

> 服务端在收到请求之后，如果发现请求头中含有Accept-Encoding字段，并且支持该类型的压缩，就对响应报文压缩之后返回给客户端，并且携带Content-Encoding:gzip消息头，表示响应报文是根据该格式压缩过的

> 客户端接收到请求之后，先判断是否有Content-Encoding消息头，如果有，按该格式解压报文。否则按正常报文处理

## 在spring boot中开启gzip
```
在application.properties 中加入如下配置即可
server.compression.enabled=true
server.compression.mime-types=application/json,application/xml,text/html,text/xml,text/plain
```

## Configuring gzip encoding for play
```
To enable the gzip filter, add the Play filters project to your libraryDependencies in build.sbt:
libraryDependencies += filters

Now add the gzip filter to your filters, which is typically done by creating a Filters class in the root of your project:
import javax.inject.Inject
import play.api.http.DefaultHttpFilters
import play.filters.gzip.GzipFilter
class Filters @Inject() (gzipFilter: GzipFilter) extends DefaultHttpFilters(gzipFilter)

The Filters class can either be in the root package, or if it has another name or is in another package, needs to be configured using play.http.filters in application.conf:
play.http.filters = "filters.MyFilters"

https://www.playframework.com/documentation/2.5.x/GzipEncoding
```

## CSRF
```
Cross-Site Request Forgery protection
```
