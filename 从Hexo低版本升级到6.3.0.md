# 从Hexo低版本升级到6.3.0

作者：bulldoge

邮箱：bulldoge@163.com

网站：[https://bulldoge.com](https://bulldoge.com)

## 一、依赖
安装最新版本nodejs和npmjs，可参考以下链接：

[https://nodejs.org](https://nodejs.org)

[https://docs.npmjs.com/downloading-and-installing-node-js-and-npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)

## 二、安装hexo
安装hexo至最新稳定版本6.3.0，可参考以下链接版本信息：
   
   [https://www.npmjs.com/package/hexo?activeTab=versions](https://www.npmjs.com/package/hexo?activeTab=versions)

   [https://hexo.io](https://hexo.io)

## 三、安装blog
>hexo init bulldoge.com

>cd bulldoge.com

>rm -rf _config.landscape.yml	_config.yml package.json source themes

>cp ../bakup/_config.yml package.json source themes .

>npm install

>hexo -v

>hexo clean

>hexo g

>hexo s

## 四、访问
http://localhost:4000

## 五、package.json

```

{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "build": "hexo generate",
    "clean": "hexo clean",
    "deploy": "hexo deploy",
    "server": "hexo server"
  },
  "hexo": {
    "version": "6.3.0"
  },
  "dependencies": {
    "@fancyapps/fancybox": "^3.5.7",
    "express": "^4.17.1",
    "gulp-htmlclean": "^2.7.22",
    "gulp-htmlmin": "^5.0.1",
    "gulp-imagemin": "^7.1.0",
    "gulp-minify-css": "^1.2.4",
    "gulp-uglify": "^3.0.2",
    "hexo": "^6.3.0",
    "hexo-generator-archive": "^2.0.0",
    "hexo-generator-category": "^2.0.0",
    "hexo-generator-index": "^3.0.0",
    "hexo-generator-tag": "^2.0.0",
    "hexo-renderer-ejs": "^2.0.0",
    "hexo-renderer-marked": "^6.0.0",
    "hexo-renderer-stylus": "^2.1.0",
    "hexo-server": "^3.0.0",
    "hexo-generator-json-content": "^4.2.3",
    "hexo-generator-search": "^2.4.1",
    "hexo-related-popular-posts": "^5.0.1",
    "hexo-renderer-less": "^2.0.2",
    "hexo-util": "^2.4.0",
    "hexo-wordcount": "^6.0.1",
    "zlib": "^1.0.5"
  },
  "devDependencies": {
    "gulp": "^4.0.2"
  },
  "main": "gulpfile.js",
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": ""
}

```
## 六、TODO
执行上一步npm install的时候，有如下过期插件提醒信息，待处理

```

npm WARN deprecated gulp-minify-css@1.2.4: Please use gulp-clean-css
npm WARN deprecated source-map-url@0.4.1: See https://github.com/lydell/source-map-url#deprecated
npm WARN deprecated stable@0.1.8: Modern JS already guarantees Array#sort() is a stable sort, so this library is deprecated. See the compatibility table on MDN: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#browser_compatibility
npm WARN deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
npm WARN deprecated har-validator@5.1.5: this library is no longer supported
npm WARN deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
npm WARN deprecated cryptiles@0.2.2: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
npm WARN deprecated source-map-resolve@0.5.3: See https://github.com/lydell/source-map-resolve#deprecated
npm WARN deprecated chokidar@1.7.0: Chokidar 2 will break on node v14+. Upgrade to chokidar 3 with 15x less dependencies.
npm WARN deprecated gulp-util@3.0.8: gulp-util is deprecated - replace it, following the guidelines at https://medium.com/gulpjs/gulp-util-ca3b1f9f9ac5
npm WARN deprecated boom@0.4.2: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
npm WARN deprecated sntp@0.2.4: This module moved to @hapi/sntp. Please make sure to switch over as this distribution is no longer supported and may contain bugs and critical security issues.
npm WARN deprecated fsevents@1.2.13: The v1 package contains DANGEROUS / INSECURE binaries. Upgrade to safe fsevents v2
npm WARN deprecated chokidar@2.1.8: Chokidar 2 does not receive security updates since 2019. Upgrade to chokidar 3 with 15x fewer dependencies
npm WARN deprecated fsevents@1.2.13: The v1 package contains DANGEROUS / INSECURE binaries. Upgrade to safe fsevents v2
npm WARN deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated hoek@0.9.1: This version has been deprecated in accordance with the hapi support policy (hapi.im/support). Please upgrade to the latest version to get the best features, bug fixes, and security patches. If you are unable to upgrade at this time, paid support is available for older versions (hapi.im/commercial).
npm WARN deprecated node-uuid@1.4.8: Use uuid module instead
npm WARN deprecated request@2.51.0: request has been deprecated, see https://github.com/request/request/issues/3142
npm WARN deprecated request@2.88.2: request has been deprecated, see https://github.com/request/request/issues/3142
npm WARN deprecated hawk@1.1.1: This module moved to @hapi/hawk. Please make sure to switch over as this distribution is no longer supported and may contain bugs and critical security issues.
npm WARN deprecated svgo@1.3.2: This SVGO version is no longer supported. Upgrade to v2.x.x.

added 1076 packages, and removed 1 package in 3m

```

## 七、更新过期插件
1. gulp-minify-css@1.2.4 -> gulp-clean-css

>cd bulldoge.com

>npm install gulp-clean-css --save-dev

added 3 packages in 2m

查找使用gulp-minify-css的地方，统一替换成gulp-clean-css

2. svgo@1.3.2 -> svgo@2.8.0

将ulp-imagemin从package.json中配置为最新版本8.0.0，然后从项目目录npm install，从而间接升级svgo。

## 八、本地文件更新
1. instant.page3.0.0 -> instant.page5.2.0

用途：预加载网页，提升访问体验。

升级方法：访问官网[https://instant.page](https://instant.page/)查看最新版本，浏览器直接输入[https://instant.page/5.2.0](https://instant.page/5.2.0)版本号，直接从官网获取代码，保存在本地服务器使用。

2. clipboard2.0.4 -> clipboard2.0.11

用途：复制内容到剪切板，无需flash、无需框架、小巧。

升级办法：

访问官网[https://clipboardjs.com](https://clipboardjs.com)查看最新版本，在官方提供的任意第三方CDN处直接浏览器下载，保存在本地服务器使用：

[https://cdn.jsdelivr.net/npm/clipboard@2.0.11/dist/clipboard.min.js](https://cdn.jsdelivr.net/npm/clipboard@2.0.11/dist/clipboard.min.js)

[https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.11/clipboard.min.js](https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/2.0.11/clipboard.min.js)

[https://cdn.rawgit.com/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js](https://cdn.rawgit.com/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js)

[https://rawcdn.githack.com/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js](https://rawcdn.githack.com/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js)

[https://unpkg.com/clipboard@2/dist/clipboard.min.js](https://unpkg.com/clipboard@2/dist/clipboard.min.js)

[https://cdn.statically.io/gh/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js](https://cdn.statically.io/gh/zenorocha/clipboard.js/v2.0.11/dist/clipboard.min.js)

## 常用网站

1.npmjs

[https://www.npmjs.com](https://www.npmjs.com/)

2.cdnjs

[https://cdnjs.com](https://cdnjs.com/)

3.jsDelivr

[https://www.jsdelivr.com](https://www.jsdelivr.com/)


   
