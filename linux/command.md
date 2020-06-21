
### mac系统的环境变量
> 加载顺序为

> /etc/profile 

> /etc/paths 

> ~/.bash_profile 

> ~/.bash_login 

> ~/.profile 

> ~/.bashrc

> 具体实践，以修改/etc/profile为例

> PYTHON_HOME=/Users/web/Library/Python/2.7/bin

> PATH=$PYTHON_HOME:$PATH:

> source /etc/profile
