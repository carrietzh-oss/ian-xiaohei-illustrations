---
name: huayexini-illustrations
description: >
  为中文文章、帖子、Notion、方法论、产品比较、工作痛点、复盘、课程和 PPT 生成视觉内容；
  完整路由 Illustrations 1.0、Scenes 2.0 与 Handdrawn PPT，保留小黑 Skill 的全部工作流、
  认知锚点、原创隐喻、真实物件、页面型能力和 QA，只将角色替换为花野稀泥，并固定使用
  背袋版或头套版两种 IP 形象。
metadata:
  short-description: "花野稀泥版 Illustrations、Scenes 与 Handdrawn PPT 视觉 Hub"
---
# 花野稀泥 Visual Hub — Illustrations · Scenes · Handdrawn PPT (Grok)

## Posicionamento

Esta skill é o **hub em português BR** para a família visual do Ian no **Grok Build**. Por padrão este repositório entrega o modo **Illustrations (花野稀泥 1.0)**, mas **deve contemplar e rotear** os projetos irmãos:

| Modo | Projeto | Repo |
|------|---------|------|
| `illustrations` | Ian 花野稀泥 Illustrations (1.0) | https://github.com/helloianneo/ian-xiaohei-illustrations |
| `scenes` | Ian 花野稀泥 Scenes (2.0) | https://github.com/helloianneo/ian-xiaohei-scenes |
| `handdrawn-ppt` | Ian Handdrawn PPT | https://github.com/helloianneo/ian-handdrawn-ppt |

> URL com typos tipo `ian-xiaohei-scenesssssssssss` → tratar como **ian-xiaohei-scenes**.

### Em uma frase por modo

- **Illustrations 1.0:** julgamento/fluxo/estrutura → rascunho de quadro absurdo, traço preto, fundo branco puro, rótulos vermelho/laranja/azul. 花野稀泥 na ação conceitual.  
- **Scenes 2.0:** situação humana → mini-set com **objeto real** + 花野稀泥 na ação física; opcional **long-scroll** de trajetória.  
- **Handdrawn PPT:** material → **páginas PNG** estilo explicação técnica à mão (Capa 20:9 (Grok), corpo 16:9). 花野稀泥 em geral **não** entra.

## Passo 0 — Roteamento (obrigatório)

Antes de gerar, leia `references/ecosystem-routing.md` e declare o modo de cada entrega:

```text
Modo: illustrations | scenes | handdrawn-ppt | híbrido
Submodo (se scenes): padrão 16:9 | long-scroll
Submodo (se ppt): Capa 20:9 (Grok) | corpo 16:9 | deck N páginas
```

| Pedido do usuário | Modo |
|-------------------|------|
| Fluxo, método, Clean Core, comparação de produto, whiteboard | `illustrations` |
| Dor, reunião, overload, “é sobre mim”, objeto real, 花野稀泥 2.0 | `scenes` |
| Trajetória, retrospectiva, evolução do produto em friso | `scenes` + long-scroll |
| PPT, slides, curso, capa de artigo, deck | `handdrawn-ppt` |
| Artigo completo com capa + método + dor | **híbrido** (pastas separadas) |

Se ambíguo e a escolha mudar o resultado: **uma** pergunta curta. Senão, default = `illustrations`.

**Não misture DNAs no mesmo canvas** (traço 1.0 + props foto 2.0, ou slide com título de PPT dentro de illustrations).

## Runtime: Grok Build

| Situação | Ferramenta |
|----------|------------|
| Nova imagem | `image_gen` + `aspect_ratio` adequado |
| Editar | `image_edit` |
| QA visual | `read_file` na imagem |
| Consistência de personagem/deck | mesma descrição de IP/style lock; opcional ref em `image_edit` |

### Aspect ratios

| Modo | Ratio |
|------|-------|
| illustrations (corpo) | `16:9` |
| scenes (padrão) | `16:9` |
| scenes long-scroll | `20:9` (Grok; `21:9` inválido na API) |
| handdrawn-ppt capa | `20:9` (Grok; `21:9` inválido na API) |
| handdrawn-ppt corpo | `16:9` |

