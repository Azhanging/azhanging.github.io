## 使用

### Vue的公共层调用
在main.js中， 使用的公共层主要有两个，device针对设备的viewport设置对应的状态
（blue-component中的```html[data-mobile-device=true]```相关），```useInVue```
主要为的Vue中的扩展，定义组件，```axios```的扩展。
```javascript
//设备相关
device({
  Vue
});

//使用插件到Vue，相对于公共的插件
useInVue({
  Vue
});
```

### Vue-router的公共层调用
主要的内容为扩展router中的```afterEach``` Hook,```beforeEach``` Hook,
meta的扩展,```scrollBehavior```记录
```javascript
//router相关的插件
useInVueRouter(Router);
```