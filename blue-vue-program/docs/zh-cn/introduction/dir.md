## 文件目录

```
- api  (公共的api存放)
- apps (存放多个vue项目)
  - blue-vue-tmpl (有关当前公共层的vue demo)
- assets (存放需要build的js,css)
  - js
  - css
   - blue-components (文件默认不存在，需要依赖到它，前往地址下载到当前文件)
- code (状态码相关)
- components (公共组件)
- config （公共配置）
  - store (vuex公共配置)
    - state.js
    - mutations.js 
    - getters.js
  - index.js (公共config，会被扩展到项目config中)
  - node.js (针对node的一些操作配置，例如vue中的模板注入)
- mock (mock server相关)
  - server.js (mock server)
  - route-opts (有关mock server中使用的是devServer的app实例，扩展express的路由配置)
- use-in-vue (扩展到vue里面的文件)
  - axios (axios的封装)
  - filter (公共的vue过滤器)
  - mint-ui (mint-ui扩展)
  - swiper (针对swiper的应用)
  - wechat (微信SDK的接入)
  - index.js (针对以上扩展的调用的入口)
- use-in-vue-router (扩展到vue-router里面的文件)
  - router-after.js (针对原来的vue-router afterEach hook的扩展)
  - router-before.js (针对原来的vue-router beforeEach hook的扩展)
  - router-id.js (针对vue-router去配置每个routerID，针对axios时候的优化)
  - router-next.js (针对router hook 中的next处理封装，涉及到一些拦截点问题)
  - index.js (针对以上扩展的调用的入口)
- version-manage （build的时候的文件版本管理使用，现只支持svn）
- vue-config （公共的vue.config.js配置）
  - index.js (公共vue.config.js，会被项目的vue.config.js扩展)
- package.json (公共层依赖)
```


## SASS的依赖

- [blue-components](https://github.com/azhanging/blue-components) 下载到/assets/css中 


