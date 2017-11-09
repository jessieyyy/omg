### v1.0.0
* 添加矩形，线的绘制
* 已on的形式给对象添加事件
* 全局拖拽位移和缩放
* 对象的拖拽位移

### v1.1.0
* 优化事件触发器，新增`dragin` `dragout` `drop`事件， 用于对象之间的交互， 模拟原生的drag and drop。
* 新增对象之间的**两两交互**，和原生drag，drop类似，不过简化为了dragin, dragout, drop， 这三个事件可以完美解决两两交互, **注意**这三个属性是作为contaner的一方添加。
* 结合**外部drag，drop**，和页面内交互。LCL作为一个全局变量，包含了一切需要的数据，何以直接结合外部drag，drop操作objects数组，然后重绘。
* 优化事件触发的顺序(order)， 支持改变对象绘制的顺序。
* 对象添加属性链式调用。XX.on(..).on(..).config(...).drag(...)...
* 优化点在形状内的判断，添加形状旋转后的判断...

#### v1.1.1
* 添加scripts文件，新增release脚本，自动化更新版本，提交代码。
* 添加eslint， 和pre-commit脚本。

### v1.2.0
* config添加fixed, bg 。 `fixed:ture` --> globalTranslate对当前对象无效
* 暂时移除rotate
* 添加图片加载器
* 添加 drag,dragend事件， 用于对象在拖拽和拖拽结束的时候触发，drop事件的callback添加item回调， `on('drop', function(item) {console.log(item)})` item是被拖拽的对象。
* 添加图形 arc,text,image..
* 优化Event

### v1.3.0
* 由于之前的设定， 只有一个全局变量LCL，而所有的信息，包括全局位置信息等都储存在着一个全局变量之中，导致无法绘制多个canvas，他们会共享一个全局变量。所以改版，支持多canvas绘制。

#### v1.3.1
* 绘制图形增添zindex, 默认为0, 可以为负数。
* addChild可以直接添加数组。

#### v1.3.4
*  新增绘制坐标系(coord.js)，只需提供x，y轴数据，即可自己选取合适的区间，绘制坐标系。

#### v1.3.5
*  增加颜色函数，包括十六进制颜色转rgb颜色， rgb颜色转hsl颜色， 仿less的lighten和darken函数...

#### v3.0.0
*  重构代码。

## ToDo

* 给时间触发添加顺序(index) (Done)
* 全局拖拽位移和缩放 [由于坐标计算出现了问题，暂时放弃缩放] -- (Done)
* 对象之间的两两交互，模拟drag, drop事件, 新增dragin, dragout, drop事件。(Done)
* 外部拖拽与页面内对象交互，像原生的drag，drop. (Done) -- 见demo源代码
* 浏览器兼容性测试
* 添加基本，常见的图形的绘制（In progress）
* 增加group组件，几个图形可以放到一个group中，作为一个整体来添加事件和操作。