# 花野稀泥手绘插画 Skill

本 skill 保留原 `ian-xiaohei-illustrations` 的文章理解、认知锚点、shot list、原创隐喻、单图生成、QA 与交付工作流，仅将默认 IP 替换为花野稀泥。

花野稀泥有两套固定形象：背袋版把紫粉色奇思妙想袋背在身后，头套版把紫粉色奇思妙想袋直接套在头顶；两版都保留左右两个对称结。两版共享紫色椭圆墨镜、粉色泡泡糖、灰/灰紫色创作者套装，以及胸前黑猫 + 蓝色不规则星形 + 恰好四条橙色鱼的徽章。不得把两版混成第三种形态，也不得添加额外动物、鱼或枪形徽章。

默认风格是纯白留白、黑色细手绘线条和少量红/橙/蓝标签。用户明确要求安装/教程流程时，允许使用 3–5 格连续手绘分镜；每格一个核心动作，角色始终参与动作。

先读 [`SKILL.md`](SKILL.md)，再按需读取 `references/` 中的双形象角色、风格、构图、Prompt 与 QA 规则。

## 与上游小黑 Skill 的对齐

本目录保留上游 Hub 的完整能力与目录职责：Illustrations 1.0、Scenes 2.0、Handdrawn PPT、模式路由、Grok 参数说明、Prompt、QA、真实物件场景、Long-scroll 和混合交付。唯一的角色替换是将小黑替换为花野稀泥，并固定为 `backpack` 背袋版或 `head-worn` 头套版。

## 最终形象确认与调用规则

仓库内两张最终头部参考图为唯一标准：无头套背袋版使用 assets/standard-sheet/huayexini-backpack-no-headwear-reference.png；有头套版使用 assets/standard-sheet/huayexini-head-worn-reference.png。用户未明确指定时，生成前必须先询问选择哪一版；明确要求两版时分别生成且整组固定。两版均保持黑色短直 Bob 齐刘海、灰色宽松西装短裤、白色衬衣与领带、紫色椭圆墨镜、粉色泡泡糖和黑猫四鱼徽章；头套袋只放抽象想法符号，背袋基本为空，禁止任何写实器官元素。
