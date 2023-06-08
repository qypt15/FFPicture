
<p align="center">
  <img width="650px" src="https://tnfe.github.io/FFCreator/_media/logo/logo.png" />
</p>

<div align="center">
<a href="https://www.npmjs.com/ffcreator" target="_blank"><img src="https://img.shields.io/npm/v/ffcreator.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/ffcreator" target="_blank"><img src="https://img.shields.io/npm/l/ffcreator.svg" alt="Package License" /></a>
<a href="https://travis-ci.org/github/tnfe/FFCreator" target="_blank"><img src="https://travis-ci.org/tnfe/FFCreator.svg?branch=master" alt="Travis CI" /></a>
<a href="https://github.com/prettier/prettier" target="_blank"><img src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg" alt="Code Style"></a>
<a href="https://github.com/tnfe/FFCreator/pulls" target="_blank"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs"/></a>
<a href="https://nodejs.org" target="_blank"><img src="https://img.shields.io/badge/node-%3E%3D%208.0.0-brightgreen.svg" alt="Node Version" /></a>
</div>



### Install npm Package

```
npm install ffpicture --save
or
yarn add ffpicture
```


```javascript
parallel: 10,
```

```javascript
highWaterMark: '6mb',
```

- 通过设置`pool`来开启或者关闭对象池方式，要根据您的机器实际配置情况来合理设置。

```javascript
pool: true,
```

## 安装

### 1. 安装`node-canvas`及`headless-gl`依赖

> ##### 若是有显示设备的电脑, 比如`windows`、`Mac OSX`系统的个人`pc`电脑或者有显卡或显示设备的`server`服务器, 则可跳过这一步无需安装此依赖。

如果您使用的是`Centos`、`Redhat`、`Fedora`系统, 可以使用`yum`来安装。

```shell
sudo yum install gcc-c++ cairo-devel pango-devel libjpeg-turbo-devel giflib-devel
```

安装[`Xvfb`](https://linux.die.net/man/1/xvfb)以及[`Mesa`](http://www.sztemple.cc/articles/linux%E4%B8%8B%E7%9A%84opengl-mesa%E5%92%8Cglx%E7%AE%80%E4%BB%8B)

```shell
sudo yum install mesa-dri-drivers Xvfb libXi-devel libXinerama-devel libX11-devel
```

如果您使用的是`Debian`、`ubuntu`系统, 则可以使用`apt`来安装。

```shell
sudo apt-get install libcairo2-dev libjpeg-dev libpango1.0-dev libgif-dev build-essential g++
sudo apt-get install libgl1-mesa-dev xvfb libxi-dev libx11-dev
```

## 启动

- ### 启动项目

  - 若是有显示设备的电脑, 比如个人`pc`电脑或者有显卡或显示设备的`server`服务器, 正常启动。

```shell
npm start
```

- 无显示设备的服务器请使用`xvfb-run`命令启动程序, 关于`xvfb-run`命令更多的参数可以点击[这里](http://manpages.ubuntu.com/manpages/trusty/man1/xvfb-run.1.html)查看。

```shell
xvfb-run -s "-ac -screen 0 1280x1024x24" npm start
```

## 常见问题

1. #### 当安装时提示错误 missing package'xi'

```shell
No package 'xi'

foundgyp: Call to 'pkg-config --libs-only-l x11 xi xext' returned exit status 1 while in angle/src/angle.gyp. while loading dependencies of binding.gyp while trying to load binding.gyp
```

#### 解决

```shell
yum install libXi-devel libXinerama-devel libX11-devel
```

2. #### 可以正常启动程序但是报错 `doesn't support WebGL....`

#### 解决

The node app should be started as follows.

```shell
xvfb-run -s "-ac -screen 0 1280x1024x24" npm start
```

3. Npm 安装报错 `ERR! command sh -c node-pre-gyp install --fallback-to-build`

#### 解决

这可能是由您的 node 版本引起的。如果是 node`v15`，会出现此问题 [https://github.com/Automattic/node-canvas/issues/1645](https://github.com/Automattic/node-canvas/issues/1645)。请把 node 版本降低到`v14`。

## License

[MIT](./LICENSE)
