# 前端技术一些踩坑记录（缓慢记录中...）

## 小程序相关另开一个仓库整理

[微信小程序踩坑记录 ](https://github.com/mrleidesen/miniprogram-issues)

## 更新日志


- `[2021-10-25]` 更新[Next.js window is not defined](#Nextjs-window-is-not-defined)
- `[2021-10-12]` 更新[禁用user-select移动端副作用](#禁用user-select移动端副作用)
- `[2021-09-26]` 更新[iOS 和安卓视频预览第一帧](#ios-和安卓视频预览第一帧)
- `[2021-09-07]` 更新[微信 H5 阴影失效](#微信-h5-阴影失效)
- `[2021-07-23]` 更新[prettier 格式化 HTML 时错位](#prettier格式化html时错位)
- `[2021-07-22]` 更新[小程序 Swiper 禁止滑动](#小程序-swiper-禁止滑动)
- `[2021-07-11]` 更新[Vite jsxInject](#vite-jsxinject)
- `[2021-07-09]` 更新[eslint 配置全局参数](#eslint-配置全局参数)
- `[2021-06-16]` 更新[React Context 简易状态管理](#react-context简易状态管理)
- `[2021-06-08]` 更新[TS 中 key/value 索引](#ts中keyvalue索引)
- `[2021-06-02]` 更新[Vue3 组合式 api 问题](#vue3组合式api问题)
- `[2021-04-29]` 更新[Vue 渲染函数问题](#vue渲染函数问题)
- `[2021-04-19]` 更新[uni-app 在安卓中调用前置摄像头自动拍照](#uni-app在安卓中调用前置摄像头自动拍照)
- `[2021-04-16]` 更新[相邻的 button 点击后让 div 发生改变](#相邻的button点击后让div发生改变)/[CSS 水平和垂直居中](#css水平和垂直居中)
- `[2021-04-07]` 更新[优化 async/await](#优化asyncawait)
- `[2021-02-25]` [Vite 的问题](#vite的问题)
- `[2021-02-23]` 更新[Element UI 如果在项目中需要 CDN 引入](#element-ui如果在项目中需要cdn引入)
- `[2021-01-22]` 更新[Tailwind 在 VSCode 中的智能提示](#tailwind在vscode中的智能提示)
- `[2020-12-25]` 更新[Vue 中通过 CDN 引入高德地图 externals 的问题](#vue中通过cdn引入高德地图externals的问题)
- `[2020-12-07]` 更新[js 文字转语音](#js文字转语音)
- `[2020-12-04]` 更新[IOS 格式化日期出错](#ios格式化日期出错)
- `[2020-9-07]` 更新[页面平滑滚动](#页面平滑滚动)
- `[2020-7-22]` 更新[Vue 和 TS](#Vue和TS)

## 目录

- [前端技术一些踩坑记录（缓慢记录中...）](#前端技术一些踩坑记录缓慢记录中)
  - [小程序相关另开一个仓库整理](#小程序相关另开一个仓库整理)
  - [更新日志](#更新日志)
  - [目录](#目录)
  - [编辑器相关（VSCode）](#编辑器相关vscode)
    - [实用插件](#实用插件)
    - [React 开启 JSX 支持](#react-开启-jsx-支持)
  - [NPM(Yarn)相关](#npmyarn相关)
    - [--save 和--save-dev 的区别](#--save-和--save-dev-的区别)
    - [npm 在国内加快下载速度](#npm-在国内加快下载速度)
  - [框架（Vue, React 等）相关](#框架vue-react-等相关)
    - [Vue 监听](#vue-监听)
    - [Vue 引入 iView 之后使用 Col 标签后 VSCode 会报错](#vue-引入-iview-之后使用-col-标签后-vscode-会报错)
    - [在 VsCode 中识别 webpack 的 alias](#在-vscode-中识别-webpack-的-alias)
    - [关于 axios 使用 post 传递 application/x-www-form-urlencoded 的问题](#关于-axios-使用-post-传递-applicationx-www-form-urlencoded-的问题)
    - [关于 Mock.js](#关于-mockjs)
    - [在 Vue 中使用`Lodash`中的`debounce`](#在-vue-中使用lodash中的debounce)
    - [后端接口 Long 类型的问题](#后端接口-long-类型的问题)
    - [Vue 和 TS](#vue-和-ts)
    - [Vue 中通过 CDN 引入高德地图 externals 的问题](#vue-中通过-cdn-引入高德地图-externals-的问题)
    - [Element UI 如果在项目中需要 CDN 引入](#element-ui-如果在项目中需要-cdn-引入)
    - [Vite 的问题](#vite-的问题)
    - [Vite2 使用 alias](#vite2-使用-alias)
    - [优化 async/await](#优化-asyncawait)
    - [Vue 渲染函数问题](#vue-渲染函数问题)
    - [Vue3 组合式 api 问题](#vue3-组合式-api-问题)
    - [React Context 简易状态管理](#react-context-简易状态管理)
    - [Vite jsxInject](#vite-jsxinject)
    - [Next.js window is not defined](#Nextjs-window-is-not-defined)
  - [HTML/CSS/JS/小程序/Git 相关](#htmlcssjs小程序git-相关)
    - [movable-view](#movable-view)
    - [关于点击穿透](#关于点击穿透)
    - [阻止事件向上传递](#阻止事件向上传递)
    - [css 来判断元素是否为空](#css-来判断元素是否为空)
    - [百度地图自定义标记点图标](#百度地图自定义标记点图标)
    - [关于判断网络状态](#关于判断网络状态)
    - [JS 录制屏幕内容](#js-录制屏幕内容)
    - [获取内部可滚动元素的滚动](#获取内部可滚动元素的滚动)
    - [原生 JS 获取当前经纬度](#原生-js-获取当前经纬度)
    - [关于调用百度腾讯等 web 服务](#关于调用百度腾讯等-web-服务)
    - [关于 cookies](#关于-cookies)
    - [微信 sdk](#微信-sdk)
    - [监听 DOM 变化](#监听-dom-变化)
    - [页面平滑滚动](#页面平滑滚动)
    - [IOS 格式化日期出错](#ios-格式化日期出错)
    - [JS 文字转语音](#js-文字转语音)
    - [Tailwind 在 VSCode 中的智能提示](#tailwind-在-vscode-中的智能提示)
    - [相邻的 button 点击后让 div 发生改变](#相邻的-button-点击后让-div-发生改变)
    - [CSS 水平和垂直居中](#css-水平和垂直居中)
    - [uni-app 在安卓中调用前置摄像头自动拍照](#uni-app-在安卓中调用前置摄像头自动拍照)
    - [TS 中 key/value 索引](#ts-中-keyvalue-索引)
    - [Git rebase](#git-rebase)
    - [Git 版本回退](#git-版本回退)
    - [macOS 下 commit 描述问题](#macos-下-commit-描述问题)
    - [eslint 配置全局参数](#eslint-配置全局参数)
    - [小程序 Swiper 禁止滑动](#小程序-swiper-禁止滑动)
    - [prettier 格式化 HTML 时错位](#prettier-格式化-html-时错位)
    - [微信 H5 阴影失效](#微信-h5-阴影失效)
    - [iOS 和安卓视频预览第一帧](#ios-和安卓视频预览第一帧)
    - [禁用user-select移动端副作用](#禁用user-select移动端副作用)

## 编辑器相关（VSCode）

### 实用插件

- Beautify _格式化代码_
- Bracket Pair Colorizer _括号颜色_
- Path Intellisense _路径智能提示_
- Vetur _Vue 提示插件_
- Volar _Vue3 推荐插件_
- ES6 _ES6 语法提示_
- Open in Browser _在浏览器中打开_

[回到顶部](#目录)

### React 开启 JSX 支持

打开`settings`，然后在右上角打开`settings.json`，配置如下：

```json
"emmet.includeLanguages": {
  "javascript": "javascriptreact"
}
```

[回到顶部](#目录)

## NPM(Yarn)相关

### --save 和--save-dev 的区别

`npm install --save`安装的包是运行时的依赖，比如`axios`  
`npm install --save-dev`安装的包仅仅是在开发阶段的依赖，比如`less\sass`等

[回到顶部](#目录)

### npm 在国内加快下载速度

- 可以使用`cnpm`，安装方法`npm install -g cnpm --registry=https://registry.npm.taobao.org`(不推荐，有时候会出问题) [文档](https://developer.aliyun.com/mirror/NPM?from=tnpm)
- 安装`yarn`来代替，直接下载或者在 npm 中下载，推荐直接下载安装 `(推荐)`

```python
# 切换淘宝源
npx nrm use taobao
# 切换回来
npx nrm use npm
```

[回到顶部](#目录)

## 框架（Vue, React 等）相关

### Vue 监听

Vue 在`mounted()`中添加监听事件之后，记得在`destroyed()`中移除监听，特别是监听滚动事件

[回到顶部](#目录)

### Vue 引入 iView 之后使用 Col 标签后 VSCode 会报错

解决方法：在`settings`中搜索`vetur.validation.template`，关闭或者改成 false 之后重启 vscode 即可解决

[回到顶部](#目录)

### 在 VsCode 中识别 webpack 的 alias

在项目根目录下创建`jsconfig.json`，如果使用 ts 则创建`tsconfig.json`，这里只展示 js

```json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "exclude": ["node_modules", "dist"]
}
```

> 问题：只会显示 js 文件和文件夹，其他文件不会显示，暂时没发现解决方法

[回到顶部](#目录)

### 关于 axios 使用 post 传递 application/x-www-form-urlencoded 的问题

使用`qs`库来格式化数据

```javascript
axios({
  method: "post",
  url: "/api/demo",
  data: qs.stringify({ id: 1 }),
});
```

如果你需要传递的数据中包含数组，则需要这样解决

```javascript
axios({
  method: "post",
  url: "/api/demo",
  data: qs.stringify({ id: 1, arr: [1, 2] }, { indices: false }),
});
```

[回到顶部](#目录)

### 关于 Mock.js

- 无法使用`fetch`来进行模拟

[回到顶部](#目录)

### 在 Vue 中使用`Lodash`中的`debounce`

官方文档演示

> \_.debounce(func, [wait=0], [options={}])
> 之后自己在使用过程中发现用不了，搜索了一下别人的代码，然后写成如下

```js
import _ from "lodash";
export default {
  methods: {
    handleClick: _.debounce(() => {
      console.log("防抖成功");
      this.fetchData();
    }, 500),

    fetchData() {
      console.log("fetch");
    },
  },
};
```

上面代码就会报错，原因是`_.debounce`中的`this`指向错误，所以不能使用箭头函数，要改成普通的写法，如果`handleClick`带参数，也可以直接写在`function(args)`中

```js
import _ from "lodash";
export default {
  methods: {
    handleClick: _.debounce(function () {
      console.log("防抖成功");
      this.fetchData();
    }, 500),

    fetchData() {
      console.log("fetch");
    },
  },
};
```

[回到顶部](#目录)

### 后端接口 Long 类型的问题

请求接口中，如果后端返回 Long 类型的参数（比如 ID），前端浏览器会自动截断，需要后端将 Long 转成 String 返回

[回到顶部](#目录)

### Vue 和 TS

- 如果是 Vue-Cli 创建的项目，可以在现有项目下直接`vue add typescript`
- 关于`Mixins`

```js
import { Vue, Component, Mixins } from "vue-property-decorator";
// 这个可以封装成 .ts文件做全局mixins
@Component({})
export class GlobalMixins extends Vue {
  /**
   * 设置提示框
   */
  setSnackbar({ msg = "一条提醒", type = "success", timeout = 2000 }) {
    this.$store.commit("openSnackbar", {
      msg,
      type,
      timeout,
    });
  }
}
// 要这么写
@Component({})
export default class App extends Mixins(GlobalMixins) {}
```

- 在 TS 中定义 prototype,可参考[这个答案](https://stackoverflow.com/questions/55893522/vue-prototype-property-doesnt-work-with-typescript)
- 关于$refs.form.validate()报错(Vuetify)

```typescript
interface VuetifyValidType extends Vue {
  validate(): boolean;
}

export default class {
  $refs!: {
    form: VuetifyValidType;
  };
}
```

[回到顶部](#目录)

### Vue 中通过 CDN 引入高德地图 externals 的问题

在 Vue 中通过 CDN 引入高德地图，script 标签需要放在 head 中，不然会报错`AMap undefined`

[回到顶部](#目录)

### Element UI 如果在项目中需要 CDN 引入

不需要配置 externals，直接通过官方提供的 CDN 引入方式就好，也不需要在`main.js`中调用  
直接就能全局引入

> 后续有什么问题再更新

[回到顶部](#目录)

### Vite 的问题

- Vite 引入 VueRouter4 的问题

```js
// 以下代码是报错代码
import VueRouter from 'vue-router'

// 以下代码是正确代码
import {createRouter, createWebHashHistory} from 'vue-router
// 因为VueRouter4没有export default，所以不能使用第一种方式
```

[回到顶部](#目录)

### Vite2 使用 alias

`vite.config.js`

```js
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";
// 正常来讲path不需要安装，node自带
// 如果Typescript环境下import出现异常，请安装@types/node
import path from "path";

export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
});
```

`tsconfig.json`配置让项目能识别@

```json
{
  "include": [
    "src/**/*.ts",
    "src/**/*.tsx",
    "src/**/*.vue",
    "tests/**/*.ts",
    "tests/**/*.tsx"
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

[回到顶部](#目录)

### 优化 async/await

```js
// try catch嵌套可能用起来不是很方便
// 在返回时直接Promise返回then,catch的值
function upload() {
  return new Promise((resolve, reject) => {
    // 你的代码
  })
    .then((res) => [res, null])
    .catch((err) => [null, err]);
}

async function fn() {
  // 解构赋值获取res和err
  // 如果没有异常，则err是null，反之res是null
  const [res, err] = await upload();

  console.log(res, err);
}
```

[回到顶部](#目录)

### Vue 渲染函数问题

如果需要`render`函数渲染 Element 或者 Vuetify 这些 UI 的组件，则需要在`components`中引入后才能生效，否则会提示组件未注册，一定要单独全局引入或者局部引入，不能直接导入整个 UI 库。

```js
// Vuetify距离，渲染v-btn
export default {
  components: {
    VBtn,
  },
  render(createElemet) {
    return createElement("v-btn", this.$slots.default);
  },
};
```

[回到顶部](#目录)

### Vue3 组合式 api 问题

可直接查看[博客详情](https://mrleidesen.github.io/posts/vue3_issues/)

[回到顶部](#目录)

### React Context 简易状态管理

可直接查看[博客详情](https://mrleidesen.github.io/posts/react_context/)

[回到顶部](#目录)

### Vite jsxInject

我们通过 `Create-React-App` 创建项目时，可以不需要在`jsx`中引入`import React from 'react'`。

当我们通过 `Vite` 创建项目时，需要自己配置`jsxInject`才可以默认注入

```js
// vite.config.js
export default defineConfig({
  // ...
  esbuild: {
    jsxInject: `import React from 'react'`,
  },
});
// ...
```

同时需要修改`tsconfig.json`文件，这样就不会报 error 了

```js
{
  "compilerOptions": {
    // ...
    "jsx": "react-jsx" // 原本是 react
  }
}
```

不过需要注意的是，一旦使用注入，就不能在任何`jsx`或者`tsx`中再次引入`React`，比如

```js
import React from "react";

interface Props {
  children?: React.ReactNode;
}
```

要改成

```js
import { ReactNode } from "react";

interface Props {
  children?: ReactNode;
}
```

否则会重复出现错误，建议在项目创建时就配置好，不然后期再配置修改有点大

[回到顶部](#目录)

### Next.js window is not defined
Next.js 出现 `window is not defined` 的时候，可以通过 `dynamic import` 来动态导入
```js
// 普通导入
import Share from '../components/share'

// 动态导入
import dynamic from 'next/dynamic'
const Share = dynamic(() => import(../components/share), { ssr: false })
```

以上是针对 JS 和 export default 的方式导出

如果你使用的是 TS 以及 export 的方式导出

```ts
// 组件
export const Share: FC<Props> = () => { 
  // ...
}

// 导入
import dynamic from 'next/dynamic'
// 要加上相关类型，不然会报类型错误，也可以使用 any （不推荐）
const Share = dynamic<Props>(() => import(../components/share).then((mod) => mod.Share), { ssr: false })
```

[回到顶部](#目录)

## HTML/CSS/JS/小程序/Git 相关

### movable-view

`movable-view` 这个组件内部无法滚动设置了 `overflow: scroll` 样式的元素（尚未解决）

[回到顶部](#目录)

### 关于点击穿透

例子: 当你点击一个嵌套元素，你点击的是`span`的范围，但你想获取父元素`div`的内容

```html
<div class="test" data-index="outer">
  <span data-index="inner">Click</span>
</div>
<script>
  document.querySelector(".test").onclick = function (e) {
    console.log(e.target.dataset.index);
  };
</script>
```

> 解决方法：内部元素的样式`pointer-events`修改为`none`; 或在内部放置一个位于所有子元素顶层的`div`专门用来点击;

[回到顶部](#目录)

### 阻止事件向上传递

例子: 我点击`inner`这个`div`，不要打印出`'outer'`

```html
<div class="outer">
  <div class="inner"></div>
</div>
<script>
  document.querySelector(".outer").addEventListener("click", (e) => {
    console.log("outer");
  });
  document.querySelector(".inner").addEventListener("click", (e) => {
    console.log("inner");
  });
</script>
```

解决方法：

```js
document.querySelector(".inner").addEventListener("click", (e) => {
  e.stopPropagation();
  console.log("inner");
});
```

[回到顶部](#目录)

### css 来判断元素是否为空

通过伪类`:empty`来判断一个元素内部是否有文字或者是否存在子元素

```css
div:empty {
  width: 100px;
  height: 100px;
  background-color: red;
}
div {
  width: 50px;
  height: 50px;
  background-color: orange;
}
```

[回到顶部](#目录)

### 百度地图自定义标记点图标

从 iconfont 上下载的图标，设置好大小即可显示，但如果图标太大，在 PS 中修改后又无法正常显示尺寸（尚不知问题，但从 iconfont 上设置好大小没问题）

[回到顶部](#目录)

### 关于判断网络状态

- `navigator.onLine`能判断网络是否在线
- `navigator.connection`能获取网络状态信息
- `navigator.connection`可以监听`change`事件

[回到顶部](#目录)

### JS 录制屏幕内容

- 使用`navigator.mediaDevices`来获取 stream 流---[MDN 文档](https://developer.mozilla.org/zh-CN/docs/Web/API/MediaDevices)
- 获取的 stream 流可以使用 MediaRecorder 录制获取 webm 文件---[MDN 文档](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API/Recording_a_media_element)

[回到顶部](#目录)

### 获取内部可滚动元素的滚动

- 通过 offsetTop 来获取内部以及外部的高度，通过相减则是实际内部高度

[回到顶部](#目录)

### 原生 JS 获取当前经纬度

[MDN 官方文档](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition)

```js
const geo = navigator.geolocation;
geo.getCurrentPosition((res) => {
  const crd = res.coords;
  console.log("Your current position is:");
  console.log(`Latitude : ${crd.latitude}`);
  console.log(`Longitude: ${crd.longitude}`);
  console.log(`More or less ${crd.accuracy} meters.`);
});
```

问题：

> 微信 H5 下无法使用，可能移动端 H5 都无法正常使用

[回到顶部](#目录)

### 关于调用百度腾讯等 web 服务

使用`axios`这些会出现跨域问题，需要使用`jsonp`

[回到顶部](#目录)

### 关于 cookies

如果在不同域名下,cookies 会无法设置,简单来说就是: 同域名下 cookies 有效,不同域名下 cookies 无效

[回到顶部](#目录)

### 微信 sdk

前端微信 sdk 的 Config 只需要域名或者 ip 地址能够对上就好

[回到顶部](#目录)

### 监听 DOM 变化

原生 JS 监听 DOM 变化

```js
// 选择需要观察变动的节点
var targetNode = document.getElementById("some-id");

// 观察器的配置（需要观察什么变动）
var config = { attributes: true, childList: true, subtree: true };

// 当观察到变动时执行的回调函数
var callback = function (mutations) {
  for (var mutation of mutations) {
    if (mutation.type == "childList") {
      console.log("A child node has been added or removed.");
    } else if (mutation.type == "attributes") {
      console.log("The " + mutation.attributeName + " attribute was modified.");
    }
  }
};

// 创建一个观察器实例并传入回调函数
var observer = new MutationObserver(callback);

// 以上述配置开始观察目标节点
observer.observe(targetNode, config);

// 之后，可停止观察
observer.disconnect();
```

[参考 MDN 文档](https://developer.mozilla.org/zh-CN/docs/Web/API/MutationObserver)

[回到顶部](#目录)

### 页面平滑滚动

- css
  - `scroll-behavior: smooth`
- js
  - `scrollIntoView({ behavior: "smooth" })`

[回到顶部](#目录)

### IOS 格式化日期出错

Safari 格式化日期格式**yyyy-mm-dd**时会返回 NaN，或者直接报错，需要把-替换成/变成**yyyy/mm/dd**才可正常格式化。

[回到顶部](#目录)

### JS 文字转语音

```js
const voice = speechSynthesis.getVoices()[0];
let speech = new SpeechSynthesisUtterance();
for (const key in voice) {
  speech[key] = voice[key];
}
speech.text = "你好";
speechSynthesis.speak(speech);
```

[回到顶部](#目录)

### Tailwind 在 VSCode 中的智能提示

- 安装插件`Tailwind CSS IntelliSense`
- 在 VSCode 设置中找到`tailwindCSS.includeLanguages`

```json
{
  "plaintext": "vue",
  "javascript": "javascript"
}
```

- 如上设置之后就能 Vue 和 React 都能智能提示了

[回到顶部](#目录)

### 相邻的 button 点击后让 div 发生改变

面试被问到的问题，回答的时候答了`:focus`和兄弟选择器的方式判断，但是没有实际用过，毕竟项目中很少出现

```html
<button class="btn">Click</button>
<div class="listen">Change Color</div>
```

```css
.btn:focus ~ .listen {
  color: red;
}
```

回来复现了一下，是可行的

[回到顶部](#目录)

### CSS 水平和垂直居中

同样也是在面试中被问到的，怪我才疏学浅，平时 flex 一把梭

- Flex

```css
.flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

- Flex Margin Auto
  > 这种方式比较冷门，只能在 flex 的情况下才能用 margin: auto 水平和垂直居中

```html
<div class="container">
  <div class="center"></div>
</div>
<style>
  .container {
    width: 100vw;
    height: 100vh;
    display: flex;
  }
  .center {
    width: 100px;
    heihgt: 100px;
    margin: auto;
    background-color: teal;
  }
</style>
```

- inline-block

```html
<div class="container">
  <div class="center"></div>
</div>
<style>
  .container {
    width: 100vw;
    height: 100vh;
    text-align: center;
    line-height: 100vh;
  }
  .center {
    display: inline-block;
    width: 100px;
    heihgt: 100px;
    background-color: teal;
  }
</style>
```

- position

```html
<div class="container">
  <div class="center"></div>
</div>
<style>
  .container {
    width: 100vw;
    height: 100vh;
    position: relative;
  }
  .center {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 100px;
    height: 100px;
    background-color: teal;
    transform: translateY(-50%) translateX(-50%);
  }
</style>
```

- Grid

```html
<div class="parent">
  <div class="div1"></div>
</div>
<style>
  .parent {
    width: 100vw;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(2, 1fr) 100px repeat(2, 1fr);
    grid-template-rows: repeat(2, 1fr) 100px repeat(2, 1fr);
    grid-column-gap: 0px;
    grid-row-gap: 0px;
  }
  .div1 {
    grid-area: 3 / 3 / 4 / 4;
    background-color: teal;
  }
</style>
```

- padding

```html
<a class="link" href="#">link</a>
<style>
  .link {
    padding: 10px 20px;
    background-color: royalblue;
    color: #fff;
  }
</style>
```

目前想到这几种，其他实在在项目中没怎么用到，自己也没用过，就不放上来误导了。

[回到顶部](#目录)

### uni-app 在安卓中调用前置摄像头自动拍照

可见个人博客的详细内容
[uni-app 安卓调用前置摄像头并自动拍照](https://mrleidesen.github.io/posts/uni_app_using_camera/)

[回到顶部](#目录)

### TS 中 key/value 索引

在 JS 中我们可能会对一个对象这么操作

```js
let obj = {};
obj["a"] = 1;
obj["success"] = function () {};
```

在 TS 中定义类型，我们就要用到`key/value`的方式

```ts
interface ObjectProps {
  [key: string]: any;
}
```

[回到顶部](#目录)

### Git rebase

如果我们需要合并多个`commits`我们需要用到`git rebase`

- 合并前 2 个 commits，或者通过 ID 进行查找

```
git rebase -i HEAD~2
```

- rebase 操作建议在本地提前完成，如果想要合并已提交的远端分支，在本地 rebase 之后强制推送远端

[回到顶部](#目录)

### Git 版本回退

- 返回上一个 commit

```shell
git reset --hard HEAD^
```

- 返回前 n 个 commit

```shell
git reset --hard HEAD~n
```

[回到顶部](#目录)

### macOS 下 commit 描述问题

macOS 中需要严格注意大小写，否则会出现不知名的问题

[回到顶部](#目录)

### eslint 配置全局参数

假如我们正在一个微信的项目中使用 `wx` 这个变量，eslint 会提示我们没有定义，那么我们需要在 `.eslintrc.js` 中配置全局变量

```js
module.exports = {
  globals: {
    wx: "readonly",
  },
};
```

[回到顶部](#目录)

### 小程序 Swiper 禁止滑动

有时候小程序项目中会需要禁止 Swiper 的滑动，有两种方法

- 禁止滑动的时候直接用 view 代替展示
- 使用 `catchtouchmove`

```html
<swiper-item
  catchtouchmove="{{needCatch ? 'handleCatchTouchMove' : ''}}"
></swiper-item>
```

```js
data: {
  needCatch: true
},

methods: {
  handleCatchTouchMove() {
    return
  }
}
```

[回到顶部](#目录)

### prettier 格式化 HTML 时错位

有时候在使用 Prettier 格式化 HTML 的时候，会出现 `>` 错位，比如：

```html
<nav-link url="/pages/user" class="nickname">{{ .nick_name }}</nav-link>
<follow-button />
```

这时我们需要在 Prettier 中设置 `htmlWhitespaceSensitivity` 为 `ignore` 就可以了。

如果你有 `.prettierrc.js` 这个文件就在这里设置，如果是 VSCode 插件则在插件中设置

[参考 StackOverflow](https://stackoverflow.com/questions/53209320/vscode-prettier-formats-html-in-an-odd-way-greater-than-symbol-on-next-line)

[回到顶部](#目录)

### 微信 H5 阴影失效

因为微信自带的浏览器兼容性很差，问题很多，有时候在写 `box-shadow` 的时候会发现在安卓下失效了，可以试试把 **十六进制** 的颜色改成 `rgb/rgba` 形式的

[回到顶部](#目录)

### iOS 和安卓视频预览第一帧

当我们使用 `video` 标签且没有 `poster` 的时候想要展示视频的第一帧当作封面图，可以通过以下写法

```html
<video src="https://xxx.mp4#t=0.01" preload="metadata" />
```

- `src` 链接后加上 `#t=0.01`
- `preload` 设置为 `metadata`

[回到顶部](#目录)

### 禁用user-select移动端副作用

我们在 Web 开发时大多会使用 `user-select: none` 来禁止用户对文本进行选中。

但是在移动端，会因为 `contextmenu` 而出现副作用：
> 禁用了 `user-select` 后长按会选中下一个未禁用的位置

搜了网上很多的答案
1. [Disabling the context menu on long taps on Android](https://stackoverflow.com/questions/3413683/disabling-the-context-menu-on-long-taps-on-android)
2. [CSS: -webkit-touch-callout alternatives for android](https://stackoverflow.com/questions/16011159/css-webkit-touch-callout-alternatives-for-android)
3. [-webkit-touch-callout](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-touch-callout)

在安卓下通过 `oncontextmenu = () => false` 可以解决问题

但是 iOS 下无法通过 `-webkit-touch-callout: none` 来解决问题

但是可以通过 `ontouchstart = () => false` 来禁用，但是副作用是这个范围内无法再滑动等操作

iOS 下还需研究其他方案，暂时搁置

[回到顶部](#目录)
