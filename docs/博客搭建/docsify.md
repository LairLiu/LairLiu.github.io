# 使用docsify搭建文档类博客系统

[TOC]

## 1 介绍
[docsify](https://docsify.js.org/#/zh-cn/) 是一个动态生成文档网站的工具，
相对于其他博客系统来说:

+ docsify不会将`.md`文件转换为`.html`文件，更直观
+ 默认只有一个`index.html`文件，每次都是提交新的`.md`文件，不会污染`git commit`记录
+ 只要初始化后马上就可以部署，结合GitHub Pages相当便捷

## 2 快速开始

关于手动初始化的方法建议直接查看官方的介绍，此处不多做说明。[手动初始化]([https://docsify.js.org/#/zh-cn/quickstart?id=%e6%89%8b%e5%8a%a8%e5%88%9d%e5%a7%8b%e5%8c%96](https://docsify.js.org/#/zh-cn/quickstart?id=手动初始化))

### 2.1安装

使用`npm`进行全局安装，需要确保本地安装了`node`

```powershell
npm install -g docsify -D
```

使用`docsify -v`确认安装成功

```powershell
docsify -v
>	docsify-cli version:
   		4.4.1
```

### 2.2 项目初始化

```powershell
## 创建一个存放项目的目录
mkdir docsify_demo ; cd docsify_demo
## 初始化项目
docsify init ./
```

初始化完成后可以看到文件夹中新增了文件

```markdown
.
├── .nojekyll		## 用于阻止github Pages 忽略下划线开头的文件
├── index.html		## 入口文件，相关的配置也在这里书写
└── README.md		会作为主页进行渲染
```

### 2.3 开始预览

通过运行`docsify serve` 启动一个本地服务器，可以方便地实时预览效果。

```powershell
docsify serve docs
> Listening at http://localhost:3000
```

到此，一个简单的框架就搭建起来了，下面就可以进行配置和写文档了。

## 3 配置

docsify 的配置都在index.html中

> 常用的一些配置

```html
<script>
    window.$docsify = {
      name: 'LairLiu',
      repo: 'https://github.com/LairLiu/LairLiu.github.io',
      maxLevel: 4,
      subMaxLevel: 3,
      homepage: 'README.md',
      loadSidebar: true,  //侧边栏
      loadNavbar: true,   //导航栏
      coverpage: false,    //封面
      auto2top: true,
      search: {
        maxAge: 86400000, //过期时间，默认一天
        paths: 'auto',
        placeholder: '搜索',
        noData: '没有找到结果',
        depth: 6  //搜索标题的最大层级
      },
      // 复制代码
      copyCode: {
        buttonText: {
          '/zh-cn/': '点击复制',
          '/': '点击复制'
        },
        errorText: {
          '/zh-cn/': '错误',
          '/': '错误'
        },
        successText: {
          '/zh-cn/': '复制',
          '/': '复制'
        },
        // 字数统计
        count: {
          countable: true,
          fontsize: '0.9em',
          color: 'rgb(90,90,90)',
          language: 'chinese'
        },
        //  在github上编辑该页面
        plugins: [
          EditOnGithubPlugin.create('https://github.com/LairLiu//master/')
        ]
      },
    }
</script>

<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<!-- 全局搜索 -->
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
<!-- 复制代码到剪贴板 -->
<script src="//unpkg.com/docsify-copy-code"></script>
<!-- 图片缩放 -->
<script src="//unpkg.com/docsify/lib/plugins/zoom-image.js"></script>
<!-- 字数统计 -->
<script src="//unpkg.com/docsify-count/dist/countable.js"></script>
<!-- 在github中编辑 -->
<script src="//unpkg.com/docsify-edit-on-github/index.js"></script>
```

将上述加上之后的目录结构

```markdown
├─ docs				//用于存放文档
├─ _coverpage.md	//首页
├─ _navbar.md		//导航栏
├─ _sidebar.md		//侧边栏
├─ .nojekyll
├─ index.html
├─ README.md		//主页
```

## 4 部署

### 4.1.1 新建仓库

### 4.1.2 提交项目

### 4.1.3 设置 github pages 功能

+ step1 在项目目录`setting`=>`Options`=>`GitHub Pages`=>`Source`选择`README.md`文件所在的路径
+ step2 选择完成后页面会刷新，在`source`的上方会有一个地址，那个地址就是我们当前项目可以访问的项目

## 总结

任何系统都只是一个工具，关键还是自己能有内容可以输出。







