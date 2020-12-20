# vue-shop

- vue 结合 koa2的移动商城项目实战
  > A Vue.js project

## Build Setup

```bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## 安装如果慢

- 使用 npm install vant --save --registry=https://registry.npm.taobao.org

## 引入 vant 组件库（有赞的）

- 全局引入样式（不推荐)
- import Vant from 'vant'
- import 'vant/lib/vant-css/index.css'
- Vue.use(Vant)

## 局部引入使用

- babel-plugin-import

````
 [
     "import",
     {
       "libraryName": "vant",
       "style": true
     }  
   ]
   ```
````
+ 然后按需使用
- import {Button} from 'vant'
- Vue.use(Button)

## 移动端适配
+ 固定高度，宽度百分比
+ rem
+ flex

## 首页布局