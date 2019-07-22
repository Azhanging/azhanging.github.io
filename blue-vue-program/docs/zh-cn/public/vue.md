## [Vue相关](https://github.com/Azhanging/blue-vue-program/tree/master/use-in-vue)

### prototype扩展

每个vue组件都mixin了config
```javascript
//mixin program in Vue
Vue.mixin({
    data() {
      //项目config
      return {
        config
      };
    }
});
```
***
公共分享
```javascript
Vue.prototype.$share({
    title:`titleString`,
    desc:`descString`,
    imgUrl:`imgUrl`
});
```
***
微信分享
```javascript
Vue.prototype.$weChatShare({
    title:`titleString`,
    desc:`descString`,
    imgUrl:`imgUrl`
});
```
***
[blue-utils](https://github.com/azhanging/blue-utils)
```javascript
import utils from 'blue-utils';
Vue.prototype.$utils = utils;
```
***
[base64](https://www.npmjs.com/package/js-base64)
```javascript
import {Base64} from 'js-base64';
Vue.prototype.$base64 = Base64;
```
***
[axios](https://www.npmjs.com/package/axios)
```javascript
import Axios from 'axios';
Vue.prototype.$axios = Axios.create({});
```
***
[mint-ui](https://mint-ui.github.io/docs/)
```javascript
import { MessageBox } from 'mint-ui';
//弹出式提示框，有多种交互形式。
Vue.prototype.$messageBox = MessageBox;
//打开弹窗,参数和mint-ui中的Toast一样
Vue.prototype.$toast = $toast;
//关闭弹窗
Vue.prototype.$closeToast = $closeToast;
```



