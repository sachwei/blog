### 简介

> 一个神奇的文档网站生成工具
>
> docsify 是一个动态生成文档网站的工具。不同于 GitBook、Hexo 的地方是它不会将 `.md` 转成 `.html` 文件，所有转换工作都是在运行时进行。这将非常实用，如果只是需要快速的搭建一个小型的文档网站，或者不想因为生成的一堆 `.html` 文件“污染” commit 记录，只需要创建一个 `index.html` 就可以开始写文档而且直接部署在[GitHub Pages](https://links.jianshu.com/go?to=https%3A%2F%2Fdocsify.js.org%2F%23%2Fzh-cn%2Fdeploy)。

### 特性

- 无需构建，写完文档直接发布
- 容易使用并且轻量 (~19kB gzipped)
- 智能的全文搜索
- 提供多套主题
- 丰富的 API
- 支持 Emoji
- 兼容 IE10+
- 支持 SSR ([example](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2Fdocsifyjs%2Fdocsify-ssr-demo))

### 快速安装

```bash
npm i docsify-cli -g
```

### 初始化

```
docsify init ./docs
```

初始化成功后，可以看到 `./docs` 目录下创建的几个文件

`index.html` 入口文件

`README.md` 会做为主页内容渲染

`.nojekyll` 用于阻止 GitHub Pages 会忽略掉下划线开头的文件

直接编辑 `docs/README.md` 就能更新网站内容，当然也可以写多个页面。



### 运行

运行一个本地服务器，通过 `docsify serve` 可以方便的预览效果，而且提供 LiveReload 功能，可以实时的预览。默认通过 [http://localhost:3000](https://links.jianshu.com/go?to=http%3A%2F%2Flocalhost%3A3000)访问。

```
docsify serve docs
```

