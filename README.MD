### 关于公司所有vue项目配置说明：
 >  公司vue项目写法大体上符合官方推荐写法，也有一些因为项目进度、人员变动等原因有一些风格上的不统一。
1.开发时的全局配置在main.js，如flexable.js等
2.开发时环境切换：config ==> test下，改变api代理的域名即可切换至不同环境
3.一些特殊域名是在vuex初始化请求的域名 ==> api ==> global.js
4.本地开发，建议run test，因为test代理好了不同环境下的请求域名    ![image.png](https://upload-images.jianshu.io/upload_images/4013462-87575ba55f2be64d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240) 
5.本地开发接口代理： config ==> index.js，按需代理     ![image.png](https://upload-images.jianshu.io/upload_images/4013462-4b613b9024fb93ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
6.全局状态管理：配请参照官方文档写法，公司项目如用到vuex，都严格按照官方推荐写法操作：  [https://vuex.vuejs.org/zh/](https://vuex.vuejs.org/zh/)



### 移动端项目说明（yoomathm）
  > 公司移动端项目大部分为vue技术栈（vue + vuex + vue-router），其中项目状态管理我是严格按照官方文档搭建，如有疑问，请查阅官方文档说明。
  #### 1.app内嵌页面 -- clent
   > 此项目页面大多数为app端内嵌页面，其中也有因为项目管理原因，放在其中的一些活动页面，项目结构如下：![image.png](https://upload-images.jianshu.io/upload_images/4013462-cff05dd93a5f5d1c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     里面包含了一些活动相关的页面，如下：       ![image.png](https://upload-images.jianshu.io/upload_images/4013462-29922dc8075f106b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 开发流程：
 > 1.gitlab拉取代码
    2.按需修改业务
    3.提交代码至gitlab
    4.后续打包流程在bamboo上进行（npm install, npm run build），前段维护打包脚本build.js，build.js为node编写，目的是为了将多个vue项目统一install和build，再将打包结果统一给到运维部署。

### 独立活动相关项目
> 有数学活动包括：PK活动，期末活动，科举活动，开学活动，暑假训练营等等，为了方便管理和保证开发进度，部分活动放在了client里面
 ![image.png](https://upload-images.jianshu.io/upload_images/4013462-2519898215e15d1b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
项目业务修改的话，参照上面的流程。

### 老移动端项目 yoomath-m
 > 老的移动端项目为jquery项目，写法也很基础，不许要过多阐述。下面为项目结构：
 ![image.png](https://upload-images.jianshu.io/upload_images/4013462-7d6373b5ded13b7a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个项目平时涉及的改动不多，需求需要的话在看代码，很简单的，就不详细阐述了

###微信端项目说明yoomath-wx：
 > 此项目也为jqeury项目，写法也很基础，平时涉及的改动不多
![image.png](https://upload-images.jianshu.io/upload_images/4013462-77688ffc7295b10c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我改过这个项目是之前做小程序时的一些绑定处理，或者公众号的微信支付之类的操作，我想这个项目如果不是需要改动公众号或者小程序，不会动。

### 小悠快批  yoocorrect
> 小悠快批其实并没有没有用到vuex做状态管理，核心功能批改逻辑也被Native端重构了，后期迭代可能会涉及到相关修改，，所以列出主要的业务代码结构，如下图：
![image.png](https://upload-images.jianshu.io/upload_images/4013462-88d3b7c212383ca6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
小悠快批采取页面书写方式为就近维护，及相关页面的组件和图片就放在同一文件夹，这样修改容易查找和同一管理

###新PC端 yoomathweb
> 新pc端为今年重构的项目，技术栈为vue，相关配置参考上面移动端配置。下面为项目结构讲解：
![`211MH[V@ZE1]HU3SF5P4%A.png](https://upload-images.jianshu.io/upload_images/4013462-337eff2b8a110e53.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
新pc端就是vue的基本套路，不难。

### 图片标注 tag-image
> 图片标注功能为vue项目，不过最后打包结果需要嵌套至管控台项目的tag文件夹
此项目代码目录结构简单，就不做过多阐述。

### 家长端小程序 wechat-app
1.公司小程序开发采用了腾讯内部员工开发的技术框架wepy，本地运行项目步骤如下：
首先gitLab拿去代码，进入根目录npm install，然后npm run dev生成dist文件，在开发者工具中就打开小程序项目调试，将项目目录选择dist，即可实时看到调试效果
2.项目目录介绍：
![image.png](https://upload-images.jianshu.io/upload_images/4013462-a7c563ee194b4102.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
开发过vue的话，这个配置很类似.
3.项目上线注意事项：
首先，项目要遵从小程序的上线规则，句规则参照：[https://developers.weixin.qq.com/blogdetail?action=get_post_info&docid=000808396a4260c0f1066c5a551801&highline=%E5%BC%BA%E5%88%B6%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E4%BF%A1%E6%81%AF](https://developers.weixin.qq.com/blogdetail?action=get_post_info&docid=000808396a4260c0f1066c5a551801&highline=%E5%BC%BA%E5%88%B6%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E4%BF%A1%E6%81%AF)
其次，上线前一定先删除目录下的dist，重新再执行npm run build，这样尽可能缩小实际上线项目体积（小于2M），打包好后，在开发者工具上上传代码，后台可提交审核
4.小程序如何测试：
将测试人员设置为开发者，不是开发者无法进入开发板，同时手机打开调试模式，即可进路小程序体验版
5.公司小程序代码配置介绍：
![image.png](https://upload-images.jianshu.io/upload_images/4013462-3919990f7735c24e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
项目公共配置放在app.wepy里面，包括了授权、验证、登录以及获取用户信息
项目基础参数配置，baseURL为借口请求域名，h5URL为学情分析的域名，都需要随环境变化手动切换，上线前换为正式域名
相关文档：
         小程序：[https://developers.weixin.qq.com/miniprogram/dev/](https://developers.weixin.qq.com/miniprogram/dev/)
         Wepy：[https://tencent.github.io/wepy/document.html](https://tencent.github.io/wepy/document.html)

### 渠道端 web-nqd
> 渠道销售端为外包做的项目，使用的依然是vue，动态路由的方式开发，用了ele组件库，不做具体阐述，有迭代需求的话，直接找对应位置修改即可，代码难度不大。

### 公式键盘
> 公式键盘为二次开发项目，使用的技术栈为react + react-router + redux + RN组件，项目具体文档在项目中有具体阐述（REDEME）。
项目最后是将静态文件放入native，内嵌到webview（具体文件请native配合查找），需要注意：因为ios和安卓的不同，他们index.html处理并不一样
