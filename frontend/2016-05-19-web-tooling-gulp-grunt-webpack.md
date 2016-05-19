# Web Tooling
--- 

Source: http://survivejs.com/webpack_react/webpack_compared/

> Historically speaking, there have been many build systems. Make is perhaps the best known, and is still a viable option. To make things easier, specialized task runners, such as Grunt and Gulp appeared. Plugins available through npm made both task runners powerful.

> Task runners are great tools on a high level. They allow you to perform operations in a cross-platform manner. The problems begin when you need to splice various assets together and produce bundles. This is the reason we have bundlers, such as Browserify or Webpack.

> Continuing further on this path, JSPM pushes package management directly to the browser. It relies on System.js, a dynamic module loader. Unlike Browserify and Webpack, it skips the bundling step altogether during development. You can generate a production bundle using it, however. Glen Maddern goes into good detail at his video about JSPM.

Source: http://jamesknelson.com/which-build-system-should-i-use-for-my-javascript-app/ 

> **The Short Answer**

> It is easy to decide which tools you need:

> - Small projects can get away with just an ES6 compiler
> - Single Page Apps need a module bundler too
> - Once your app is in production, use a task runner to automate anything else

> And here are the packages which fulfil these requirements:

> - For compiling and polyfilling ES6, use Babel
> - For bundling your JavaScript files and dependencies into static assets, use Webpack
> - If your have other tasks like renaming files to avoid caching or publishing to the web, automate them with Gulp

## Building System

- [Make](https://en.wikipedia.org/wiki/Make_%28software%29)

### Task Runners

- [Grunt](http://gruntjs.com/) 
- [Gulp](http://gulpjs.com/)

### Compiler

- [Babel](https://babeljs.io/)

### Bundlers

- [Browserify](http://browserify.org/)
- [Webpack](https://webpack.github.io/)


---

## Reference

- [Webpack Compared](http://survivejs.com/webpack_react/webpack_compared/)
- [James K Nelson: Choosing a JavaScript Build Tool – Babel, Browserify, Webpack, Grunt and Gulp](http://jamesknelson.com/which-build-system-should-i-use-for-my-javascript-app/)
- [NPMCompare: Comparing browserify vs. grunt vs. gulp vs. webpack](https://npmcompare.com/compare/browserify,grunt,gulp,webpack)
- [gulp vs. Grunt vs. Webpack](http://stackshare.io/stackups/gulp-vs-grunt-vs-webpack)
- [StackOverflow: npm vs bower vs browserify vs gulp vs grunt vs webpack](http://stackoverflow.com/questions/35062852/npm-vs-bower-vs-browserify-vs-gulp-vs-grunt-vs-webpack)
