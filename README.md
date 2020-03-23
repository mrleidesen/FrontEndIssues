# 前端技术一些踩坑记录（缓慢记录中...）

## 框架（Vue, React等）相关
### Vue监听
Vue在`mounted()`中添加监听事件之后，记得在`destroyed()`中移除监听，特别是监听滚动事件

### Vue引入iView之后使用Col标签后VSCode会报错
解决方法：在`settings`中搜索`vetur.validation.template`，关闭或者改成false之后重启vscode即可解决

### 在VsCode中识别webpack的alias
在项目根目录下创建`jsconfig.json`，如果使用ts则创建`tsconfig.json`，这里只展示js
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"],
      "@views/*": ["./src/views/*"]
    }
  },
  "include": ["./src/**/*"]
}
```
> 问题：只会显示js文件和文件夹，其他文件不会显示，暂时没发现解决方法

## 小程序相关
### 微信小程序bindtap
以下情况点击`area`可能并不会获取到该元素，小程序判定点在哪个元素上，触发的就是哪个。比如：你想要点击整个`area`元素来获取data-index的值，但你点击在了子元素`area-item`上，那么你的函数返回的就是该元素的内容，不会返回`area`的内容
```html
<view
  class="area"
  data-index="1"
  bindtap="handleTap"
>
  <view class="area-item">Some Content</view>
  <view class="area-item">Some Content</view>
  <view class="area-item">Some Content</view>
</view>
```
>解决方法: 内部放一个透明但是覆盖了整个大小的子元素，确保点击在它上面（如果有更好的解决方法，欢迎提供！暂时只想到这个）
```html
<view
  class="area"
>
  <view
    data-index="1"
    bindtap="handleTap"
    style="position: relative;z-index: 1;width: 100%;height:100%;"
  ></view>
  <view class="area-item">Some Content</view>
  <view class="area-item">Some Content</view>
  <view class="area-item">Some Content</view>
</view>
```

### movable-view
`movable-view` 这个组件内部无法滚动设置了 `overflow: scroll` 样式的元素（尚未解决）

## ios、安卓相关
* ios调用接口，可能会因为域名不同出现问题，即使做过跨域