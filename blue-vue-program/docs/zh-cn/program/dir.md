## 文件目录

```
- blue-vue-tmpl
  - mock (mock server api)
  - public
  - src
    - assets (项目资源)
    - components
    - config
    - router
    - store
    - use-in-vue-program
    - use-in-vue-router-program
    - views
  - dev-server.js
  - version-manage.js
  - vue.config.js 
```

### alias配置
$开头的为公共层文件，@开头为项目文件

vue-config/index.js
```javascript
module.exports = {
  configureWebpack: {
    resolve: {
      alias: {
        '$config': resolve(`./config`),
        '$components': resolve(`./components`),
        '$load-more': resolve(`./assets/js/load-more`),
        '$page-list': resolve(`./components/m-page-list/index`),
        '$assets': resolve(`./assets`),
        '$upload': resolve(`./components/vue-upload-component/upload`),
        '$wechat': resolve(`./use-in-vue/wechat`),
        '$use-in-vue': resolve(`./use-in-vue`),
        '$use-in-vue-router': resolve(`./use-in-vue-router`),
        '$axios': resolve(`./use-in-vue/axios`),
        '$api': resolve(`./api`),
        '$code': resolve(`./code`)
      }
    }
  },
  css: {
    loaderOptions: {
      sass: {
        data: `@import "@css/index.scss";`
      }
    }
  },
  pwa: {
    assetsVersion: hash(time)
  },
  filenameHashing: true
};
```

vue.config.js 合并了公共层vue配置
```javascript
//公共的vue-config
const publicVueConfig = require('../../vue-config');
const utils = require('blue-utils');
const path = require('path');
const hash = require('hash-sum');
const devServer = require(`./dev-server`);

//当前打包的时间戳
const time = new Date().getTime();
//版本号hash
const versionHash = hash(time);

function resolve(dir) {
  return path.join(__dirname, dir);
}

//合并两个配置
module.exports = utils.extend(publicVueConfig, {
  //webpack config extend public webpack config
  configureWebpack: {
    resolve: {
      alias: {
        //@开头的为项目的别名路径
        '@': resolve('src'),
        '@router': resolve('src/router'),
        '@store': resolve('src/store'),
        '@config': resolve('src/config'),
        '@assets': resolve('src/assets'),
        '@css': resolve('src/assets/css'),
        '@components': resolve('src/components')
      }
    }
  },
  devServer,
  //PWA离线应用配置
  pwa: {
    //workbox配置
    workboxOptions: {
      //设置cache manifest的存放位置
      precacheManifestFilename: `static/${versionHash}/precache-manifest.[manifestHash].js`
    }
  },
  outputDir: `./server`,
  indexPath: `./views/index.tmpl`,
  assetsDir: `static/${versionHash}`
});
```


