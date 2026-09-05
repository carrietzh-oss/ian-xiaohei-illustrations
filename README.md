# 花野稀泥 IP Illustrations

这是“花野稀泥”的个人 IP 图像生成 Skill，基于公开的 `ian-xiaohei-illustrations` 目录结构改造而来。

## 当前 IP 基准

- 角色气质：冷脸萌、安静但有梗的 AI × 视觉创意实验者
- 核心外貌：短直黑 Bob 发、紫粉半透明双结脑洞袋、紫色椭圆墨镜、粉色泡泡糖
- 服装：灰紫创作者套装、深葡萄紫腰封、宽腿短裤、深色鞋
- 固定徽章：黑猫、蓝色异形星形底、四条橙色小鱼
- 适用内容：小红书封面、漫画、拼豆、像素图、贴纸、徽章、表情和创意实验插画

## 安装

将 `ian-xiaohei-illustrations/` 复制到你使用的 Skill 目录中，并以其中的 `SKILL.md` 作为入口。

## 目录

```text
ian-xiaohei-illustrations/
├── SKILL.md
├── agents/openai.yaml
├── assets/
│   ├── huayexini-front-final.png
│   ├── black-cat-four-fish-badge.png
│   ├── standard-sheet/          # 10 张标准设定图与徽章源文件
│   └── examples/                 # 保留的上游参考素材
└── references/
    ├── huayexini-ip.md           # 角色圣经
    ├── style-dna.md               # 画风与配色
    ├── prompt-template.md         # Prompt 模版
    ├── composition-patterns.md    # 构图模式
    └── qa-checklist.md            # 验收清单
```

标准设定图的编号、用途和不可变识别点见 `ian-xiaohei-illustrations/assets/standard-sheet/README.md`。

## 使用示例

```text
使用 huayexini-illustrations Skill，生成一张 4:5 的小红书封面。
主题：我用 AI 把普通照片变成了意外的视觉作品。
保持冷脸萌角色、紫色双结脑洞袋、灰紫套装和黑猫四鱼徽章。
```

## 版权与来源

本仓库保留原项目的 MIT License 和来源说明。花野稀泥角色设定、徽章、配色、Prompt 与新增资产按本仓库中的角色圣经执行；重新发布前请确认新增图片资产的使用权。

原始项目：<https://github.com/ggampp/ian-xiaohei-illustrations>
