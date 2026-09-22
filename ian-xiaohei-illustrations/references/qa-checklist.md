# Checklist de QA (Grok)

## Obrigatório (pass)

- **16:9** horizontal.
- Fundo **branco limpo**.
- Tem **花野稀泥**.
- Usa exatamente uma variante: `backpack` ou `head-worn`; nunca as duas.
- 花野稀泥 na **ação central** (não só decoração).
- Metáfora **nova** para o artigo (não clone de exemplo).
- Absurdo, criativo, interessante.
- Limpo: sujeito ≤ ~**60%** do quadro.
- **Um** núcleo estrutural por imagem.
- Rótulos **poucos, curtos, legíveis** (PT-BR ou chinês).
- Laranja só em fluxo/setas; vermelho em alerta; azul em secundário.

## Sinais de falha → ação no Grok

| Sinal | Ferramenta sugerida |
|-------|---------------------|
| Título no canto | `image_edit` — remover só o título |
| 花野稀泥 fofo / canto | `image_edit` ou nova `image_gen` |
| Cara de PPT / curso | regenerar com template “simplificar” |
| Elementos/setas demais | regenerar com menos nós |
| Texto longo ou ilegível | regenerar com ≤3–5 rótulos curtos |
| Fundo sujo / textura | regenerar reforçando pure white |
| Copiou uma imagem histórica de personagem | regenerar usando somente a referência A/B e trocar objeto + ação |
| Precisa inspecionar texto/estilo | `read_file` na imagem gerada |

## Como iterar

- **Comum demais:** 花野稀泥 sujeito + metáfora estranha coerente.  
- **Complexo:** um movimento, 3–5 rótulos.  
- **Fofo:** deadpan, not cute, not mascot.  
- **PPT:** sem título, grade, setas em excesso.  
- **Clone de exemplo:** mesma ideia, outro objeto e outra ação.  
- **Texto errado:** edição local; se piorar, regenerar com menos texto.

## Entrega

Bom: o leitor pensa “que estranho…” e em ~1s entende a estrutura.

Ruim: parece página de tutorial em vez de rascunho absurdo de produto no papel branco.

## Entrega no workspace

- Listar caminhos retornados pelo Grok (`images/…` ou path absoluto).  
- Se o projeto pedir: copiar para `assets/<slug>-illustrations/01-….png`.  
- Não sobrescrever assets sem confirmação.

## 最终双形象一致性 QA（v2.0）

每张图、每组图输出前必须逐项确认：

- [ ] 已有明确的 selected_variant；未指定时已经先询问用户。
- [ ] 头部严格匹配对应最终参考图：黑色短直 Bob、齐刘海、紫色椭圆墨镜、粉色泡泡糖。
- [ ] backpack 版没有头套，透明紫粉双结袋只在背部且基本为空。
- [ ] head-worn 版的袋子直接在头顶，恰好两个对称结；袋内只有灯泡、星星、纸条等抽象想法符号。
- [ ] 两版均保持灰色宽松西装短裤、白色衬衣、领带、腰带、紫色墨镜、粉色泡泡糖、紫白黑鞋子，以及黑猫 + 蓝星 + 恰好四条橙鱼徽章。
- [ ] 没有脑组织、肠子、写实器官、身体内部剖面、血腥或其他器官元素。
- [ ] 同一组图没有混用两种变体；没有因为场景、姿势、画幅或文字生成第三种形态。
- [ ] 没有灰发、耳饰、长裤、不同鞋子、额外动物、额外鱼、武器、Logo 或水印。
- [ ] 未指定 A/B 时，已在生成前询问用户，没有按场景自动猜测。
