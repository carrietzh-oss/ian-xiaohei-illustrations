# 花野稀泥 IP Illustrations

这是“花野稀泥”个人 IP 的可复用图像生成 Skill 适配包。

它把固定角色、画风、徽章、配色、Prompt、构图和验收规则放在同一个可安装目录中，用于生成小红书封面、漫画、拼豆、贴纸、表情、场景和创意实验插画。

## 当前基准

- 角色：冷脸萌创意实验者
- 核心外貌：紫色双结脑洞袋、短黑发、紫色墨镜、泡泡糖、灰紫创作者套装
- 最终徽章：黑猫＋蓝色异形星形＋四条橙色小鱼
- 账号定位：花野稀泥，AI × 视觉创意实验

## 目录

```text
.
├── README.md
├── SKILL.md
├── assets/
│   ├── huayexini-front-final.png
│   ├── black-cat-four-fish-badge.png
│   ├── standard-sheet/          # 10 张标准设定图与徽章源文件
│   └── derivatives/             # 已选 4 张正式衍生资产
├── references/
│   ├── huayexini-ip.md
│   ├── style-dna.md
│   ├── prompt-template.md
│   ├── composition-patterns.md
│   └── qa-checklist.md
└── examples/
    └── prompts.md
```

标准设定图的编号、用途和不可变识别点见 `assets/standard-sheet/README.md`。

已选的漫画、拼豆、透明贴纸和封面样稿见 `assets/derivatives/README.md`。

## 使用示例

```text
使用 huayexini-illustrations Skill，生成一张花野稀泥风格的小红书封面。
主题：我用 AI 把普通照片变成了意外的视觉作品。
画面比例：4:5。
保持冷脸萌角色、紫色双结脑洞袋、灰紫套装和黑猫四鱼蓝色星形徽章。
```

## 重要规则

1. 每次生成都先读取 `references/huayexini-ip.md` 和 `references/style-dna.md`。
2. 一次只改变动作、场景或道具中的一到两个变量。
3. 角色核心外貌、徽章、配色和冷脸萌表情不能随机改变。
4. 多个独立需求要分别生成，不要挤在一张图里。
5. 生成后使用 `references/qa-checklist.md` 做检查。
