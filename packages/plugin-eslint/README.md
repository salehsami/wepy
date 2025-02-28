# wepy eslint 插件
# wepy eslint plugin

## 安装
## Install

```bash
npm install @wepy/plugin-eslint --save-dev
```

## 配置`wepy.config.js`

```javascript
const eslint = require('@wepy/plugin-eslint');

module.exports = {
  plugins: [
    eslint({
      // options
    })
  ]
};
```

## 参数说明

## Parameter Description

你提供的配置选项 ```options``` 将传递给 ```CLIEngine```处理，有关 ```options``` 的更多详细信息，请参阅[eslint文档](https://eslint.org/docs/developer-guide/nodejs-api#cliengine)。

The configuration options you provide ```options``` will be passed to ```CLIEngine``` for processing, for more details about ```options```, please refer to the [eslint documentation](https://eslint .org/docs/developer-guide/nodejs-api#cliengine).

#### quiet (default: ```false```)

#### quiet (默认值: ```false```)

如果此选项设置为true，插件将仅处理和报告错误，忽略警告
If this option is set to true, the plugin will only process and report errors, ignoring warnings

```javascript
const eslint = require('@wepy/plugin-eslint');

module.exports = {
  plugins: [
    eslint({
      quiet: true
    })
  ]
};
```
#### fix (default: ```false```)

启用 ```ESLint``` 自动修复功能

注意：此选项将更改源文件

#### output (default: ```true```)

启用 ```ESLint```
Enable ```ESLint```


#### eslintPath (default: ```eslint```)

用于 ```linting``` 的 ```ESLint``` 实例的路径
Path to ```ESLint``` instance to use for ```linting```


#### formatter (default: eslint stylish formatter)

用于格式化 ```ESLint``` 输出，选项值接收字符串或者函数
Used to format ```ESLint``` output, option values ​​accept strings or functions


```javascript
const eslint = require('@wepy/plugin-eslint');

module.exports = {
  plugins: [
    eslint({
      // default value
      formatter: require('eslint/lib/formatters/stylish'),

      // community formatter
      formatter: require('eslint-friendly-formatter'),

      // custom formatter
      formatter: function(results) {
        // `results` format is available here
        // http://eslint.org/docs/developer-guide/nodejs-api.html#executeonfiles()

        // you should return a string
        // DO NOT USE console.*() directly !
        return 'OUTPUT'
      }
    })
  ]
};
```
