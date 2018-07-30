# ecarx-cli
A simple CLI for scaffolding [weex](http://weex.apache.org/cn/) projects, we provide [ecarx-template](https://github.com/bmfe/ecarx-template) to quickly build small and medium sized app.

## Installation
Prerequisites: Node.js (>=4.x, 6.x preferred), npm version 3+ and Git.

```
$ npm install -g ecarx-cli
```

If you were in China, we recommand you install [cnpm](https://npm.taobao.org/) before.

```
$ cnpm install -g ecarx-cli
```

## Usage
You can code `ecarx -h` to show a profile.
```
ecarx-cli:
The following instructions are provided to help you build app !

 build      | build for ecarx project.
 dev        | start dev server.
 init       | generate ecarx template.
 install    | install ecarx platform and components' librarys.
 pack       | pack full dose zip and send to ecarx platform project.
 update     | update ecarx-template file by path.
 mock       | start a mock server.
```

## Command
#### **build**: 

ecarx cli build prod's full zip, contain js bundle, assets/images and iconfont. 
```
$ ecarx build
```
build full zip and copy to specified path, post full zip info to your server, you can use [ecarx-publish](https://github.com/bmfe/ecarx-publish) for collocation.
```
$ ecarx build -s url
```
build full zip and copy to specified path, generate full zip and diff zip in  [ecarx-template](https://github.com/bmfe/ecarx-template)'s dist folder.
```
$ ecarx build -d
```
build full zip and copy to specified path, generate full zip and diff zip in  [ecarx-template](https://github.com/bmfe/ecarx-template)'s dist folder， post full zip info to your server at same time.
```
$ ecarx build -s url -d
```
#### **dev**:

start dev server, you can change default `server.path` and `server.port` in `ecarx-template/config/ecarx.dev.js`, ecarx' app can refresh current view when your local code is changed and saved, **You can debug by forward agent software in real machine.**

forward agent software recommand:

* windows: fidder
* ios: charles

```
$ ecarx dev
```
#### **init**:

generate [ecarx-template](https://github.com/bmfe/ecarx-template) in current execution directory, you can quickly build your app through
 it.
```
$ ecarx init
```
#### **~install~** (abandon)

ecarx developed many functions based on weex (self-module), you don't have to worry about the version of the weex update, we will update weex in time, every time we have a change ( new module / bugfix / weex update and so on), you can install them to use it.
```
$ ecarx install
```

install ecarx ios sdk.
```
$ ecarx install ios
```
install ecarx android sdk.
```
$ ecarx install android
```
install both sdk.
```
$ ecarx install all
```
#### **pack**
build prod's full zip and send it to platforms's ios/android built-in package storage path.
```
$ ecarx pack
```

pack ecarx ios inner js bundle.
```
$ ecarx pack ios
```
pack ecarx android inner js bundle.
```
$ ecarx pack android 
```
pack ecarx ios && android inner js bundle.
```
$ ecarx pack all
```
#### **update**
you can update [ecarx-template](https://github.com/bmfe/ecarx-template)'s every file/path when ecarx-template has updated, **`but your must use it be careful, when the file/path has be changed by yourself that you want to update`**. 
```
$ ecarx update
```

update ecarx ios sdk.
```
$ ecarx update ios
```
update ecarx android sdk.
```
$ ecarx update android 
```
update template by path.
```
$ ecarx update template path
```
#### **mock**
start mock server, you can change default `proxy` and `mockServer` in `ecarx-template/config/ecarx.dev.js`.
```
$ ecarx mock
```

## Develop & Test

* cd ecarx-template or ecarx init project `parent directory`.
* git clone https://github.com/bmfe/ecarx-cli
* cd ecarx-cli && git checkout dev
* npm/cnpm i
* cd ecarx-template or ecarx init project
* node ../ecarx-cli/bin/ecarx.js + command

## Change Log

### 2.0.8-beta
* [bugfix] remove ecarx pack android umeng appid.
* [bugfix] jsServer undefined when packing inner zip.

### 2.0.7
* [remove] ecarx install.
* [remove] ecarx update ios/android (ecarx update tempate still in there).
* [bugfix] ip.txt send to template.
* [bugfix] newPack.config.js -> newpack.config.js.
* [bugfix] gulp in not deined.
* [bugfix] cannot find module.
* [bugfix] sass less stylus not effect.
* [feature] add socketServer.
* [feature] add `$ ecarx config reload`.
* [feature] ecarx init support choose pure template.
* [optimize] change babel to happypack.
* [optimize] make process.env.NODE_ENV customizable.

### 2.0.6-beta.4
* [bugfix] weex-loader down to 0.5.2.

### 2.0.6-beta.2/3
* [feature] update `weex-loader` to newest，support `recyle-list`.
* [feature] add socket server, start to develop save auto refresh.
* [bugfix] ecarx build -d report wrong info.

### 2.0.6-beta.1
* [bugfix] ecarx pack and ecarx build generate different zip.
* [bugfix] ecarx dev not add app board file.

### 2.0.6
* [optimize] support weex debug.
* [feature] add ecarx run ios.


### 2.0.5
* cli[add]: ecarx install all 可同时下载两端的 ecarx-sdk
* cli[add]: 支持在 init 的时候输入安卓的包名
* cli[fix]: ecarx mock 报错问题
* cli[mod]: ecarx cli 的帮助日志更新
* cli[del]: 由于 widget 已提交到 npm 上，目录下不在存在 widget，所以去掉 ecarx update widget 指令

### 2.0.4
* fix: ecarx pack all 失效问题
* fix: ecarx pack ios 失效问题
* fix: ecarx pack android 失效问题

### 2.0.3
* add: ecarx pack all
* add: ecarx pack ios
* add: ecarx pack android

### 2.0.2
* add: ecarx install ios
* add: ecarx install android
* add: ecarx update ios
* add: ecarx update android
* add: ecarx update template your_path
* add: ecarx update widget

### 2.0.1
* fix: ecarx build 会打内置包的情况
* add: ecarx pack --all 同时打两端的内置包

### 2.0.0-beta.14-16
* 添加 eslint 编译

### 2.0.0-beta.13
* 修复 windows 上报打包解析错误的bug

### 2.0.0-beta.12
* ecarx pack 没有打包本地静态资源

### 2.0.0-beta.11
* ecarx pack 没有打包本地静态资源

### 2.0.0-beta.10
* ecarx pack 没有打包本地静态资源

### 2.0.0-beta.9
* fix 脚手架 dev 报错的问题

### 2.0.0-beta.8
* 删除组件更新

### 2.0.0-beta.7
* bugfix: 修复 ecarx init 报错的问题

### 2.0.0-beta.6
* 脚手架更新： 加密算法
* 脚手架更新： 添加tree-shaking
* 脚手架更新： 精简体积，删除无用代码
* 脚手架更新： ecarx update 可选择不再覆盖


### 2.0.0-beta.5
* pack 动态给安卓添加配置信息。

### 2.0.0-beta.4
* 优化差分包逻辑，增加webpack输出提示。

### 2.0.0-beta.2
* 新增ecarx update

### 2.0.0-beta.1
* add ecarx init
* add ecarx build
* add ecarx dev
* add ecarx pack (--ios/android)
* add ecarx install (--ios/android)
* 兼容 windows
* minWeex 打包问题
* 打包js的时候 混淆会顺便删除map文件减少体积
* iconfont 打包路径问题
* 修改 ecarx NODE_env 搭配修复ecarx debug问题
* fix diff bug
* build assets 时候多调用了打 iconfont md5 方法
