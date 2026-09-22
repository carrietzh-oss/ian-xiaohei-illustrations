# Prompt 模板 — Grok image_gen / image_edit

## 组装规则

- 一次 image_gen 只生成一个核心画面；新图默认 aspect_ratio: "16:9"，除非用户明确指定其他比例。
- 先写人物与核心动作，再写隐喻、风格、构图和短标签。
- 每组图先锁定 selected_variant；用户未指定 A/B 时先询问，不得自动选择。
- 文字只使用少量中文短标签；不要在图中塞长段文字。

## 主模板

~~~text
{画幅} hand-drawn absurd article illustration, pure white background, black thin wobbly line art, generous empty space, restrained red/orange/blue accents, not PPT, not a formal infographic, not a commercial mascot poster.

Character lock: 花野稀泥, use exactly one user-confirmed variant: {A backpack / B head-worn}. Keep the user-confirmed proportions and silhouette: short straight black Bob hair with blunt bangs, purple oval sunglasses, pink bubble gum, loose gray suit shorts, white shirt, tie, waist belt, purple-white-black shoes, and the black cat + blue star + exactly four orange fish chest badge.
A backpack: no headwear; the translucent purple-pink double-knot bag is worn on the back only and is basically empty.
B head-worn: the translucent purple-pink double-knot bag is worn directly on the head; exactly two bows; its contents are only abstract idea symbols such as light bulbs, stars, paper notes and question marks.

花野稀泥必须执行核心动作：{动作}。核心隐喻：{一句话}。构图：{人物、真实物件、空间关系和阅读方向}。对象：{1–4 个}。中文短标签：{不超过 5 个}。

Do not change the character identity, do not mix A and B, do not create a third variant. No gray hair, earrings, long trousers, different shoes, missing sunglasses, missing gum, missing badge, extra fish, extra animals, organs, brain tissue, intestines, gore, anatomical imagery, logos, watermarks, copied reference composition, or dense text.
~~~

## 短模板

~~~text
{画幅} pure-white hand-drawn absurd product sketch. 花野稀泥使用已选择的 {A 无头套背袋版 / B 有头套版}，保持用户确认图中的黑色短直 Bob 齐刘海、灰色西装短裤、白衬衣、领带、腰带、紫色椭圆墨镜、粉色泡泡糖、紫白黑鞋子和黑猫蓝星四橙鱼徽章；A 透明袋只在背后且基本为空，B 透明袋只在头顶且只含抽象奇思妙想符号。角色执行：{动作}。画面表达：{隐喻}。中文短标签：{标签}。不要第三种形象、器官元素、PPT、长文字或复制参考图构图。
~~~

## 编辑模板

~~~text
只修正角色一致性，保持原画面的动作、构图、道具、文字和线稿不变。使用 {A / B} 对应的用户确认参考图锁定黑色短直 Bob 齐刘海、灰色西装短裤、白衬衣、领带、腰带、紫色墨镜、粉色泡泡糖、紫白黑鞋子和黑猫蓝星四橙鱼徽章。A 只能背基本为空的透明袋；B 只能戴含抽象奇思妙想符号的透明头套袋。不要混用变体、不要新增袋子、不要器官元素、不要改变画面主题。
~~~

## 参考图选择门（强制）

- A backpack：assets/standard-sheet/user-confirmed-a-no-headwear-backpack-reference.png
- B head-worn：assets/standard-sheet/user-confirmed-b-head-worn-reference.png
- 徽章局部：assets/standard-sheet/badge-black-cat-four-fish.png

实际调用 imagegen/image_edit 时必须把所选 A/B PNG 作为图像输入，不得只把路径写进文字 Prompt。参考图中的脸型、人物比例、冷脸萌＋软萌气质、发型轮廓、服装版型与干净服装笔触必须保持一致；不得自行重绘、润色、美化或改造标准形象。

参考图只锁定人物身份，不复制其中的页面、文字、UI、构图或动作。花野稀泥旧角色图和历史衍生图不得加载。原小黑示例图可以校准构图、认知隐喻和白底手绘风格，但不得校准角色外貌。

如果用户未选择变体，先问：**“这次使用哪一套形象：A 无头套背袋版，还是 B 有头套版？”** 用户要求两版时分组渲染，每组内部固定一个变体。

## 输出参数

~~~text
image_gen:
  prompt: <填写后的模板>
  aspect_ratio: <用户指定比例；未指定时 16:9>
~~~
