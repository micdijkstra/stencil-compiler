# Stencil Compiler

## The short version
+ Download and `cd` into the repo.
+ Run compiler tasks with `$ grunt`.
+ Write Sass in `sass`.
+ Write CoffeeScript and Javascript in `scripts`.
+ Copy JavaScript and CSS modules/plugins into `vendor`.
+ Manage and edit your site files in `assets`, `templates` and `includes`.
+ Your files and assets are compiled to `_site`.
+ Commit, then deploy to GitHub pages with `$ grunt deploy`.

## Table of Contents

+ [Getting Started](#getting-started)
+ [Deployment](#deployment)
+ [Liquid HTML](#liquid-html)
+ [Sass and CSS](#sass-and-css)
	+ [Sass compiler](#sass-compiler)
+ [CoffeeScript and Javascript](#coffeescript-and-javascript)
	+ [CoffeeScript compiler](#coffeescript-compiler)
	+ [Javascript plugins](#javascript-plugins)

## Getting started
+ Install NPM:  
`$ curl https://www.npmjs.org/install.sh | sh `
+ Install Grunt:  
`$ npm install -g grunt-cli`
+ Install NPM packages:  
`$ npm install`
+ Run Grunt  
`$ grunt`

Grunt will automatically open your default browser to [http://localhost:8000](http://localhost:8000) and is configured for automatic live reload.

## Deployment

Stencil is configured to compile files and copy assets to the `_site` folder. You just need to copy this folder to a server.

### GitHub Pages

Stencil includes a deployment script to automate deployment to GitHub pages. When you’re ready, you can deploy by running the following task:

```
$ grunt deploy
```

This will push your `_site` folder to a `gh-pages` branch at `origin`.

## Liquid HTML

Stencil uses the [Liquid Templating language](http://liquidmarkup.org/) to help you generate static sites while reusing blocks of code. 

### Templates

Templates, or pages, are stored in the `templates` folder and should be saved as `.liquid` files.

### Includes

Includes, or snippets, are stored in the `includes` folder and should be saved as `.liquid` files.

#### Example

The file `includes/head.liquid` can be included with the following syntax:

```liquid
{% include head %}
```

## Sass

### Sass Compiler

The main Sass file is `sass/application.sass` which will be compiled and combined with all the CSS files found in `vendor` and saved as `assets/application.css`. The file will then be minified and saved as `assets/application.min.css`. The `vendor` files will be added to the start of the compiled file.

####  Third party CSS

1. Copy CSS file into `vendor`.

That’s it! It will be automatically appended to your `application.css` and `appliction.min.css` files.

## CoffeeScript and JavaScript

### CoffeeScript compiler

CoffeeScript and JavaScript files found in will be converted to JavaScript and combined with all the Javascript files found in `vendor`, minified and saved as `assets/application.min.js`. The `vendor` files will be compiled first, then sub folders within `scripts` and finally root files within `scripts`.

####  Javascript plugins

1. Copy the plugin into `vendor`
2. Initialize your plugin in a custom script file in `scripts`
