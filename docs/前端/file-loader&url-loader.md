---
title: file-loader 和 url-loader 的区别
date: :year/:month/:day/
tags:
    - webpack
---

<!-- ## file-loader 和 url-loader 的区别 -->

#### [file-loader](https://www.webpackjs.com/loaders/file-loader/)

```javascript
module.exports = {
  // ...
  output:{
    path: path.join(__dirname, '/dist/')
  },
  // ...
  module:{
    rules:[{
      test: /\.(png|svg|jpg|gif)$/,
        use: [{
          loader: "file-loader",
          options: { name: '[name].[ext]?[hash]', outputPath: 'images/' }
        }]
    }]
  }
}
```

打包执行后，`file-loader`会将`css文件、html、js...`中使用的图片抽离打包到`/dist/images/`中


#### [url-loader](https://www.webpackjs.com/loaders/url-loader/)

```javascript
// webpack.config.js
module.exports = {
  // ...
  rules:{
    test: /\.(png|svg|jpg|jpeg|gif)$/,
    use: [{
        loader: "url-loader",
        options: {
        name: '[name].[ext]?[hash]',
        outputPath: 'images/',
        limit: 10240
      }
    }]
  }
}
```
使用`url-loader`的时候要安装`file-loader`插件
打包执行后会将`10240b(10kb)`大小的图片转换为base64进行使用，其他配置会往下传给`file-loader`进行处理