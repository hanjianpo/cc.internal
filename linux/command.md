## common

> scp -r java_pid653811.hprof web@10.223.53.140:/Users/web/dev/hprof/


## mac系统的环境变量修改
### 加载顺序为

> /etc/profile 

> /etc/paths 

> ~/.bash_profile 

> ~/.bash_login 

> ~/.profile 

> ~/.bashrc

### 具体实践，以修改/etc/profile为例

> PYTHON_HOME=/Users/web/Library/Python/2.7/bin

> PATH=$PYTHON_HOME:$PATH:

> source /etc/profile