Orientação geral de prompt Imagine: skill `imagine` do Grok; **DNA do modo escolhido** tem prioridade.

## Mapa de referências

Leia **só o necessário** do modo ativo:

### Sempre (hub)

- `references/ecosystem-routing.md` — decisão de modo e híbridos.

### Modo `illustrations` (completo neste repo)

- `references/style-dna.md`
- `references/huayexini-ip.md`
- `references/huayexini-variants.md`
- `references/composition-patterns.md`
- `references/prompt-template.md`
- `references/qa-checklist.md`
- `assets/standard-sheet/` — única fonte de identidade: as duas imagens confirmadas pelo usuário e o recorte do distintivo.

### Modo `scenes` (condensado neste repo)

- `references/mode-scenes.md`
- Se a skill irmã existir em `~/.grok/skills/ian-xiaohei-scenes/`, **prefira o SKILL.md e references oficiais**.

### Modo `handdrawn-ppt` (condensado neste repo)

- `references/mode-handdrawn-ppt.md`
- Se existir `~/.grok/skills/ian-handdrawn-ppt/`, **prefira o pacote oficial**.

## IP identity lock — exactly two variants

The output character is always 花野稀泥. Before generating, select exactly one user-confirmed variant and keep it fixed across the image set:
- `backpack` / A 无头套背袋版: short straight black Bob hair with blunt bangs fully visible; the translucent purple-pink double-knot bag is worn on the back only and is basically empty.
- `head-worn` / B 有头套版: the same short straight black Bob hair appears below a translucent purple-pink double-knot bag worn directly on the head; the bag contains only abstract idea symbols such as light bulbs, stars, paper notes and question marks.
- Both variants share the exact gray loose suit shorts, white shirt, tie, waist belt, purple oval sunglasses, pink bubble gum, purple-white-black shoes, deadpan-cute expression, and black-cat + blue star + exactly four orange fish badge.
- Never combine the two variants in one image or change the selected variant without the user explicitly requesting a switch.
- If the user does not specify a variant, ask which one to use. Do not auto-select from movement, desk, tutorial, aspect ratio, or any other scene heuristic.

## Fluxos por modo

### A) Illustrations (1.0) — detalhe completo

1. Digestão → âncoras cognitivas.  
2. Shot list (se só planejar).  
3. `image_gen` 16:9 por âncora (template em `prompt-template.md`).  
4. QA `qa-checklist.md`; `image_edit` se preciso.  
5. Salvar em `assets/<slug>-illustrations/`.

Regras-chave: fundo branco puro; traço preto; 花野稀泥 na ação; ≤5–8 rótulos curtos; sem PPT; metáfora nova, sem carregar imagens históricas de personagens.

### B) Scenes (2.0) — ver `mode-scenes.md`

1. Extrair **situação** + ação física + objeto real.  
2. Shot list com ressonância (não só estrutura).  
3. `image_gen` 16:9 (ou 20:9 long-scroll).  
4. QA: mini-set real, 花野稀泥 na ação, sem inventário de props.  
5. `assets/<slug>-scenes/` ou `…-long-scroll/`.

### C) Handdrawn PPT — ver `mode-handdrawn-ppt.md`

1. Intake + blueprint (título, ponto, arquétipo, texto exato).  
2. Style lock do deck em todos os prompts.  
3. Capa `20:9` + páginas `16:9`, uma `image_gen` cada.  
4. QA de consistência de deck e texto curto.  
5. `assets/<slug>-handdrawn-ppt/`.  
6. **Não** entregar PPTX salvo pedido explícito fora desta skill.

### D) Híbrido

Declarar tabela frame → modo. Gerar por modo. Pastas separadas. Entregar mapa:

```text
capa → handdrawn-ppt
01–04 → illustrations
05–06 → scenes
```

## Idioma

| Origem do texto | Rótulos / títulos na imagem |
|-----------------|----------------------------|
| PT-BR | Português curto |
| Chinês | Chinês curto |
| Misto | Idioma dominante do trecho |

