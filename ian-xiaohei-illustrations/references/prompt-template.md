# Template de prompt — Grok `image_gen` / `image_edit`

## Regras de montagem (Grok Imagine)

- **Uma cena por chamada** de `image_gen`.
- Sempre passe **`aspect_ratio: "16:9"`** em novas gerações.
- Escreva o prompt em **prosa natural** (português e/ou inglês). O DNA visual em inglês abaixo costuma estabilizar o estilo; tema e composição podem ir em PT-BR.
- Front-load: sujeito (花野稀泥 + ação) → metáfora → estilo → composição → rótulos.
- Prefira dizer o que **deve existir** (descrições positivas). Mantenha a lista de exclusões do DNA porque o estilo desta skill depende de “não ser PPT”.
- Rótulos: **curtos**. Modelo de imagem erra com texto longo — menos é mais.
- Várias imagens do artigo: várias chamadas; prompts distintos.

## Template principal (`image_gen`)

Substitua as chaves `{…}`. Envie o bloco inteiro (ou uma prosa condensada equivalente) no campo `prompt`.

```text
Ilustração horizontal 16:9 para corpo de artigo, rascunho de produto absurdo e limpo.

Visual DNA:
Pure white background. Minimalist black hand-drawn line art. Slightly wobbly pen lines. Lots of empty white space. Sparse red, orange, and blue handwritten short annotations. Clean absurd product-sketch feeling. No gradients, no shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no cute mascot poster, no children's illustration, no realistic UI, no top-left title banner.

Personagem recorrente (obrigatório):
花野稀泥 / 花野稀泥 — cold-faced cute Q-version creative experimenter with short black Bob hair, the selected translucent purple-pink double-knot brain-bag variant, purple oval sunglasses, pink bubble gum, gray-purple creator outfit, deep grape-purple waist belt, and the black-cat + blue star + exactly four orange fish badge. 花野稀泥 performs the core conceptual action; the character is not a corner decoration. Serious, slightly bizarre, not generic cute.

Tema: {tema da ilustração}

Tipo de estrutura (não escrever o nome na imagem): {Workflow | recorte de sistema | antes e depois | estados | metáfora conceitual | camadas | mapa-rota | mini-quadrinhos}

Ideia central: {uma frase com o que o leitor deve entender}

Composição: {onde está o 花野稀泥, o que faz, objeto low-tech principal, como o fluxo se lê da esquerda para a direita ou no centro}

Elementos: {1–4 objetos no máximo}

Rótulos manuscritos curtos ({idioma: pt-BR ou chinês}), no máximo 5:
{rótulo1} / {rótulo2} / {rótulo3} / {rótulo4} / {rótulo5 opcional}

Cores: preto ou deep grape-purple no traço; use purple-pink only for the selected brain-bag and sunglasses, gray-purple for the creator outfit, orange only for flow/arrows or the four badge fish, red only for alerts/problems/results, and blue only for secondary notes or the badge star.

Restrições: um único núcleo estrutural; sujeito ~40–60% do quadro; ≥35% vazio; sem título no canto; sem copiar composições de exemplos antigos; inventar metáfora fresca para este artigo; claro mas não didático; estranho mas limpo.
```

### Versão curta (quando o contexto já carrega o DNA)

```text
16:9 pure white hand-drawn absurd product sketch. Black wobbly line art, lots of empty space, sparse short handwritten labels in {pt-BR|Chinese} with red/orange/blue only. 花野稀泥 (cold-faced cute Q-version creator with short black Bob hair, the selected backpack or head-worn brain-bag variant, purple oval sunglasses, pink bubble gum, gray-purple creator outfit, and black-cat + blue-star + exactly-four-orange-fish badge) must do the core action: {ação}. Scene: {composição em 1–2 frases}. Labels: {lista curta}. No PPT, no cute mascot, no top-left title, no busy diagram.
```

## Parâmetros da ferramenta

```text
image_gen:
  prompt: <template preenchido>
  aspect_ratio: "16:9"
```

## Variant lock

In every prompt, explicitly select either `backpack` or `head-worn` from `references/huayexini-variants.md`; never mix them.

## Edição (`image_edit`)

### Remover título no canto

```text
Edit only: remove the handwritten title "{texto}" and its underline from the top-left. Fill with clean pure white matching the paper. Keep everything else identical — characters, labels, paths, line style, composition, quality. Do not add any new text or objects.
```

```text
image_edit:
  prompt: <acima>
  image: ["<caminho absoluto da imagem ou token [Image #N]>"]
```

### Reforçar protagonismo do 花野稀泥

```text
Regenerate with the same core meaning and sparse layout, but make 花野稀泥 with the selected backpack or head-worn brain-bag variant central to the conceptual action — the character must perform the strange work that explains the idea, not stand beside a diagram. Keep pure white background, black hand-drawn lines, minimal short labels, not cute.
```

### Calibrar estilo com exemplo (só se pedido)

```text
New illustration for theme "{tema}", invent a fresh metaphor (do not copy the reference composition or objects). Match only the style of the reference: pure white paper, sparse black wobbly line density, limited red/orange/blue handwritten labels, deadpan 花野稀泥 participation. 16:9 article body illustration.
```

Use a referência em `image` (ex.: um PNG em `assets/examples/`).

### Reduzir densidade / “cheiro de PPT”

```text
Simplify: keep the same core idea and 花野稀泥 as action subject. Remove extra nodes, boxes, and arrows. No title, no grid, no formal flowchart look. More empty white space, fewer short labels, hand-drawn product sketch only.
```

## Idioma

- Artigo em **português** → rótulos em **português** curto.
- Artigo em **chinês** → rótulos em **chinês** curto.
- O bloco “Visual DNA” em inglês pode permanecer: estabiliza o render no Imagine.
