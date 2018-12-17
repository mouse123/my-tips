## 重排与重绘
![avatar](https://raw.githubusercontent.com/mouse123/my-tips/master/image/reflow%E3%80%81repaint.jpg)
- 简而言之，重排（reflow）和重绘（repaint）都是改变页面样式的步骤。重排步骤包括 Recalculate Style、Layout、Update Layer Tree 等渲染类型事件，重绘步骤包括 Paint 和 Composite Layers 这些绘制类型事件。重排之后必然会造成重绘，而造成重绘的操作不一定会造成重排。下面列出了一些造成重排或重绘的常见操作，更多操作可以参阅 [csstriggers](https://link.zhihu.com/?target=https%3A//csstriggers.com/)
## SVG自适应
- preserveAspectRatio
- xMinYMin
强制统一缩放
视窗X轴的最小值对齐元素viewBox的<min-x>。
视窗Y轴的最小值对齐元素viewBox的<min-y>。
把这个类比为backrgound-position: 0% 0%;。
- xMinYMid
强制统一缩放。
视窗X轴的最小值对齐元素viewBox的<min-x>。
视窗Y轴的中间值来对齐元素的viewBox的中间值。
把这个类比为backrgound-position: 0% 50%;。
- xMinYMax
强制统一缩放。
视窗X轴的最小值对齐元素viewBox的<min-x>。
视窗X轴的最大值对齐元素的viewBox的<min-y>+<height>。
把这个类比为backrgound-position: 0% 100%;。
- xMidYMin
强制统一缩放。
视窗X轴的中间值对齐元素的viewBox的X轴中间值。
视窗Y轴的中间值对齐元素的viewBox的 <min-y>。
把这个类比为backrgound-position: 50% 0%;。
- xMidYMid (默认值)
强制统一缩放。
视窗X轴的中间值对齐元素的viewBox的X轴中间值。
视窗Y轴的中间值对齐元素的viewBox的Y轴中间值。
把这个类比为backrgound-position: 50% 50%;。
- xMidYMax
强制统一缩放。
视窗X轴的中间值对齐元素的viewBox的X轴中间值。
视窗Y轴的最大值对齐元素的viewBox的<min-y>+<height>。
把这个类比为backrgound-position: 50% 100%;。
- xMaxYMin
强制统一缩放。
视窗X轴的最大值对齐元素的viewBox的 <min-x>+<width>。
视窗Y轴的最小值对齐元素的viewBox的<min-y>。
把这个类比为backrgound-position: 100% 0%;。
- xMaxYMid
强制统一缩放。
视窗X轴的最大值对齐元素的viewBox的 <min-x>+<width>。
视窗Y轴的中间值对齐元素的viewBox的Y轴中间值。
把这个类比为backrgound-position: 100% 50%;。
- xMaxYMax
强制统一缩放。
视窗X轴的最大值对齐元素的viewBox的 <min-x>+<width>。
视窗Y轴的最大值对齐元素的viewBox的 <min-y>+<height>。
把这个类比为backrgound-position: 100% 100%;。
所以，通过使用preserveAspectRatio属性的align和meetOrSlice值，你可以声明是否统一缩放viewBox，是否和视窗对齐，在视窗中是否整个可见。