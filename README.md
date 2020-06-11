# 前端技术一些踩坑记录（缓慢记录中...）

## 更新日志
* `[2020-6-11]` 更新微信js-sdk配置相关
* `[2020-6-02]` 更新地图调用
* `[2020-5-28]` 更新cookies
* `[2020-5-14]` 更新JS获取经纬度
* `[2020-5-13]` 更新目录
* `[2020-5-12]` 更新lodash

## 目录
* [编辑器相关（VSCode）](#编辑器相关VSCode)
  * [实用插件](#实用插件)
  * [React开启JSX支持](#React开启JSX支持)
* [NPM(Yarn)相关](#NPMYarn相关)
  * [--save和--save-dev的区别](#--save和--save-dev的区别)
  * [npm在国内加快下载速度](#npm在国内加快下载速度)
* [框架（Vue, React等）相关](#框架Vue-React等相关)
  * [Vue监听](#Vue监听)
  * [Vue引入iView之后使用Col标签后VSCode会报错](#Vue引入iView之后使用Col标签后VSCode会报错)
  * [在VsCode中识别webpack的alias](#在VsCode中识别webpack的alias)
  * [关于axios使用post传递](#关于axios使用post传递application-x-www-form-urlencoded的问题)
  * [关于Mock.js](#关于Mockjs)
  * [在Vue中使用Lodash中的debounce](#在Vue中使用Lodash中的debounce)
* [小程序相关以及HTML](#小程序相关以及HTML)
  * [movable-view](#movable-view)
  * [关于点击穿透](#关于点击穿透)
  * [css来判断元素是否为空](#css来判断元素是否为空)
  * [百度地图自定义标记点图标](#百度地图自定义标记点图标)
  * [关于判断网络状态](#关于判断网络状态)
  * [JS录制屏幕内容](#JS录制屏幕内容)
  * [获取内部可滚动元素的滚动](#获取内部可滚动元素的滚动)
  * [原生JS获取当前经纬度](#原生JS获取当前经纬度)
  * [关于调用百度腾讯等web服务](#关于调用百度腾讯等web服务)
  * [关于cookies](#关于cookies)
  * [微信sdk](#微信sdk)
* [ios、安卓相关](#ios安卓相关)

## 编辑器相关（VSCode）
### 实用插件
* Beautify *格式化代码*
* Bracket Pair Colorizer *括号颜色*
* Path Intellisense *路径智能提示*
* Vetur *Vue提示插件*
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

## 小程序相关以及HTML

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

## ios、安卓相关
* ios调用接口，可能会因为域名不同出现问题，即使做过跨域

[回到顶部](#目录)
