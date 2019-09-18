### 楼层

#### tab切换 
框架/小程序配置/全局配置（向下拉）-->tabBar

在app.json里面设置

```
 "tabBar": {
    //字体的颜色
    "color": "#ccc",
    //选择状态的字体的颜色
    "selectedColor": "tomato",
    //nav导航的位置 只能是top和bottom
    "position": "bottom",
    "list": [
      {//text 为tab切换的按钮的内容
        "text": "首页",
        //选中状态时icon图标的路径
        "selectedIconPath": "./static/index-active.png",
         //未选中状态时icon图标的路径
        "iconPath": "./static/index.png",
        //路由页面的地址
        "pagePath": "pages/home/home"
      }
    ]
  }
```
#### scroll

##### 使用：组件/视图容器/scroll-view
###### 注意：包裹的父元素必须有高度撑开 需要给scroll-view一个固定高度

```
<scroll-view 
  class="m-scroll-view" 
  scroll-y 
  <!--scroll-into-view的值currentKey为要滚动到的子元素的id（不能以数字开头）-->
  scroll-into-view="{{currentKey}}" 
  scroll-with-animation 
  bindscroll="handleScroll">
  <!-- 类名js-list-item用于获取所有外层元素距离顶部的距离 -->
    <view wx:for="{{dataList}}"
    <!--子元素的id为每一项的key值-->
    wx:key="{{index}}" id="{{item.key}}" class="js-list-item">
      <text class="m-scroll-item-title">{{item.key}}</text>
      <view wx:for="{{item.row}}" wx:key="{{index}}">
        <text class="m-scroll-item-text">{{item.name}}</text>
      </view>
    </view>
  </scroll-view>
  
  <!--点击右面导航 动态改变currentKey的值-->
```



