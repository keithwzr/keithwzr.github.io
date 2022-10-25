---
title: Springboot+vue前后端分离项目
comments: false
date: 2022-10-25 21:07:58
tags:
categories:
top_img:
cover:
---

# Spring+Vue前后端分离项目

## 环境配置

### node.js安装

[Node.js (nodejs.org)](https://nodejs.org/zh-cn/)在这里下载安装（建议14.0以上）

```
node -v
npm -v
#检查版本
```

#### 问题

1、node.js安装后，执行npm报错npm WARN config global --global, --local are deprecated. Use --location=global instead.

2、使用官网文档命令安装vue-cli：`npm install -g @vue/cli`，过程中卡住，很慢

#### 解决方法

问题一：

1、打开node.js安装目录那里，找到npm.cmd文件
2、打开编辑：直接点编辑或者把后缀改为.txt记事本文件，内容修改后再改回来也许
3、将文件里的 prefix-g 改为 prefix --location=global
4、点击保存就解决了
注意，文件保存时可能因为权限问题改不了
可以点文件右键----属性----安全------保险起见全部用户设置为完全可控
5、控制台尝试一下输入，没有npm报错，说明解决了；

问题二：

（1）安装vue-cli之前确认是否安装nodejs
（2）关闭防火墙等软件，避免拦截和无法使用npm安装包
（3）去下载一个cnpm （注释：淘宝npm镜像，这个是阿里把外国的npm服务器搬到我们中国来了，用淘宝镜像npm下载一些配置文件会更快一些）
cmd 右键复制下行命令：

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

## 创建工程

### create

在cmd中创建

```
vue create springboot-vue-demo
```

回车后进行配置



![create1](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\create1.PNG)

![create2](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\create2.PNG)

版本选择3.x![create3](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\create3.PNG)

无脑选y

![create4](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\create4.PNG)

选择package.json

之后会问是否保存配置，随意即可。

### 在idea使用

将springboot-vue-demo拖入idea运行

在文件\设置中安装插件![idea1](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\idea1.PNG)

在运行\编辑配置中设置npm，即可在运行时启动vue

![idea2](D:\GitHub\keithwzr.github.io\source\_posts\Springboot-vue前后端分离项目\idea2.PNG)

## 工程文件介绍

### public

vue 文件经过编译后会在index.html 中显示

### src

主要的核心代码

#### assets

静态资源，包括图片以及.css.js等

#### components

放组件的地方

#### router

写路由的地方（路由：路径和文件之间写的映射，通过路径访问文件）

#### store

定义页面的一些变量，如页面跳转时要携带一些变量，或是用户登录后需要显示用户名，可以存在这里

#### views

视图的存放位置

在Home.vue中引用了HelloWorld.vue组件（将代码通过组件的方式打包）

#### package.json

项目所依赖的组件
