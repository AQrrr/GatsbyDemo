
<h1 align="left">
  Build a starter Portfolio with Gatby&Netlify
</h1>

<p align="left">
  English | [简体中文](/readmeCN.md)
</p>

Playful and Colorful One-Page portfolio featuring Parallax effects and animations. Using Cara's Gatsby Theme [`@lekoarts/gatsby-theme-cara`](https://github.com/LekoArts/gatsby-themes/tree/master/themes/gatsby-theme-cara) she is the origin author.


## ✨ Features

- Theme UI-based theming
- react-spring parallax effect
- CSS Animations on Shapes

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



## 📝 Using and modifying this starter

**Important Note:** Please read the guide [Shadowing in Gatsby Themes](https://www.gatsbyjs.org/docs/themes/shadowing/) to understand how to customize the underlying theme!

This starter creates a new Gatsby site that installs and configures the theme [`@lekoarts/gatsby-theme-cara`](https://github.com/LekoArts/gatsby-themes/tree/master/themes/gatsby-theme-cara).


### Changing content

The content of this project is defined in four `.mdx` files inside the theme's `sections` folder. You can override the files `intro.mdx`, `projects.mdx`, `about.mdx` and `contact.mdx`. This starter has overriden the `intro.mdx` file as an example. Place the other files in the same `src/@lekoarts/gatsby-theme-cara/sections/` folder.

You have to use the `<ProjectCard />` component inside `projects.mdx` to display the cards. Example:

```md
### Change your `static` folder

The `static` folder contains the icons, social media images and robots.txt. Don't forget to change these files, too!


