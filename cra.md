# create-react-app

## 本地自定义地址启动 

在 package.json 中修改启动脚本

```json
{
  "start": "HOST=local.elenet.me node scripts/start.js",
}
```

## 添加 less

```bash
npm i less less-loader -D
```

webpack.config.js 的 sass-loader 下添加以下代码

```js
// sass 正则下
const lessRegex = /\.less$/;
const lessModuleRegex = /\.module\.less$/;

// sass-loader 后
{
  test: lessRegex,
  exclude: lessModuleRegex,
  use: getStyleLoaders(
    {
      importLoaders: 2,
      sourceMap: isEnvProduction && shouldUseSourceMap,
    },
    'less-loader'
  ),
  sideEffects: true,
},
{
  test: lessModuleRegex,
  use: getStyleLoaders(
    {
      importLoaders: 2,
      sourceMap: isEnvProduction && shouldUseSourceMap,
      modules: true,
      // getLocalIdent: getCSSModuleLocalIdent,
    },
    'less-loader'
  )
},


```