Modelos de imagem falham com texto longo: **menos rótulos, mais estável**.

## Instalação no Grok

```powershell
# Hub (este repo)
$dest = Join-Path $env:USERPROFILE ".grok\skills\ian-xiaohei-illustrations"
Copy-Item -Recurse -Force ".\ian-xiaohei-illustrations" $dest
```

Opcional — skills irmãs completas:

```powershell
# Após clonar os repos oficiais
Copy-Item -Recurse -Force ".\ian-xiaohei-scenes\ian-xiaohei-scenes" (Join-Path $env:USERPROFILE ".grok\skills\ian-xiaohei-scenes")
Copy-Item -Recurse -Force ".\ian-handdrawn-ppt\ian-handdrawn-ppt" (Join-Path $env:USERPROFILE ".grok\skills\ian-handdrawn-ppt")
```

Com as três instaladas, o hub **roteia**; a execução profunda usa o pacote irmão se presente.

## Uso típico

```text
Use $huayexini-illustrations (hub Ian).
Para o texto abaixo: roteie o modo certo e gere as imagens no Grok.
Se for método → illustrations; se for dor/situação → scenes; se for deck → handdrawn-ppt.
```

```text
Modo scenes: 3 cenas 花野稀泥 2.0 com objeto real sobre pressão de release.
```

```text
Modo handdrawn-ppt: 1 Capa 20:9 (Grok) + 4 páginas 16:9 sobre Clean Core.
```

```text
Híbrido: capa PPT + 3 illustrations de estrutura + 1 scene de manutenção.
```

## Tom da entrega

Antes: modo escolhido + shot list / blueprint curto.  
Depois: contagem, uso, caminhos, o que é estável vs opcional.  
Sem tratado longo de teoria — deixe a imagem falar.

## 最终 IP 参考锁（v2.0，2026-09-22，强制）

本仓库当前只保留用户刚确认的两张角色图及徽章局部图。两张用户确认图是花野稀泥身份的唯一权威参考；不得读取或使用旧角色图、原小黑人物图、旧标准表或历史衍生图。

| 用户可见选择 | 内部变体 | 权威头部参考 | 固定含义 |
| --- | --- | --- | --- |
| A 无头套背袋版（也可称袋子版） | backpack | assets/standard-sheet/user-confirmed-a-no-headwear-backpack-reference.png | 黑色短直 Bob、齐刘海；不戴头套；透明紫粉袋背在身后，袋内基本为空 |
| B 有头套版 | head-worn | assets/standard-sheet/user-confirmed-b-head-worn-reference.png | 同一黑色短直 Bob、齐刘海；透明紫粉袋直接戴在头上；袋内只能出现抽象奇思妙想符号，如灯泡、星星、纸条、问号 |

生成前的确认门：

- 用户已明确说“无头套背袋版/袋子版”或“有头套版”时，直接使用对应变体；如果明确要求两版，则分别生成并且每一组内部固定一版。
- 用户只说“用我的 IP”“生成插画”或其他未明确变体的请求时，必须先问：**“这次使用哪一套形象：A 无头套背袋版，还是 B 有头套版？”** 在得到选择前不要生成。
- 不得根据构图、场景、尺寸或模型习惯自行猜测变体；不得把两版混在同一角色或同一组图里。
- 两版都固定：黑色短直 Bob 齐刘海、紫色椭圆墨镜、粉色泡泡糖、灰色宽松西装短裤套装、白色衬衣与领带、腰带、紫白黑相间的鞋子，以及黑猫 + 蓝色星形 + 恰好四条橙色鱼徽章。
- 严禁脑组织、肠子、写实器官、身体内部剖面、血腥或其他生物器官隐喻。头套袋中的内容只能是抽象想法符号；背袋版保持基本为空。
- 每次 imagegen/image_edit 调用前，先在内部记录 selected_variant 与对应参考路径；整组图不得中途切换。任何其他形象变化都必须得到用户明确的新确认，不能凭模型习惯改动。
