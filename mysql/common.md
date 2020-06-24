## max_connect_errors设置
```
错误连接超过 max_connect_errors 会被mysql报一个错误，
MySql Host is blocked because of many connection errors; unblock with 'mysqladmin flush-hosts'

我个人理解为 mysql的一种防护机制，防止ip攻击

原因：同一个ip在短时间内产生太多（超过mysql数据库max_connection_errors的最大值）中断的数据库连接而导致的阻塞

解决方法：
1、提高允许的max_connection_errors数量（治标不治本）：
    修改max_connection_errors的数量为1000： set global max_connect_errors = 1000;
    查看是否修改成功：show variables like '%max_connection_errors%';
2、直接flush hosts;
3、重启业务服务，因为max_connection_errors太大的时候，大概率会出现大量的CLOSE_WAIT，需要重启业务服务
    tcp        1      0 123.56.87.167:8070      123.56.87.167:47072     CLOSE_WAIT  off (0.00/0/0)
    tcp        1      0 123.56.87.167:8070      123.56.87.167:49038     CLOSE_WAIT  off (0.00/0/0)
    tcp        1      0 123.56.87.167:8070      123.56.87.167:48816     CLOSE_WAIT  off (0.00/0/0)
    tcp        1      0 123.56.87.167:8070      123.56.87.167:47164     CLOSE_WAIT  off (0.00/0/0)
    tcp        1      0 123.56.87.167:8070      123.56.87.167:47298     CLOSE_WAIT  off (0.00/0/0)
```