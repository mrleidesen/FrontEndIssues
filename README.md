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

## 小程序相关以及HTML

### movable-view
`movable-view` 这个组件内部无法滚动设置了 `overflow: scroll` 样式的元素（尚未解决）

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

### 百度地图自定义标记点图标
从iconfont上下载的图标，设置好大小即可显示，但如果图标太大，在PS中修改后又无法正常显示尺寸（尚不知问题，但从iconfont上设置好大小没问题）

## ios、安卓相关
* ios调用接口，可能会因为域名不同出现问题，即使做过跨域