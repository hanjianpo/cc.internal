# visual code
```
visual code可以很方便的编辑markdown，并能实时预览。
推荐安装markdown pdf插件，可将单个文档输出pdf/png/jpeg/html等格式。
```

# sublime text + gitbook
```
sublime text等文本编辑器，均可以方便的编辑markdown文档。
gitbook可以方便的将所有markdown源文件转换成网页，便于快速编译部署，且UI风格清爽优美。
```

## gitbook 安装
### macbook 安装
> $ brew install node

> $ npm install gitbook-cli -g

### ubuntu 安装
> $ sudo apt-get install -y nodejs

> $ npm install gitbook-cli -g

### centos 安装
> $ sudo yum -y install nodejs

> $ npm install gitbook-cli -g

## gitbook 使用
> cd /..../ai-whitebooks

> gitbook init // 可不执行此命令，因为summary.md已经存在

> gitbook build

![gitbookbuild](pics/gitbook_build.png)

> gitbook serve

![gitbookserve](pics/gitbook_serve.png)

## 浏览器访问
> 浏览器访问 http://localhost:4000/ ，即可在浏览器查看内容展示

