# 前端技术一些踩坑记录（缓慢记录中...）

## 更新日志
* `[2021-07-23]` 更新[prettier格式化HTML时错位](#prettier格式化html时错位)
* `[2021-07-22]` 更新[小程序 Swiper 禁止滑动](#小程序-swiper-禁止滑动)
* `[2021-07-11]` 更新[Vite jsxInject](#vite-jsxinject)
* `[2021-07-09]` 更新[eslint 配置全局参数](#eslint-配置全局参数)
* `[2021-06-16]` 更新[React Context简易状态管理](#react-context简易状态管理)
* `[2021-06-08]` 更新[TS中key/value索引](#ts中keyvalue索引)
* `[2021-06-02]` 更新[Vue3组合式api问题](#vue3组合式api问题)
* `[2021-04-29]` 更新[Vue渲染函数问题](#vue渲染函数问题)
* `[2021-04-19]` 更新[uni-app在安卓中调用前置摄像头自动拍照](#uni-app在安卓中调用前置摄像头自动拍照)
* `[2021-04-16]` 更新[相邻的button点击后让div发生改变](#相邻的button点击后让div发生改变)/[CSS水平和垂直居中](#css水平和垂直居中)
* `[2021-04-07]` 更新[优化async/await](#优化asyncawait)
* `[2021-02-25]` [Vite的问题](#vite的问题)
* `[2021-02-23]` 更新[Element UI如果在项目中需要CDN引入](#element-ui如果在项目中需要cdn引入)
* `[2021-01-22]` 更新[Tailwind在VSCode中的智能提示](#tailwind在vscode中的智能提示)
* `[2020-12-25]` 更新[Vue中通过CDN引入高德地图externals的问题](#vue中通过cdn引入高德地图externals的问题)
* `[2020-12-07]` 更新[js文字转语音](#js文字转语音)
* `[2020-12-04]` 更新[IOS格式化日期出错](#ios格式化日期出错)
* `[2020-9-07]` 更新[页面平滑滚动](#页面平滑滚动)
* `[2020-7-22]` 更新[Vue和TS](#Vue和TS)

## 目录
- [前端技术一些踩坑记录（缓慢记录中...）](#前端技术一些踩坑记录缓慢记录中)
  - [更新日志](#更新日志)
  - [目录](#目录)
  - [编辑器相关（VSCode）](#编辑器相关vscode)
    - [实用插件](#实用插件)
    - [React开启JSX支持](#react开启jsx支持)
  - [NPM(Yarn)相关](#npmyarn相关)
    - [--save和--save-dev的区别](#--save和--save-dev的区别)
    - [npm在国内加快下载速度](#npm在国内加快下载速度)
  - [框架（Vue, React等）相关](#框架vue-react等相关)
    - [Vue监听](#vue监听)
    - [Vue引入iView之后使用Col标签后VSCode会报错](#vue引入iview之后使用col标签后vscode会报错)
    - [在VsCode中识别webpack的alias](#在vscode中识别webpack的alias)
    - [关于axios使用post传递application/x-www-form-urlencoded的问题](#关于axios使用post传递applicationx-www-form-urlencoded的问题)
    - [关于Mock.js](#关于mockjs)
    - [在Vue中使用`Lodash`中的`debounce`](#在vue中使用lodash中的debounce)
    - [后端接口Long类型的问题](#后端接口long类型的问题)
    - [Vue和TS](#vue和ts)
    - [Vue中通过CDN引入高德地图externals的问题](#vue中通过cdn引入高德地图externals的问题)
    - [Element UI如果在项目中需要CDN引入](#element-ui如果在项目中需要cdn引入)
    - [Vite的问题](#vite的问题)
    - [Vite2使用alias](#vite2使用alias)
    - [优化async/await](#优化asyncawait)
    - [Vue渲染函数问题](#vue渲染函数问题)
    - [Vue3组合式api问题](#vue3组合式api问题)
    - [React Context简易状态管理](#react-context简易状态管理)
    - [Vite jsxInject](#vite-jsxinject)
  - [HTML/CSS/JS/小程序/Git相关](#htmlcssjs小程序git相关)
    - [movable-view](#movable-view)
    - [关于点击穿透](#关于点击穿透)
    - [阻止事件向上传递](#阻止事件向上传递)
    - [css来判断元素是否为空](#css来判断元素是否为空)
    - [百度地图自定义标记点图标](#百度地图自定义标记点图标)
    - [关于判断网络状态](#关于判断网络状态)
    - [JS录制屏幕内容](#js录制屏幕内容)
    - [获取内部可滚动元素的滚动](#获取内部可滚动元素的滚动)
    - [原生JS获取当前经纬度](#原生js获取当前经纬度)
    - [关于调用百度腾讯等web服务](#关于调用百度腾讯等web服务)
    - [关于cookies](#关于cookies)
    - [微信sdk](#微信sdk)
    - [监听DOM变化](#监听dom变化)
    - [页面平滑滚动](#页面平滑滚动)
    - [IOS格式化日期出错](#ios格式化日期出错)
    - [JS文字转语音](#js文字转语音)
    - [Tailwind在VSCode中的智能提示](#tailwind在vscode中的智能提示)
    - [相邻的button点击后让div发生改变](#相邻的button点击后让div发生改变)
    - [CSS水平和垂直居中](#css水平和垂直居中)
    - [uni-app在安卓中调用前置摄像头自动拍照](#uni-app在安卓中调用前置摄像头自动拍照)
    - [TS中key/value索引](#ts中keyvalue索引)
    - [Git rebase](#git-rebase)
    - [Git 版本回退](#git-版本回退)
    - [macOS下commit描述问题](#macos下commit描述问题)
    - [eslint 配置全局参数](#eslint-配置全局参数)
    - [小程序 Swiper 禁止滑动](#小程序-swiper-禁止滑动)
    - [prettier格式化HTML时错位](#prettier格式化html时错位)

## 编辑器相关（VSCode）
### 实用插件
* Beautify *格式化代码*
* Bracket Pair Colorizer *括号颜色*
* Path Intellisense *路径智能提示*
* Vetur *Vue提示插件*
* Volar *Vue3推荐插件*
* ES6 *ES6语法提示*
* Open in Browser *在浏览器中打开*

[回到顶部](#目录)

### React开启JSX支持
打开`settings`，然后在右上角打开`settings.json`，配置如下：
```json
"emmet.includeLanguages": {
  "javascript": "javascriptreact"
}
```

[回到顶部](#目录)
## NPM(Yarn)相关
### --save和--save-dev的区别
`npm install --save`安装的包是运行时的依赖，比如`axios`  
`npm install --save-dev`安装的包仅仅是在开发阶段的依赖，比如`less\sass`等

[回到顶部](#目录)
### npm在国内加快下载速度
* 可以使用`cnpm`，安装方法`npm install -g cnpm --registry=https://registry.npm.taobao.org`(不推荐，有时候会出问题) [文档](https://developer.aliyun.com/mirror/NPM?from=tnpm)
* 安装`yarn`来代替，直接下载或者在npm中下载，推荐直接下载安装 `(推荐)`
```python
# 切换淘宝源
npx nrm use taobao
# 切换回来
npx nrm use npm
```

[回到顶部](#目录)

## 框架（Vue, React等）相关
### Vue监听
Vue在`mounted()`中添加监听事件之后，记得在`destroyed()`中移除监听，特别是监听滚动事件

[回到顶部](#目录)

### Vue引入iView之后使用Col标签后VSCode会报错
解决方法：在`settings`中搜索`vetur.validation.template`，关闭或者改成false之后重启vscode即可解决

[回到顶部](#目录)

### 在VsCode中识别webpack的alias
在项目根目录下创建`jsconfig.json`，如果使用ts则创建`tsconfig.json`，这里只展示js
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
> 问题：只会显示js文件和文件夹，其他文件不会显示，暂时没发现解决方法

[回到顶部](#目录)

### 关于axios使用post传递application/x-www-form-urlencoded的问题
使用`qs`库来格式化数据
```javascript
axios({
  method: 'post',
  url: '/api/demo',
  data: qs.stringify({ id: 1 })
})
```
如果你需要传递的数据中包含数组，则需要这样解决
```javascript
axios({
  method: 'post',
  url: '/api/demo',
  data: qs.stringify({ id: 1, arr: [1, 2] }, { indices: false })
})
```

[回到顶部](#目录)

### 关于Mock.js
* 无法使用`fetch`来进行模拟

[回到顶部](#目录)

### 在Vue中使用`Lodash`中的`debounce`
官方文档演示
> _.debounce(func, [wait=0], [options={}])
之后自己在使用过程中发现用不了，搜索了一下别人的代码，然后写成如下
```js
import _ from 'lodash'
export default {
  methods: {
    handleClick: _.debounce(() => {
      console.log('防抖成功')
      this.fetchData()
    }, 500),

    fetchData() {
      console.log('fetch')
    },
  }
}
```
上面代码就会报错，原因是`_.debounce`中的`this`指向错误，所以不能使用箭头函数，要改成普通的写法，如果`handleClick`带参数，也可以直接写在`function(args)`中
```js
import _ from 'lodash'
export default {
  methods: {
    handleClick: _.debounce(function() {
      console.log('防抖成功')
      this.fetchData()
    }, 500),

    fetchData() {
      console.log('fetch')
    },
  }
}
```

[回到顶部](#目录)

### 后端接口Long类型的问题
请求接口中，如果后端返回Long类型的参数（比如ID），前端浏览器会自动截断，需要后端将Long转成String返回

[回到顶部](#目录)

### Vue和TS
* 如果是Vue-Cli创建的项目，可以在现有项目下直接`vue add typescript`
* 关于`Mixins`
```js
import { Vue, Component, Mixins } from 'vue-property-decorator'
// 这个可以封装成 .ts文件做全局mixins
@Component({})
export class GlobalMixins extends Vue {
  /**
   * 设置提示框
   */
  setSnackbar({
    msg = "一条提醒",
    type = "success",
    timeout = 2000
  }) {
    this.$store.commit('openSnackbar', {
      msg,
      type,
      timeout
    })
  }
}
// 要这么写
@Component({})
export default class App extends Mixins(GlobalMixins) {}
```
* 在TS中定义prototype,可参考[这个答案](https://stackoverflow.com/questions/55893522/vue-prototype-property-doesnt-work-with-typescript)
* 关于$refs.form.validate()报错(Vuetify)
```typescript
interface VuetifyValidType extends Vue {
  validate(): boolean
}

export default class {
  $refs!: {
    form: VuetifyValidType
  }
}
```

[回到顶部](#目录)

### Vue中通过CDN引入高德地图externals的问题
在Vue中通过CDN引入高德地图，script标签需要放在head中，不然会报错`AMap undefined`

[回到顶部](#目录)

### Element UI如果在项目中需要CDN引入
不需要配置externals，直接通过官方提供的CDN引入方式就好，也不需要在`main.js`中调用  
直接就能全局引入 
> 后续有什么问题再更新

[回到顶部](#目录)

### Vite的问题
* Vite引入VueRouter4的问题
```js
// 以下代码是报错代码
import VueRouter from 'vue-router'

// 以下代码是正确代码
import {createRouter, createWebHashHistory} from 'vue-router
// 因为VueRouter4没有export default，所以不能使用第一种方式
```

[回到顶部](#目录)

### Vite2使用alias
`vite.config.js`
```js
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
// 正常来讲path不需要安装，node自带
// 如果Typescript环境下import出现异常，请安装@types/node
import path from 'path'

export default defineConfig({
  plugins: [vue()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, './src')
    }
  }
})
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

### 优化async/await
```js
// try catch嵌套可能用起来不是很方便
// 在返回时直接Promise返回then,catch的值
function upload() {
  return new Promise((resolve, reject) => {
    // 你的代码
  }).then(res => [res, null]).catch(err => [null, err])
}

async function fn() {
  // 解构赋值获取res和err
  // 如果没有异常，则err是null，反之res是null
  const [res, err] = await upload()

  console.log(res, err)
}
```

[回到顶部](#目录)

### Vue渲染函数问题
如果需要`render`函数渲染Element或者Vuetify这些UI的组件，则需要在`components`中引入后才能生效，否则会提示组件未注册，一定要单独全局引入或者局部引入，不能直接导入整个UI库。
```js
// Vuetify距离，渲染v-btn
export default {
  components: {
    VBtn
  },
  render(createElemet) {
    return createElement(
      'v-btn',
      this.$slots.default
    )
  }
}
```
[回到顶部](#目录)

### Vue3组合式api问题
可直接查看[博客详情](https://mrleidesen.github.io/posts/vue3_issues/)

[回到顶部](#目录)

### React Context简易状态管理
可直接查看[博客详情](https://mrleidesen.github.io/posts/react_context/)

[回到顶部](#目录)

### Vite jsxInject
我们通过 `Create-React-App` 创建项目时，可以不需要在`jsx`中引入`import React from 'react'`。

当我们通过  `Vite` 创建项目时，需要自己配置`jsxInject`才可以默认注入

```js
// vite.config.js
export default defineConfig({
  // ...
  esbuild: {
    jsxInject: `import React from 'react'`,
  },
})
// ...
```

同时需要修改`tsconfig.json`文件，这样就不会报error了
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
import React from 'react'

interface Props {
  children?: React.ReactNode
}
```

要改成
```js
import { ReactNode } from 'react'

interface Props {
  children?: ReactNode
}
```

否则会重复出现错误，建议在项目创建时就配置好，不然后期再配置修改有点大

[回到顶部](#目录)

## HTML/CSS/JS/小程序/Git相关

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
  document.querySelector('.test').onclick = function (e) {
    console.log(e.target.dataset.index);
  }
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
  document.querySelector('.outer').addEventListener('click', e => {
    console.log('outer')
  })
  document.querySelector('.inner').addEventListener('click', e => {
    console.log('inner')
  })
</script>
```
解决方法：
```js
document.querySelector('.inner').addEventListener('click', e => {
  e.stopPropagation()
  console.log('inner')
})
```

[回到顶部](#目录)

### css来判断元素是否为空
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
从iconfont上下载的图标，设置好大小即可显示，但如果图标太大，在PS中修改后又无法正常显示尺寸（尚不知问题，但从iconfont上设置好大小没问题）

[回到顶部](#目录)

### 关于判断网络状态
* `navigator.onLine`能判断网络是否在线
* `navigator.connection`能获取网络状态信息
* `navigator.connection`可以监听`change`事件

[回到顶部](#目录)

### JS录制屏幕内容
* 使用`navigator.mediaDevices`来获取stream流---[MDN文档](https://developer.mozilla.org/zh-CN/docs/Web/API/MediaDevices) 
* 获取的stream流可以使用MediaRecorder录制获取webm文件---[MDN文档](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API/Recording_a_media_element)

[回到顶部](#目录)

### 获取内部可滚动元素的滚动
* 通过offsetTop来获取内部以及外部的高度，通过相减则是实际内部高度

[回到顶部](#目录)

### 原生JS获取当前经纬度
[MDN官方文档](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/getCurrentPosition)
```js
const geo = navigator.geolocation
geo.getCurrentPosition((res) => {
  const crd = res.coords
  console.log('Your current position is:');
  console.log(`Latitude : ${crd.latitude}`);
  console.log(`Longitude: ${crd.longitude}`);
  console.log(`More or less ${crd.accuracy} meters.`);
})
```
问题：
> 微信H5下无法使用，可能移动端H5都无法正常使用

[回到顶部](#目录)

### 关于调用百度腾讯等web服务
使用`axios`这些会出现跨域问题，需要使用`jsonp`

[回到顶部](#目录)

### 关于cookies
如果在不同域名下,cookies会无法设置,简单来说就是: 同域名下cookies有效,不同域名下cookies无效

[回到顶部](#目录)

### 微信sdk
前端微信sdk的Config只需要域名或者ip地址能够对上就好

[回到顶部](#目录)

### 监听DOM变化
原生JS监听DOM变化
```js
// 选择需要观察变动的节点
var targetNode = document.getElementById('some-id');

// 观察器的配置（需要观察什么变动）
var config = { attributes: true, childList: true, subtree: true };

// 当观察到变动时执行的回调函数
var callback = function(mutations) {
    for(var mutation of mutations) {
        if (mutation.type == 'childList') {
            console.log('A child node has been added or removed.');
        }
        else if (mutation.type == 'attributes') {
            console.log('The ' + mutation.attributeName + ' attribute was modified.');
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
[参考MDN文档](https://developer.mozilla.org/zh-CN/docs/Web/API/MutationObserver)

[回到顶部](#目录)

### 页面平滑滚动
- css
  - `scroll-behavior: smooth`
- js
  - `scrollIntoView({ behavior: "smooth" })`

[回到顶部](#目录)

### IOS格式化日期出错
Safari格式化日期格式**yyyy-mm-dd**时会返回NaN，或者直接报错，需要把-替换成/变成**yyyy/mm/dd**才可正常格式化。

[回到顶部](#目录)

### JS文字转语音
```js
const voice = speechSynthesis.getVoices()[0];
let speech = new SpeechSynthesisUtterance();
for (const key in voice) {
  speech[key] = voice[key];
}
speech.text = '你好';
speechSynthesis.speak(speech);
```

[回到顶部](#目录)

### Tailwind在VSCode中的智能提示
* 安装插件`Tailwind CSS IntelliSense`
* 在VSCode设置中找到`tailwindCSS.includeLanguages`
```json
{
  "plaintext": "vue",
  "javascript": "javascript"
}
```
* 如上设置之后就能Vue和React都能智能提示了

[回到顶部](#目录)

### 相邻的button点击后让div发生改变
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

### CSS水平和垂直居中
同样也是在面试中被问到的，怪我才疏学浅，平时flex一把梭
* Flex
```css
.flex {
  display: flex;
  justify-content: center;
  align-items: center;
}
```
* Flex Margin Auto
> 这种方式比较冷门，只能在flex的情况下才能用margin: auto水平和垂直居中
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
* inline-block
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
* position
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
* Grid
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
目前想到这五种，其他实在在项目中没怎么用到，自己也没用过，就不放上来误导了。

[回到顶部](#目录)

### uni-app在安卓中调用前置摄像头自动拍照
可见个人博客的详细内容
[uni-app安卓调用前置摄像头并自动拍照](https://mrleidesen.github.io/posts/uni_app_using_camera/)

[回到顶部](#目录)

### TS中key/value索引
在JS中我们可能会对一个对象这么操作
```js
let obj = {}
obj["a"] = 1
obj["success"] = function() {}
```
在TS中定义类型，我们就要用到`key/value`的方式
```ts
interface ObjectProps {
  [key: string]: any
}
```

[回到顶部](#目录)

### Git rebase
如果我们需要合并多个`commits`我们需要用到`git rebase`

* 合并前2个commits，或者通过ID进行查找
```
git rebase -i HEAD~2
```
* rebase操作建议在本地提前完成，如果想要合并已提交的远端分支，在本地rebase之后强制推送远端

[回到顶部](#目录)

### Git 版本回退
* 返回上一个 commit
```shell
git reset --hard HEAD^
```
* 返回前 n 个 commit
```shell
git reset --hard HEAD~n
```


[回到顶部](#目录)

### macOS下commit描述问题
macOS中需要严格注意大小写，否则会出现不知名的问题

[回到顶部](#目录)

### eslint 配置全局参数
假如我们正在一个微信的项目中使用 `wx` 这个变量，eslint 会提示我们没有定义，那么我们需要在 `.eslintrc.js` 中配置全局变量

```js
module.exports = {
  globals: {
    wx: 'readonly'
  }
}
```

[回到顶部](#目录)

### 小程序 Swiper 禁止滑动
有时候小程序项目中会需要禁止 Swiper 的滑动，有两种方法

* 禁止滑动的时候直接用 view 代替展示
* 使用 `catchtouchmove`
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

### prettier格式化HTML时错位
有时候在使用 Prettier 格式化 HTML 的时候，会出现 `>` 错位，比如：

```html
<nav-link
  url="/pages/user"
  class="nickname"
  >{{ .nick_name }}</nav-link
>
<follow-button />
```

这时我们需要在 Prettier 中设置 `htmlWhitespaceSensitivity` 为 `ignore` 就可以了。

如果你有 `.prettierrc.js` 这个文件就在这里设置，如果是 VSCode 插件则在插件中设置 

[参考 StackOverflow](https://stackoverflow.com/questions/53209320/vscode-prettier-formats-html-in-an-odd-way-greater-than-symbol-on-next-line)

[回到顶部](#目录)