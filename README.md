# Kids Voice

Site:  [http://kidsvoice.netlify.com](http://kidsvoice.netlify.com)

Admin:  [http://kidsvoice.netlify.com/admin](http://kidsvoice.netlify.com/admin)

This project uses 
*  Hugo static site generator
*  Netlify CMS for content administration
*  post-css and babel for CSS and JavaScript

## Usage

Be sure that you have git, the latest node, npm and Hugo installed. 

[Hugo Install Docs](https://hugodocs.info/getting-started/installing/)

[Windows specifically]( https://hugodocs.info/getting-started/installing/#i-class-icon-windows-i-windows)

Next, clone this repository and run:

```bash
npm install
npm start
```

Then visit http://localhost:3000/ - BrowserSync will automatically reload CSS or
refresh the page when stylesheets or content changes.

To build your static output to the `/dist` folder, use:

```bash
npm run build
```

## Structure

```
|--site                // Everything in here will be built with hugo
|  |--content          // Pages and collections - ask if you need extra pages
|  |--data             // YAML data files with any data for use in examples
|  |--layouts          // This is where all templates go
|  |  |--partials      // This is where includes live
|  |  |--index.html    // The index page
|  |--static           // Files in here ends up in the public folder
|--src                 // Files that will pass through the asset pipeline
|  |--css              // CSS files in the root of this folder will end up in /css/...
|  |--js               // app.js will be compiled to /app.js with babel
```

## Basic Concepts

You can read more about Hugo's template language in their documentation here:

https://hugodocs.info/templates/introduction/#introduction-to-go-templates

For assets that are completely static and don't need to go through the asset pipeline,
use the `site/static` folder. Images, font-files, etc, all go there.

Files in the static folder ends up in the web root. So a file called `site/static/favicon.ico`
will end up being available as `/favicon.ico` and so on...

The `src/js/app.js` file is the entry point for webpack and will be built to `/dist/app.js`.

You can use ES6 and use both relative imports or import libraries from npm.

Any CSS file directly under the `src/css/` folder will get compiled with [PostCSS Next](http://cssnext.io/)
to `/dist/css/{filename}.css`. Import statements will be resolved as part of the build

