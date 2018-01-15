# react-npm-minimal-package

Absolutely minimal boilerplate package.Includes ONLY what is necessary to start developing simple React components with the intention to publish them on NPM later.

There are many such packages on NPM and Github, but almost always they include way too many unnecessary dependencies, bloating your projects and introducing complexity a sane person cannot be expected to manage. Here I strived to create an absolutely minimal skeleton, containing no unnecessary cruft whatsoever. This enables you to create React components with simple demo pages to showcase them that can be later easily hosted using Github pages or other static hosting providers.

The only potentially superfluous element are the packages handling SASS to CSS conversion. They are easy to remove should you find them unneeded.

## What does it include?
All included packages, one by one, with rationale behind their inclusion:

- ava
  - Simple test runner for unit-testing your code
  
- babel-*
  - Babel transpiler to transform JSX into regular javascript. Presets and webpack loader included.
  
- css-loader, style-loader
  - Webpack loaders for css. Most React components will want to use custom stylesheets. If you're creating a non-visual component, feel free to remove this and adjust webpack config accordingly.
  
- node-sass, sass-loader
  - SASS is a popular alternative to pure css. I include it in virtually all of my projects. Feel free to remove these if you don't need them.
  
- webpack
  - The simplest way to create a single script to be included in the demo page. The included config will bundle your component and a simple demo script to create a website consisting of only two files which can be then statically hosted.
  
## Development
Develop your component in ./src. This directory contains index.js which should be used to define what you want to export in your package.

## Creating a demo
./demo contains a very basic html page and a script that will by default include your component without passing in any props. Modify them to your tastes and run `npm run demo` to generate the script bundle. 

Afterwards, if you want to use Github pages for hosting, you'll need to move index.html and bundle.js to a new branch called gh-pages.

## Publishing
To be added.
