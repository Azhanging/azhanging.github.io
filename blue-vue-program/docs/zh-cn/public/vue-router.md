## [Vue-Router相关](https://github.com/Azhanging/blue-vue-program/tree/master/use-in-vue-router)

[Vue.mixin中有两个hook，beforeRouteEnter和beforeRouteLeave，为了处理刷新keep-alive问题，由于页面后退之后，再前进，页面是需要重新获取数据的](https://github.com/Azhanging/blue-vue-program/blob/master/use-in-vue-router/index.js)。

### prototype

```javascript
VueRouter.prototype.getHref //获取当前地址href，直接获取location.href会出现路由未更新前的地址
```
***
```javascript
VueRouter.prototype.routerBack //路由后退规则,如果有具体的路由，否则走根路径
```
***
```javascript
VueRouter.prototype.routerTo(path) //跳转到指定的地址
```
***
```javascript
VueRouter.prototype.matchRoutes(routesRegExp) //匹配路由的路径组，返回布尔值
```
***
```javascript
VueRouter.prototype.getParam(key) //获取params中的某个参数
```
***
```javascript
VueRouter.prototype.getMeta(key) //获取currentRoute中的meta
```





### 扩展的文件

### [router-id](https://github.com/Azhanging/blue-vue-program/blob/master/use-in-vue-router/router-id.js)
用于给路由添加id,细节化router跳转和axios require的跳转问题
***
### [router-before](https://github.com/Azhanging/blue-vue-program/blob/master/use-in-vue-router/router-before.js)
扩展公共层路由执行beforeEach业务
***
### [router-after](https://github.com/Azhanging/blue-vue-program/blob/master/use-in-vue-router/router-after.js)
扩展公共层路由执行afterEach业务


