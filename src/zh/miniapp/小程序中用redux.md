### 在小程序中使用redux

##### 下包 redux;redux-thunk;wechat-weapp-redux
在程序中设置支持npm文件

1.新建一个目录libs将以上几个包的list下的文件复制进去。

2.新建store目录 写法与react中一样

3.app.js中 引入Provider和store

```
import {Provider} from "./libs/wechat-weapp-redux.min.js"
import store from "./store/index.js"

App(Provider(store)(原app.js中的代码))
```

4.在页面的js文件中


```
//用法与在react中一样
import {connect} from "../../libs/wechat-weapp-redux.min.js"
import {bindActionCreators} from "../../libs/redux.min.js"
import listAction from "../../store/list.action.js"

Page(connect(
  state => state,
  dispatch => bindActionCreators(actios, dispatch)


)(原此js中的代码))

```


