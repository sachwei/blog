### 准备
``` bash
- nodejs
- git

$ npm install -g hexo-cli
```

### 创建
``` bash
hexo init projectName
cd projectName
npm install
```

<!-- more -->

### 运行
运行即可查看效果
```
hexo server
```

### 命令
命令|描述
-|-
-d, --deploy|文件生成后立即部署网站
-w, --watch|监视文件变动
-p, --port|重设端口
-s, --static|只使用静态文件
-l, --log|启动日记记录，使用覆盖记录格式
-g, --generate|生成静态文件
-n, --new layout title|创建博客

### 部署
1. 注册github，新建'账户名'+'.github.io'的仓库
2. 在项目_config.yml中配置git信息,如下：
``` bash
deploy:
  type: git
  repo: https://github.com/yourname/yourname.github.io
  branch: master
```

### 发布
通过下面命令编译发布，同时有个小技巧，可以在package.json中配置快捷命令。
```
hexo clean
hexo g
hexo d

或

npm run publish

提前配置：
"scripts": {
  "publish": "hexo clean && hexo g && hexo d"
}
```