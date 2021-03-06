## config
项目config会和公共层config合并

/src/config/index.js
```javascript
import utils from 'blue-utils';
import publicConfig from '$config';
//环境
const env = require('./env');

//合并公共的配置
const config = utils.extend(publicConfig, {
  view: {
    title: "我是项目默认标题",
    tabBar: 'home'
  },
  env,
  path: {
    base: location.origin,
    static: location.origin
  },
  share: {
    title: "blue-vue-tmpl",
    deps: "blue-vue-tmpl is vue public template",
    imgUrl: ""
  },
  login: {
    mode: `token`
  }
});

export default config;
```

/config/index.js
```javascript

//获取当前的设备
import { getCurrentDevice } from '$assets/js/device';

const config = {

  //是否为混合开发（使用区分绑定手机和跳转登录的是跳到base还是indexPath）
  mixedDevelopment: false,

  //获取用户用户信息
  user: {
    url: ''
  },

  //视图相关
  view: {
    title: "blue-vue-tmpl-title",       //默认的文档标题
    tabBar: false                    //默认的导航名，定义到的bv-tab-bar中使用
  },

  //设备
  device: getCurrentDevice(),

  //环境相关
  env: {
    dev: true,                     //开发环境
    test: false,
    beta: false,                    //beta环境
    prod: false                     //生产环境
  },

  //路径相关
  path: {
    base: location.origin,                     //域名
    home: '/',                                  //首页地址
    indexPath: location.origin,                 //服务器的html入口
    static: location.origin,                    //静态资源域名
    login: ``,                                  //登陆地址
    bindPhone: ``                               //绑定手机地址
  },

  //登录状态
  login: {
    //cookie通过登录后设cookie来识别登录态，token通过localStorage中对应的token key来识别登录态
    mode: `cookie`,
    in: {
      url: ``,          //token的login api请求
    },
    //登录退出相关
    out: {
      url: ``,    //请求url
      redirectUrl: ``   //退出后到的路由地址，不存在跳回到首页
    },
    storage: {
      ['token']: `token`
    }
  },

  //微信相关
  weChat: {
    getConfig: {
      type: 'get',
      url: '/api/wechat_config/index',
      data: {}
    }
  },

  //公共的分享相关
  share: {
    origin: '',                         //分享的域名
    title: "blue-vue-tmpl",             //分享的标题
    deps: "blue-vue-tmpl is vue public template",     //分享的简介
    imgUrl: "",                         //分享图片
    //分享相关的参数的
    params: {
      phone: 'n',                     //绑定参数
      redirectUrl: 'redirect_url',    //绑定后重定向回来的参数
      wantUrl: 'want_url'             //想要跳转的地址
    }
  },

  //绑定相关
  bind: {

    //角色绑定
    relation: {
      url: ''
    },

    //绑定手机
    phone: {
      url: '/member/personal/deitor_phone'
    }
  },

  //错误相关
  error: {
    404: {
      path: '/error-page/error-page-404'
    }
  },

  //request相关
  axios: {
    timeout: 3000
  },

  /*
  * debug模式
  * 1.关闭axios跳转到错误页面
  * */
  debug: false

};
```