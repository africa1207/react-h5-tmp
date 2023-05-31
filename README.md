<!--
 * @Descripttion: 项目描述文件
 * @version:
 * @Author: zhoukai
 * @Date: 2022-07-28 09:54:02
 * @LastEditors: zhoukai
 * @LastEditTime: 2023-05-31 23:54:27
-->

# 简介

react-h5-tmp 是基于 create-react-app(v5) 创建并使用 Ant Design Mobile + JavaScript + craco + Redux + sass + Rem 布局适配 + axios（封装）+ Eslint + Prettier 等流行技术栈构建移动端模板脚手架，开箱即用。

craco 是什么？
craco（一个对 create-react-app 进行自定义配置的社区解决方案） 对 create-react-app 的默认配置进行自定义设置。

## 环境要求

-   node 14+

## 编辑器以及对应扩展

-   Visual Studio 69+
-   Vetur v0.35.0
-   Eslint v2.2.6
-   Prettier - Code formatter v9.5.0

## 快速开发

```
#通过 npm 安装 pnpm (如果本地已安装pnpm,请忽略)
npm install -g pnpm
#安装项目依赖
pnpm install
#开发环境启动
pnpm start
#打包 test 环境代码
pnpm build:test
#打包生产环境代码
pnpm build or pnpm build:prod
#执行 js 类型检查
pnpm lint:fix
#执行 prettier 批量格式化代码
pnpm lint:prettier

##注：详细请阅读package.json 以及对应的环境配置文件（即.env 文件）！
```

```text
同时在项目根目录下包含一个 run.bat，该文件会列出所有 package.json 中 script 块里面的所有命令，
通过双击该文件，你可以在命令行中输入相应的序号并按 Enter 键，程序将运行你选择的脚本。
```

## 开发基础规范

<font  color="red">如果设计稿的尺寸不是 750，而是 375 或其他大小，请在 .postcssrc.js 中及时调整 rootValue。</font>

-   🚀 重要、复杂逻辑一定要写注释；
-   🚀 代码规范按照 eslint 的规则来，做到 no waring 和 no error；
-   🚀 预编译使用 sass；
-   🚀 操作成功或失败后要有提示，比如新增成功、新增失败运行时间长的任务（计算量大、请求后台接口），要有 loadding 效果；
-   🚀 公共的状态才放到 store；
-   🚀 代码尽量往纵向发展，一行不要太长；
-   🚀 不要在钩子函数中写大量业务代码；
-   🚀 异步使用 aysnc await 语法；
-   🚀 不是常用的方法不要全局挂载；
-   🚀 文件命名如果是多单词则采用驼峰命名或者烤肉串大小写，尽量简洁明了；

### 基础组件名。 【注：src/components 目录。】

> 基础组件文件命名应该以 base 为前缀命名，以示其唯一性，并且以横线连接。

```
例子：
src
└─ resources
   └─ components
      └─ base-list
         ├─ index.js      //源码
         ├─ index.scss    //样式
         └─ README.md     //组件使用说明文档
```

### 业务组件名。 【注：src/views/components 目录。】

> 业务组件文件命名应该以 the 为前缀命名，以示其唯一性，并且以横线连接。

```
例子：
src
└─ views
   └─ components
      └─ the-loading
         ├─ index.js      //源码
         ├─ index.scss    //样式
         └─ README.md     //组件使用说明文档
```

### 路由文件创建与命名。 【注：src/config/router 目录。】

为了方便维护与开发，建议路由文件命名与对应的页面文件命名保持一致，尽量简洁明了。

```
例子：
src
└─ config
   └─ router
      |- index.js
      |- dev.js
      |- home.js
```

### 接口文件创建与命名。 【注：src/config/apis 目录。】

为了方便维护与开发，建议接口文件命名与对应的页面文件命名保持一致，尽量简洁明了。

```
例子：
src
└─ config
   └─ apis
      |- index.js
      |- home.js
```

### 状态切片文件创建与命名。 【注：src/config/store 目录。】

为了方便维护与开发，建议以当前对应模块或者功能命名文件夹，尽量简洁明了。

```
例子：
src
└─ config
   └─ store
      └─ dev
         |- index.js
      └─ home
         |- index.js
```

### 图片资源。 【注：src/assets/img 目录。】

建议图片文件夹命名与对应的页面文件命名保持一致，公共图片资源放置到 src/assets/img/base 目录下即可。

```
例子：
src
└─ assets
   └─ img
      |- index
      |- dev
      |- base
```

## git 版本规范

### 分支管理

一般项目分主分支（master）和其他分支。 当有团队成员要开发新功能(Feather)或改 BUG(Fix) 时，就从 master 分支开一个新的分支。

### Commit 规范

-   feat 新增功能
-   fix 修复 bug
-   docs 文档变更
-   style 代码格式（不影响功能，例如空格、分号等格式修正）
-   refactor 代码重构
-   perf 改善性能
-   test 测试
-   build 变更项目构建或外部依赖（例如 scopes: webpack、gulp、npm 等）
-   ci 更改持续集成软件的配置文件和 package 中的 scripts 命令，例如 scopes: Travis, Circle 等
-   chore 变更构建流程或辅助工具
-   revert 代码回退

