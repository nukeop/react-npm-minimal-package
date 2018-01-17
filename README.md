# react-npm-minimal-package

Absolutely minimal boilerplate package.Includes ONLY what is necessary to start developing simple React components with the intention to publish them on NPM later.

There are many such packages on NPM and Github, but almost always they include way too many unnecessary dependencies, bloating your projects and introducing complexity a sane person cannot be expected to manage. Here I strived to create an absolutely minimal skeleton, containing no unnecessary cruft whatsoever. This enables you to create React components with simple demo pages to showcase them that can be later easily hosted using Github pages or other static hosting providers.

The only potentially superfluous element are the packages handling SASS to CSS conversion. They are easy to remove should you find them unneeded.

## What does it include?
All included packages, one by one, with rationale behind their inclusion:

| Package                  | What is it?                                                                                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ava                      | Simple test runner for unit-testing your code                                                                                                                                                                                                                                                                                                                                                                                   |
| babel-*                  | Babel transpiler to transform JSX into regular javascript. Presets and webpack loader included.                                                                                                                                                                                                                                                                                                                                 |
| css-loader, style-loader | Webpack loaders for css. Most React components will want to use custom stylesheets. If you're creating a non-visual component, feel free to remove this and adjust webpack config accordingly.                                                                                                                                                                                                                                  |
| node-sass, sass-loader   | SASS is a popular alternative to pure css. I include it in virtually all of my projects. Feel free to remove these if you don't need them.                                                                                                                                                                                                                                                                                      |
| react-hot-loader         | This package lets you "hot reload" your component's demo page when you're developing it, which means it applies your changes as you save them, without reloading the page manually. It is now an essential part of React development as it's way faster than building the project manually every time you change something.                                                                                                     |
| webpack                  | The simplest way to create a single script to be included in the demo page. The included production config will bundle your component and a simple demo script to create a website consisting of only two files which can be then statically hosted. The development config will facilitate developing your component, and the publishing config will take care of bundling everything into a file that can be exported to NPM. |
| webpack-dev-server       | Allows you to easily serve your demo page from a local server, using the "hot reload" mechanism (see above). `npm run dev` will start it with a simple configuration that has everything you need to get to developing your component.                                                                                                                                                                                          |


- webpack
  - 
  
## Development
Develop your component in ./src. This directory contains index.js which should be used to define what you want to export in your package.

To run a development version of your demo (with hot reload), run `npm run dev`, then open `localhost:8080` in your browser.

## Creating a demo
./demo contains a very basic html page and a script that will by default include your component without passing in any props. Modify them to your tastes and run `npm run demo` to generate the script bundle. 

Afterwards, if you want to use Github pages for hosting, you'll need to move index.html and bundle.js to a new branch called gh-pages.

## Publishing
Change the `package.json` file and update it with your package's name, keywords, author, repository link and so on. Then run `npm publish`. The prepublish script will build a ready to be published development version of your package and upload it to NPM.
