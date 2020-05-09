# Create Website in [Gatsby](https://www.gatsbyjs.org/) with [TailwindCSS](https://tailwindcss.com/)

### New project
```sh
$ npx gatsby new site_folder https://github.com/gatsbyjs/gatsby-starter-hello-world
```
### Create siteMetadata in a separate file
```js
// ./config/metadata.js

module.exports = {
  title: "Site Title",
  siteUrl: "https://site.url",
  description: "Site Description",
  social: [
    {
      name: "social network",
      url: "https://social-networtk,url",
    },
    ...
  ],
}
```
### Gatsby config (siteMetadata)
```js
// ./gatsby-config.js

const siteMetadata = require("./config/metadata")

module.exports = {
  siteMetadata,
  plugins: [
    ...
  ],
}
```
### Basic plugins
| Plugin | README |
| ------ | ------ |
| NProgress | [gatsby-plugin-nprogress](https://www.gatsbyjs.org/packages/gatsby-plugin-nprogress/?=nprogress#gatsby-plugin-nprogress) |
| Google Analytics | [gatsby-plugin-google-analytics](https://www.gatsbyjs.org/packages/gatsby-plugin-google-analytics/?=gatsby-plugin-google-analytics) |
| Prefetch Google Fonts | [gatsby-plugin-prefetch-google-fonts](https://www.gatsbyjs.org/packages/gatsby-plugin-prefetch-google-fonts/?=gatsby-plugin-prefetch-google-fonts) |
| React Helmet | [gatsby-plugin-react-helmet](https://www.gatsbyjs.org/packages/gatsby-plugin-react-helmet/?=gatsby-plugin-react-helmet) |
| Manifest | [gatsby-plugin-manifest](https://www.gatsbyjs.org/packages/gatsby-plugin-manifest/?=gatsby-plugin-manifest) |
| Canonical URLs | [gatsby-plugin-canonical-urls](https://www.gatsbyjs.org/packages/gatsby-plugin-canonical-urls/?=gatsby-plugin-canonical-urls) |
| Sitemap | [gatsby-plugin-sitemap](https://www.gatsbyjs.org/packages/gatsby-plugin-sitemap/?=gatsby-plugin-sitemap) |
| Styled Components `*` | [gatsby-plugin-styled-components](https://www.gatsbyjs.org/packages/gatsby-plugin-styled-components/?=gatsby-plugin-styled-components) |
| Page Creator `*` | [gatsby-plugin-page-creator](https://www.gatsbyjs.org/packages/gatsby-plugin-page-creator/?=gatsby-plugin-page-creator) |
| Transformer Sharp | [gatsby-transformer-sharp](https://www.gatsbyjs.org/packages/gatsby-transformer-sharp/?=transformer-sharp) |
| Offline | [gatsby-plugin-offline](https://www.gatsbyjs.org/packages/gatsby-plugin-offline/?=gatsby-plugin-offline) |
*`*`Install plugin when using `styles.js` in page folders*

### Add Tailwind CSS
```sh
$ yarn add tailwindcss

$ yarn add gatsby-plugin-postcss

$ yarn add gatsby-plugin-purgecss
```

### Gatsby config (postcss)
```js
  // ./gatsby-config.js
  ...
  plugins: [
    ...
    {
      resolve: `gatsby-plugin-postcss`,
      options: {
        postCssPlugins: [require(`tailwindcss`), require(`autoprefixer`)],
      },
    },
    {
      resolve: `gatsby-plugin-purgecss`,
      options: {
        printRejected: false,
        develop: false,
        tailwind: true,
      },
    },
    ...
  ]
  ...
```

### Add Tailwind to your CSS
```css
/* ./src/assets/styles/tailwind.css */

@tailwind base;

@tailwind components;

@tailwind utilities;
```
### Create your Tailwind config file (optional)
```sh
$ npx tailwindcss init
```
### Initialize Tailwind in the project
```js
// ./gatsby-browser.js

import "./src/assets/styles/tailwind.css"
```

By [Lucas Gomes](https://github.com/lucassbgomes)


>These tips were created from some videos: [Configurando projeto Gatsby | Behind the Code #09](https://www.youtube.com/watch?v=Z88SWjN6Yj0) made by [Diego Fernandes](https://github.com/diego3g) and João Pedro from the [Rocketseat](https://www.youtube.com/channel/UCSfwM5u0Kce6Cce8_S72olg) channel; and [Gatsby.js with Tailwind CSS and PurgeCSS](https://www.youtube.com/watch?v=d0v_ouu5mqU) from the [Code Bushi](https://www.youtube.com/channel/UCS6lPt9btmTG3GkU82ELygA) channel.
