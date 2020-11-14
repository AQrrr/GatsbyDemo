
<h1 align="left">
  Build a starter Portfolio with Gatby&Netlify
</h1>


 [English](README.md) | [简体中文](readmeCN.md)


Playful and Colorful One-Page portfolio featuring Parallax effects and animations. Using Cara's Gatsby Theme [`@lekoarts/gatsby-theme-cara`](https://github.com/LekoArts/gatsby-themes/tree/master/themes/gatsby-theme-cara) she is the origin author.


## ✨ Features

- Theme UI-based theming
- react-spring parallax effect
- CSS Animations on Shapes

## ✨ What You Will Need
1. Sign up at Gatsby&Netlify 
2. Installed Git
3. Patient and Google 😂

## 🚀 Getting Started

1. **Create a Gatsby site.**
Make sure you've installed Gatsby 
```sh
npm install -g gatsby-cli
```
Use the Gatsby CLI to create a new site

```sh
gatsby new project-name https://github.com/LekoArts/gatsby-starter-portfolio-cara
```

2. **Start developing.**

Navigate into your new site's directory and start it up.

```sh
cd your-project-name

with npm
npm install // to install all the dependencies needed

with yarn
yarn // to install all the dependencies needed

gatsby develop
```

3. **Open the code and start customizing!**

Your site is now running at `http://localhost:8000`!


4. **Add Netlify CMS to your site**

Log in Netlify

install dependencies:
```sh
npm install --save netlify-cms-app gatsby-plugin-netlify-cms
```

##### Configuration
We will deploy to Netlify from a GitHub repository which requires the minimum configuration.

Create a `config.yml` file in the directory structure you see below:
```sh
├── static
│   ├── admin
│   │   ├── config.yml
```

Paste the following configurationin `config.yml`:
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

Insert plugin in `gatsby-config.js` <br/>

```sh
plugins: [`gatsby-plugin-netlify-cms`]
```

##### Push to GitHub

```sh
git init
git add .
git commit -m "Initial Commit"
git remote add origin https://github.com/YOUR_USERNAME/NEW_REPO_NAME.git
git push -u origin main
```

##### Add your repo to Netlify

Go to Netlify, log in and select 'New Site from Git'. 

##### Enable Identity and Git Gateway
Netlify's Identity and Git Gateway services allow you to manage CMS admin users for your site without requiring them to have an account with your Git host or commit access on your repo. 

From your site dashboard on Netlify:

Go to **Settings > Identity**, and select Enable Identity service.
Under **Registration preferences**, select Open or Invite only.  
Scroll down to **Services > Git Gateway**, and click **Enable Git Gateway**. This authenticates with your Git host and generates an API access token. In this case, we're leaving the Roles field blank, which means any logged in user may access the CMS. 

##### Updating Your Website
Login to your site's /admin/ page and create a new post by clicking New Blog.




