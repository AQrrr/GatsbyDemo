<h1 align="left">
  用Gatby和Netlify创建网站
</h1>
[![Netlify Status](https://api.netlify.com/api/v1/badges/2b91ae69-eff5-4d85-bf87-a37b81236fde/deploy-status)](https://app.netlify.com/sites/inspiring-demo/deploys)
[English](README.md) | [简体中文](readmeCN.md)

本教程使用gatsby官网提供的一页式网站模板，这里是原作者链接 [`@lekoarts/gatsby-theme-cara`](https://github.com/LekoArts/gatsby-themes/tree/master/themes/gatsby-theme-cara).  


大家也可以去Gatsby Starter Library里找自己喜欢的其他模板，之后复制模板中的命令创建文件就可以。

准备工作：
1. 在Gatsby和Netlify完成注册
2. 已经安装git
3. 很多很多耐心，以及善用Google 😂


本教程参考Netlify[官网指南](https://www.netlifycms.org/docs/gatsby/#get-to-know-gatsby)，有兴趣的同学可以去看原文。 



## 🚀 准备开始

1. **创建Gatsby站点**
请先去Gatsby官网完成注册，之后全局安装Gatsby 
```sh
npm install -g gatsby-cli
```
然后用Gatsby CLI创建新站点

```sh
gatsby new (你的文件夹名字) https://github.com/LekoArts/gatsby-starter-portfolio-cara
```
ps. 创建新站点这一步，示例中我选用的是gatsby-starter-portfolio-cara，大家可以换成自己喜欢的starter

2. **开始运行**

进入你的文件夹，开始运行

```sh
cd 你的文件夹名字

用npm
npm install // 安装依赖 要等好久……

或者用yarn
yarn // 安装依赖 要等好久……

最后
gatsby develop
```

3. **创建完毕**

可以打开浏览器查看你的网页啦 `http://localhost:8000`


4. **添加Netlify CMS**

安装依赖：
```sh
npm install --save netlify-cms-app gatsby-plugin-netlify-cms
```

##### 配置
我们需要从github仓库部署到Netlify，因此要做一些基本配置。

在static/admin文件夹里新建config.yml文件。 目录结构如下：
```sh
├── static
│   ├── admin
│   │   ├── config.yml
```

把以下代码粘贴到config.yml中：
```sh
backend:
  name: git-gateway
  branch: main

media_folder: static/img
public_folder: /img

collections:
  - name: 'blog'
    label: 'Blog'
    folder: 'content/blog'
    create: true
    slug: 'index'
    media_folder: ''
    public_folder: ''
    path: '{{title}}/index'
    editor:
      preview: false
    fields:
      - { label: 'Title', name: 'title', widget: 'string' }
      - { label: 'Publish Date', name: 'date', widget: 'datetime' }
      - { label: 'Description', name: 'description', widget: 'string' }
      - { label: 'Body', name: 'body', widget: 'markdown' }
```

在`gatsby-config.js`中，添加插件 <br/>

```sh
plugins: [`gatsby-plugin-netlify-cms`]
```
##### 本地文件上传到git仓库
```sh
git init
git add .
git commit -m "Initial Commit"
git remote add origin https://github.com/YOUR_USERNAME/NEW_REPO_NAME.git
git push -u origin main
```

**5. 部署到Netlify**

登录Netlify点击 'New Site from Git'. 

##### 开启 Identity 和 Git Gateway
开启后，你的网站主账户可以从Netlify管理后台，不需要反复从git进行修改。 

在Netlify的site dashboard中:

点击 **Settings > Identity**, 选择 Enable Identity service.
在 **Registration preferences**, 选择 Open 或者 Invite only.  
左侧**Services > Git Gateway**, 选择 **Enable Git Gateway**. 

##### 更新你的网站
登录你的网址 /admin/  点击 New Blog 发布新文章




