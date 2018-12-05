## 重排与重绘
![avatar](https://raw.githubusercontent.com/mouse123/my-tips/master/image/gpu.gif)
- 简而言之，重排（reflow）和重绘（repaint）都是改变页面样式的步骤。重排步骤包括 Recalculate Style、Layout、Update Layer Tree 等渲染类型事件，重绘步骤包括 Paint 和 Composite Layers 这些绘制类型事件。重排之后必然会造成重绘，而造成重绘的操作不一定会造成重排。下面列出了一些造成重排或重绘的常见操作，更多操作可以参阅 [csstriggers](https://link.zhihu.com/?target=https%3A//csstriggers.com/)