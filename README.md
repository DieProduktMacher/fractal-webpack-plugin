# fractal-webpack-plugin
Fractal Webpack Plugin.

Read a `fractal.js` file if placed in the root of the project. See https://fractal.build/guide/project-settings

## Installation

```
npm install fractal-webpack-plugin --save
```


## Usage

Example `webpack.config`

```javascript
const FractalWebpackPlugin = require('fractal-webpack-plugin');

module.exports = {
    entry: {
        app: path.resolve('./src/assets/js/app.js'),
    },
    output: {
        path: path.resolve('./public/js/'),
        filename: '[name].js',
    },
    module: {
        rules: [
            {
                test: /\.js$/,
                use: ['babel-loader'],
            },
        ],
    },
    plugins: [
      new FractalWebpackPlugin({
        mode: 'server', // mode: 'build'
        sync: true,
      })
    ]
};
```

## Options

#### mode

Type: `string` <br>
Default: `server`

Boot up a server or build a static page. Available modes: `server` and `build`

#### sync

Type: `boolean` <br>
Default: `true`

To use browsersync or not

