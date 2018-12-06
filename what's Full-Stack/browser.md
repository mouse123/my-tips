## 浏览器是怎么绘制一帧动画的
- 在默认状态下，我们点击左上角的圆记录事件，几秒后我们可以点击 Performance 中的 Stop 产生分析数据。在概览面板中我们看到在渡过最初的几百毫秒后，CPU 面积图中各种事件占比按固定周期变化，我们点取其中一小段观察，在主线程图中可看到一段一段类似事件组。观察几组事件后，我们发现，这些事件组的组成都是：10 个 Recalculate Style + Layout 的循环 -> Update Layer Tree -> Paint -> Composite Layers。我们知道，Composite Layers 事件之后，意味着人眼可见新的页面图层，也就是说这样一组事件过后，一帧画面绘制在眼前。

## 浏览器渲染过程
![avatar](https://raw.githubusercontent.com/mouse123/my-tips/master/image/v2-a9b24264340f0402ece0ec6c9989d889_hd.jpg)
- 当渲染首屏时，浏览器分别解析 HTML 与 CSS 文件，生成文档对象模型（DOM）与 样式表对象模型（CSSOM）；合并 DOM 与 CSSOM 成为渲染树（Render Tree）；计算样式（ Style）；计算每个节点在屏幕中的精确位置与大小（Layout）；将渲染树按照上一步计算出的位置绘制到图层上（Paint）；渲染引擎合成所有图层最终使人眼可见（Composite Layers）。
如果改变页面布局，则是先通过 JS 更新 DOM 再经历计算样式到合成图像这个过程。如果仅仅是非几何变化（颜色、visibility、transform），则可以跳过布局步骤。