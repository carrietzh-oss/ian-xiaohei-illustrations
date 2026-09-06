# Handdrawn PPT 模式（保留原页面型能力，替换角色）

当用户明确说 PPT、slides、deck、课程页、文章封面或多页技术解释时使用。这里的 PPT 指 PNG 页面图，不承诺可编辑 `.pptx`。

## 工作流

1. 读取主题、受众、使用场景和材料。
2. 规划 deck 故事线。
3. 为每页选择一个页面构图原型。
4. 锁定整套页面的纸张、线条、标题位置和尺度。
5. 每页单独调用一次 `image_gen`。
6. 需要总览时制作 contact sheet 或按顺序列出页面。

## 页面 DNA

- 近白背景、细手绘线、轻铅笔排线、少量浅蓝/鼠尾草绿/桃色/薰衣草色点缀。
- 中央图解小而清楚，页面保留大块留白。
- 标题克制，文字只使用用户提供的短文案。
- 不使用厚重幻灯片边框、企业模板、光泽 3D 或照片拼贴。
- 花野稀泥不是每页强制出现；如果出现，必须先固定 `backpack` 背袋版或 `head-worn` 头套版，保持恰好两个对称扎结，套装保持灰色；整套页面不得无理由切换变体。

## 页面格式

| 页面角色 | 建议比例 |
| --- | --- |
| 文章封面 | 20:9 或用户指定比例 |
| 标准正文页 | 16:9 |

## 页面原型

封面/隐喻、左右对照、轻量流程、循环、分类、矩阵、短列表和总结页。每页只讲一个观点，不把整篇正文塞入图片。

## 提示词骨架

```text
Near-white hand-drawn technical explanation page, thin wobbly pen lines, light pencil hatching, soft restrained pastel marks, large negative space, small central diagram, restrained title, no heavy slide border, no corporate PowerPoint template, no glossy 3D.
Page role: {封面/正文页}.
Main point: {一个观点}.
Layout archetype: {页面原型}.
Required text only: {用户提供的准确短文字}.
If a character appears, use the fixed Huayexini IP, not the original Xiaohei; choose exactly one variant — backpack behind the shoulders or head-worn directly on top of the head — and keep the gray suit and double-knot construction consistent.
```
