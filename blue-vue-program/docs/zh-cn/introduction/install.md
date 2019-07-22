## 安装

因为是公共层，和项目层分离，在公共层有属于自己的node_modules，先安装公共层依赖

```cmd
npm i 或者 cnpm i  
```

项目依赖也是需要自行安装，例如下载demo中的依赖，进到apps/blue-vue-tmpl
```
npm i 或者 cnpm i
```

在blue-vue-tmpl中启动
```
npm run serve
```

## SASS的依赖

- [blue-components](https://github.com/azhanging/blue-components) 下载到/assets/css中

## 某些npm包的问题

npm包中存在bug
把./components/vue-upload-component/vue-upload-component.js,
./components/mint-ui/mint-ui.js复制到node_modules相对的npm包中


