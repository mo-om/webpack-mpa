[![GitHub stars](https://img.shields.io/github/stars/scriptex/webpack-mpa.svg?style=social&label=Stars)](https://github.com/scriptex/webpack-mpa)
[![GitHub forks](https://img.shields.io/github/forks/scriptex/webpack-mpa.svg?style=social&label=Fork)](https://github.com/scriptex/webpack-mpa/network#fork-destination-box)
[![GitHub release](https://img.shields.io/github/release/scriptex/webpack-mpa.svg)](https://github.com/scriptex/webpack-mpa/releases/latest)
[![GitHub issues](https://img.shields.io/github/issues/scriptex/webpack-mpa.svg)](https://github.com/scriptex/webpack-mpa/issues)
[![GitHub last commit](https://img.shields.io/github/last-commit/scriptex/webpack-mpa.svg)](https://github.com/scriptex/webpack-mpa/commits/master)
[![npm](https://img.shields.io/npm/dt/webpack-mpa-next.svg)](https://www.npmjs.com/package/webpack-mpa)
[![npm](https://img.shields.io/npm/v/webpack-mpa-next.svg)](https://www.npmjs.com/package/webpack-mpa)
[![license](https://img.shields.io/github/license/scriptex/webpack-mpa.svg)](https://github.com/scriptex/webpack-mpa)
[![Analytics](https://ga-beacon.appspot.com/UA-83446952-1/github.com/scriptex/webpack-mpa/README.md)](https://github.com/scriptex/webpack-mpa/)
[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/scriptex/webpack-mpa/)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/scriptex/webpack-mpa/webpack.config.js/graphs/commit-activity)

[![ForTheBadge built-with-love](http://ForTheBadge.com/images/badges/built-with-love.svg)](https://github.com/scriptex/)

# Webpack-MPA-Next

Opinionated multiple page application setup with Webpack using SASS, PostCSS, ES2017, PNG & SVG Sprites and more.

This boilerplate is suitable for static web applications, WordPress websites, etc.

## Dependencies

In order to use this setup you need to have installed the following dependencies:

1.  Node - min v8.9.4
2.  NPM - min v5.6.0
    or
3.  Yarn - min v1.3.2
4.  Bash terminal (Default on OSX/Linux, GitBash or similar on Windows)

## Default setup

The default setup uses PHP files, but you can easily switch to a file format of your choice.

Also, you can always switch to another file/folder structure if the current one does not suit you.

Just keep in mind that the styles should be located in `assets/styles` and the scripts should be located in `assets/scripts`.

## Download

You can download this setup [directly](https://github.com/scriptex/webpack-mpa/archive/postcss.zip) and extract it.

or use NPM or Yarn to install it:

```
npm i webpack-mpa-next
```

or

```
yarn add webpack-mpa-next
```

Then navigate to the `webpack-mpa-next` folder and proceed with the rest of the instructions.

## Install dependencies

```
yarn
```

or

```
npm i
```

## Develop

```
yarn start
```

or

```
npm start
```

## Build

```
yarn build
```

or

```
npm run build
```

## Details

1.  [PostCSS](http://postcss.org/) stylesheets pre and postprocessing

    *   The CSS file/folder structure utilizes the ITCSS pattern as shown and explained [here](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)
    *   Glob import in CSS thanks to [postcss-easy-import](https://github.com/TrySound/postcss-easy-import)
    *   [url rebase](https://github.com/postcss/postcss-url) - locates and copies assets from `node_modules`
    *   [postcss-utilities](https://github.com/ismamz/postcss-utilities) - allows usage of utility mixins such as `clearfix`
    *   [flexbox bugs](https://github.com/luisrudge/postcss-flexbugs-fixes) - fixes common flexbox issues on Internet Explorer
    *   [css minification](http://cssnano.co/) - minifies the bundles stylesheet
    *   [automatic vendor prefixes](https://github.com/postcss/autoprefixer)

        > "Write your CSS rules without vendor prefixes (in fact, forget about them entirely)"

    *   [postcss cssnext](http://cssnext.io/) - use tomorrow's CSS syntax, today
    *   [postcss nested](https://github.com/postcss/postcss-nested) - use SASS like nesting in CSS
    *   [postcss mixins](https://github.com/postcss/postcss-mixins) - PostCSS plugin for mixins
    *   [rules merging](https://github.com/ben-eb/postcss-merge-rules)

2.  PNG Sprite generating using [Webpack SpriteSmith](https://github.com/mixtur/webpack-spritesmith)
    The default setup includes retina sprite support which means that you should provide a retina version of each png icon.

    If you do not wish to use the retina sprite, comment the `@include retina-sprites($retina-groups);` statement in `main.scss` file.

3.  Latest EcmaScript support

    *   Usage of the latest features in EcmaScript
    *   Using [Babel](https://github.com/babel/babel) to transpile to ES5
    *   Minification of the bundled file
    *   Source maps

4.  Automatic browser reload using [BrowserSync](https://browsersync.io/)

    *   The setup assumes that you have a web server installed. If you do not, then the files will be served via the browser-sync built-in server.
    *   If you wish to use a proxy in browsersync you can do it using the `url` CLI argument like this:

    ```
    yarn start --env.url=http://your.app
    ```

    or

    ```
    npm start -- --env.url=http://your.app
    ```

5.  Images optimization using [Imagemin](https://github.com/Klathmon/imagemin-webpack-plugin)

6.  SVG Sprite generating using [spritesh](https://www.npmjs.com/package/spritesh)

    All svg files located in `assets/images/svg` are merged into a single `sprite.svg` file in `dist` directory.

    This action is performed each time the `start` command is invoked.

7.  All front-end assets are stored in an auto-generated `dist` folder.

## Assets

The `assets` folder contains several folders:

*   `images` - contains several folders too:
    *   `favicon` - holds all favicon variations
    *   `sprite` - holds png sprite's parts
    *   `svg` - holds svg sprite's parts
    *   `temp` - holds content images
*   `scripts` - contains the JS modules
*   `styles` - contains the SASS stylesheets

**Each `start` command regenerates the contents of the `dist` folder.**

## Supported Browsers

This setup uses [Browserslist](https://github.com/browserslist/browserslist) to target browsers.

The default list of supported browsers is listed in the `package.json` file:

```
"browserslist": ["> 1%", "last 2 versions"]
```

This means that supported browsers vary based on current usage data and current browser versions.

In general, this setup supports the two most recent versions of all browsers.

## LICENSE

MIT