### Tag 版本号

版本号以 v 开头，根据当前仓库的 tag 编号进行累加，如：v1.10.45。

## 项目目录说明

```
react-h5-tmp                            //
├─ .env.development                     // 开发环境配置文件
├─ .env.production                      // 生产环境配置文件
├─ .env.test                            // 灰度 or 测试 or or uat环境配置文件
├─ .eslintignore                        //
├─ .eslintrc.js                         // ESlint配置文件
├─ .npmrc                               //
├─ .prettierrc.js                       // prettier配置文件
├─ .vscode                              //
│  └─ settings.json                     //
├─ babel.config.js                      //
├─ craco.config.js                      // 构建脚本（webpack配置）
├─ jsconfig.json                        //
├─ package.json                         //
├─ pnpm-lock.yaml                       //
├─ postcss.config.js                    //
├─ public                               //
│  ├─ index.html                        // 入口文件
│  └─ static                            // 静态资源
│     └─ favicon.ico                    //
├─ README.md                            // 项目描述文件
├─ run.bat                              // 批处理文件
└─ src                                  // 业务代码
   ├─ assets                            // 静态资源 hash处理
   │  ├─ css                            // css
   │  │  ├─ index.scss                  //
   │  │  └─ utils                       //
   │  │     └─ @util.scss               //
   │  ├─ img                            // img
   │  │  └─ base                        //
   │  │     ├─ empty.png                //
   │  │     └─ loading@2x.gif           //
   │  └─ js                             // js
   ├─ config                            // 业务配置目录
   │  ├─ apis                           // 所有接口相关
   │  │  ├─ index.js                    //
   │  │  └─ list.js                     //
   │  ├─ router                         // 所有路由相关
   │  │  ├─ dev.js                      //
   │  │  └─ index.js                    //
   │  └─ store                          // 状态商店（所有全局状态管理相关）
   │     └─ dev                         //
   │        └─ index.js                 //
   ├─ index.js                          // 入口js文件
   ├─ layout                            // 布局组件
   │  ├─ frame-view                     //
   │  │  ├─ index.js                    //
   │  │  └─ index.scss                  //
   │  ├─ README.md                      //
   │  └─ tabbar                         //
   │     └─ index.js                    //
   ├─ packages                          // 项目配套的第三方包
   │  ├─ console                        // vConsole配置
   │  │  └─ index.js                    //
   │  ├─ request                        // axios请求库封装
   │  │  ├─ cancel                      //
   │  │  │  ├─ index.js                 //
   │  │  │  └─ utils                    //
   │  │  │     └─ generateReqKey.js     //
   │  │  ├─ httpErrorStatusHandle       //
   │  │  │  └─ index.js                 //
   │  │  ├─ index.js                    //
   │  │  ├─ loading                     //
   │  │  │  └─ index.js                 //
   │  │  ├─ README.md                   //
   │  │  └─ retry                       //
   │  │     └─ index.js                 //
   │  ├─ router                         // router 核心封装(集中导出)
   │  │  └─ index.js                    //
   │  └─ store                          // Redux 核心封装(集中导出)
   │     ├─ index.js                    //
   │     └─ modules.js                  //
   ├─ reportWebVitals.js                //
   ├─ resources                         // 全局基础资源如基础组件、全局插件等
   │  ├─ components                     // 基础组件
   │  │  └─ base-list                   //
   │  │     ├─ index.js                 //
   │  │     ├─ index.scss               //
   │  │     └─ README.md                //
   │  └─ plugin                         // 全局插件
   ├─ utils                             // 工具库
   │  ├─ helper                         // 帮助类
   │  │  └─ env.js                      //
   │  └─ tools                          // 其他工具类
   │     ├─ eventBus                    //
   │     │  └─ index.js                 //
   │     ├─ get-realpx                  //
   │     │  └─ index.js                 //
   │     ├─ sleep.js                    //
   │     └─ validate.js                 //
   └─ views                             // 视图
      ├─ app                            //
      │  └─ App.js                      //
      ├─ components                     //
      │  └─ the-loading                 //
      │     ├─ index.js                 //
      │     └─ index.scss               //
      ├─ dev                            //
      │  ├─ components                  //
      │  │  ├─ eventBus                 //
      │  │  │  ├─ components            //
      │  │  │  │  ├─ children.js        //
      │  │  │  │  └─ find.js            //
      │  │  │  └─ index.js              //
      │  │  ├─ layOut                   //
      │  │  │  └─ index.js              //
      │  │  ├─ list                     //
      │  │  │  ├─ index.js              //
      │  │  │  └─ index.scss            //
      │  │  ├─ lodashjs                 //
      │  │  │  └─ index.js              //
      │  │  ├─ redux                    //
      │  │  │  ├─ index.js              //
      │  │  │  └─ index.scss            //
      │  │  └─ tabbar                   //
      │  │     └─ index.js              //
      │  ├─ index.js                    //
      │  └─ index.scss                  //
      ├─ err404                         //
      │  ├─ index.js                    //
      │  └─ index.scss                  //
      └─ index                          //
         ├─ index.js                    //
         └─ index.scss                  //

```
