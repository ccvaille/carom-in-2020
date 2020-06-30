### webpack 从 0 - 1
- webpack 是什么
  - module bundler 模块打包工具
- 命令执行
  - `npx webpack -v`
    - 查看当前目录的 webpack 版本
  - `npx webpack index.js`
    - 打包 index.js
  - `npm info webpack`
    - 查看当前 webpack 版本
- 使用方式
  - global 安装
    - webpack index.js
  - loacal 安装
    - npx webpack index.js
    - npm scripts 
      - npm run build -> webpack
- loader
  - file-loader
    - 文件加载器,将文件上的import / require（）解析为url，并将该文件发射到输出目录中
  - url-loader
    - 如果文件小于字节限制，则可以返回 DataURL，否则将文件转换成 base 64
    - name: '[name].[ext]?[hash]',
    - outputPath: 'images/',
    - limit: 1024
  - css-loader
    - 解析 css 文件里面的 import 语法
    - importLoaders
      - 在解析 CSS loader 之前还执行其他的 loader 个数
        - // 0 => no loaders (default);
        - // 1 => postcss-loader;
        - // 2 => postcss-loader, sass-loader
    - modules
      - true 模块化 css
        - import style from './bear.js'
        - img.classList.add(style.bear)
  - less-loader
    - 把 less 打包成 css
- plugins
- devtool
  - 分类
    - cheap
      - 只提示多少行出错，不提示多少列出错
      - 只处理业务代码出错，不处理 loader 的出错
    - module
      - 也处理 loader 出错
    - eval
      - 直接 eval 执行打包
    - inline
      - 映射代码打包在打包后的目标文件里面
    - source-map
      - 自动生成 .map 文件
  - 开发环境
    - cheap-module-eval-source-map
  - 生产环境
    - cheap-module-source-map
- 热更新方法
  - `webpack --watch`
  - webpack-dev-server
    - devServer
  - 自己写一个服务器
    - webpackDevMiddleware 可以监听到 webpack 的打包代码发生变化