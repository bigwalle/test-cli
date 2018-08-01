# ecarx-cli
A simple CLI for scaffolding [weex](http://weex.apache.org/cn/) projects, we provide [ecarx-template](https://github.com/welcome112s/ecarx-template) to quickly build small and medium sized app.

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
build full zip and copy to specified path, generate full zip and diff zip in  [ecarx-template](https://github.com/welcome112s/ecarx-template)'s dist folder.
```
$ ecarx build -d
```
build full zip and copy to specified path, generate full zip and diff zip in  [ecarx-template](https://github.com/welcome112s/ecarx-template)'s dist folder， post full zip info to your server at same time.
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

generate [ecarx-template](https://github.com/welcome112s/ecarx-template) in current execution directory, you can quickly build your app through
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
you can update [ecarx-template](https://github.com/welcome112s/ecarx-template)'s every file/path when ecarx-template has updated, **`but your must use it be careful, when the file/path has be changed by yourself that you want to update`**.
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
* git clone https://github.com/welcome112s/ecarx-cli
* cd ecarx-cli && git checkout dev
* npm/cnpm i
* cd ecarx-template or ecarx init project
* node ../ecarx-cli/bin/ecarx.js + command

## Change Log

### 1.0.1-beta
* [bugfix]  修改了初始化工程的脚本。.