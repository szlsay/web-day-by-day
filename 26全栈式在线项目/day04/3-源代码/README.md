# 课程笔记

## 反馈

-  不会的太多了,跟不上.老师讲的尽量激情一点吧
- 老师讲的东西太多了,之前express框架忘了!ＡＰＩ了
-  知识点有点多,下午的案例要重新看视频才能动手
  +  Ecmascript 6
  +  babel
  +  Express（以前学过的）
  +  npm scripts
- 能否重新串一下底层结构的构建那部分,要做什么,主线不清晰,老师再给捋捋
- 很担心后几天能不能跟上。
-  老师，我已经不知道我是清楚还是模糊了。。。。
-  连不起来，晚自习还得看视频敲代码，贼郁闷
-  讲的太快了,东西太多了,能不能多关注下吸收情况,如果大家普遍跟不上,那这项目就没意义了
-  老师讲涉及node操作的地方在稍微复习一下呗，比方说那些API什么的，惭愧惭愧放假回来都忘没了！谢谢老师！
- 感觉老师思路稍稍有点不清晰，有时候听着听着就听跑偏了
-  老师是不是自己在讲给自己听呢，都不管我们有没有听懂，诶诶，全程懵逼，细节太多，api太多，希望老师明天能给我们再过一遍
- 老师，jQuery Mobile 和 touch 咱们讲嘛
  + 已经过时了

---

## 复习

- Ecmascript 6 + Babel
- npm scripts
- Express

### Babel Register

第一：在项目根目录下创建一个 `.babelrc` 文件，写入以下内容：

```json
{
  "presets": [
  ]
}
```

第二：安装对应的转码规则：

```bash
# ES2015转码规则
$ npm install --save-dev babel-preset-es2015

# react转码规则
$ npm install --save-dev babel-preset-react

# ES7不同阶段语法提案的转码规则（共有4个阶段），选装一个
$ npm install --save-dev babel-preset-stage-0
$ npm install --save-dev babel-preset-stage-1
$ npm install --save-dev babel-preset-stage-2
$ npm install --save-dev babel-preset-stage-3
```

第三：将 `.babelrc` 文件中修改为以下内容：

```json
{
  "presets": [
    "es2015"
  ]
}
```

第四步（从第四步开始，前三部必不可少）：

- babel-cli：命令行转码
- babel-node：babel-cli工具自带一个babel-node命令，提供一个支持ES6的REPL环境
- babel-register：实时转码，所以只适合在开发环境使用
- babel-core：如果某些代码需要调用Babel的API进行转码，就要使用babel-core模块

babel-cli：

一种使用方式就是全局安装：`npm install -g babel-cli`（可以通过 `npm root -g` 查看全局包安装目录），
只要全局安装了 `babel-cli`，则会在命令行中多出一个命令：`babel`。

这里如果使用全局安装的 `babel-cli` 进行转码是没有问题的，但是问题是如果一旦项目给了别人，
别人不知道你使用了这个转码工具，所以解决方式就是将 `babel-cli` 安装到本地项目中：

```bash
npm install --save-dev babel-cli
```

这种第三方命令行工具如果安装到本地项目，会在 `node_modules` 中生成一个目录：`.bin`，
然后第三方命令行工具会将对应的可执行文件放到该目录中。

这样的话，就可以直接在本地项目中使用该第三方命令行工具了。

对于如何使用，则可以通过配置 `package.json` 文件中的 `scripts` 字段来配置使用：

```json
{
  "name": "babel-demo",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "babel demo1.js"
  },
  "devDependencies": {
    "babel-cli": "^6.22.2",
    "babel-preset-es2015": "^6.22.0",
    "babel-preset-react": "^6.22.0"
  }
}
```

babel-register（适合开发阶段，实时编码转换）:

第一：安装 babel-register

```bash
npm install --save-dev babel-register
```

第二：添加一个傀儡文件(main.js)：

```js
require('babel-register')
require('你的核心功能代码入口文件模块')
```

第三：使用 node 执行 `main.js`，而不是你的入口文件.

### --save 和 --save-dev

通过 `--save` 参数安装的包，是将依赖项保存到 package.json 文件中的 dependencies 选项中。
通过 `--save-dev` 参数安装的包，是将依赖项保存到 package.json 文件中的 devDependencies 选项中。

无论是 `--save` 或者 `--save-dev` 安装的包，通过执行 `npm install` 都会将对应的依赖包安装进来。

但是，在开发阶段会有一些仅仅用来辅助开发的一些第三方包或是工具，然后最终上线运行（到了生产环境），
这些开发依赖项就不再需要了，就可以通过 `npm install --production` 命令仅仅安装 `dependencies` 中的
依赖项。

---

## Express

### hello world

### 基本路由

根据不同的请求路径分发到具体的请求处理函数

### 处理静态资源

### 模板引擎

### 中间件

### Express API

- express()
- Application
- Request
- Response
- Router

---

## 知识点

- Nunjucks 模板引擎
- Mongoose ORM 对象模型映射

## 在线教育项目

### 使用 Nunjucks 模板引擎抽取模板页

### 广告管理

### 路由设计

| 请求方法 |   请求路径  | 查询字符串 |                                请求体                                | 路径参数 |        作用        |
|----------|-------------|------------|----------------------------------------------------------------------|----------|--------------------|
| GET      | /advert     |            |                                                                      |          | 渲染广告管理列表页 |
| GET      | /advert/add |            |                                                                      |          | 渲染添加广告页面   |
| POST     | /advert/add |            | image、link、start_time、end_time、title、create_time、last_modified |          | 处理添加广告请求   |
|          |             |            |                                                                      |          |                    |

## 晚自习补课

- jsonp
- nvm
- nrm
- Yarn

### jsonp

### nvm

Node Version Management

- nvm list 查看所有已安装的 node 版本
- nvm install 版本号 安装指定版本的 node
- nvm use 版本号 切换到指定版本号
- nvm proxy 代理地址 配置代理进行下载

### nrm（node registry manager）

使用淘宝的 cnpm 镜像源下载：

```
npm install --save express --registry=https://registry.npm.taobao.org
```

第一：

```
npm install -g nrm
```

基本使用：

```

```


### Yarn

Yarn 是一个 Facebook 开源的一个类似于 npm 的一个包管理工具，也就是 npm 能做的，
yarn 也能做。

安装：

```bash
npm install -g yarn
```

使用：

```bash
# npm init
yarn init

# npm install --save 包名
yarn add 包名

# 离线安装
yarn add 包名@版本号 --offline

# npm install
yarn install

# npm uninstall 包名
yarn remove 包名

# npm install -g 包名
yarn global add 包名

# npm uninstall -g 包名
yarn global remove 包名
```


## 目标

1. 能掌握理解 Express 中间件执行机制并举例
2. 能掌握利用 Express 中间件处理网站 404
3. 能掌握 Express 中间件统一处理全局错误
4. 能掌握 Nunjucks 模板引擎的基本使用（布局功能）
5. 能掌握利用 Express 中间件解析表单 POST 请求体
