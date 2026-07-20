---
name: copy
description: >
  Escreve copy de venda e institucional sob demanda — headlines, e-mails de venda, landing
  pages, taglines, anúncios, cartas de venda. Diagnostica o nível de consciência e sofisticação
  do mercado antes de gerar qualquer texto, em vez de escrever copy genérica. Use quando o
  usuário pedir "escreve uma copy", "texto de venda", "headline pra isso", "tagline",
  "landing page", "carta de venda", "melhora esse texto pra vender mais", ou /copy.
---

# /copy — Copywriting sob diagnóstico

Skill de copy geral-propósito. Complementa `/carrossel`, `/anuncio-google` e `/publicar-tema`
(que já geram a própria copy internamente) pra tudo que é formato aberto — landing pages, cartas
de venda, taglines, headlines avulsas, e-mails de venda, reescrita de texto existente.

## Dependências

- **Negócio:** `_memoria/empresa.md`.
- **Voz:** `_memoria/preferencias.md`.
- **Identidade (se o formato for visual, ex: landing page em HTML):** `identidade/identidade.md`.

---

## Por que diagnosticar antes de escrever

Copy que usa a mesma fórmula pra qualquer produto é o motivo de tanto texto de venda soar igual.
Antes de escrever uma linha, entender quem é o leitor e o que ele já sabe.

### Nível de consciência do leitor

1. **Não sabe que tem o problema** — copy precisa nomear a dor antes de vender qualquer coisa.
2. **Sabe do problema, não conhece soluções** — copy foca em apresentar a categoria de solução.
3. **Conhece a categoria, não o produto** — copy foca em por que essa abordagem funciona.
4. **Conhece o produto, não decidiu** — copy foca em diferencial concreto e prova.
5. **Já quer comprar** — copy foca na oferta: preço, condição, urgência real.

### Saturação do mercado

Quanto mais promessas parecidas o público já viu nesse nicho, menos a promessa crua funciona —
precisa de mecanismo ou diferencial específico pra furar o ceticismo. Perguntar (ou inferir de
`_memoria/empresa.md`): esse tipo de oferta é comum no nicho? Nicho pouco explorado aceita
promessa direta; nicho saturado (emagrecimento, "ganhar dinheiro online", etc.) exige
especificidade.

---

## Workflow

### Passo 1 — Entender o pedido

Se não estiver claro, perguntar:
1. "Que formato? (headline, e-mail de venda, landing page, tagline, anúncio, carta de venda, ou
   reescrita de algo que você já tem)"
2. "Pra quem é? (se não souber o nível de consciência, descreve o público que a gente classifica
   junto)"
3. "Que ação o texto precisa gerar?"

Se o usuário colar um texto pra reescrever, pular a pergunta 1 e diagnosticar o texto direto.

### Passo 2 — Diagnóstico

Classificar consciência + saturação (seção acima) e mostrar em 1-2 linhas antes de escrever:

> "Isso é pra um público [nível], num mercado [saturado/pouco explorado] pra esse tipo de oferta.
> Vou [abordagem escolhida]."

### Passo 3 — Escrever

Seguir `_memoria/preferencias.md` à risca — sem jargão de guru se o tom do negócio não pedir isso.

- **Headlines:** 3-5 variações, ângulos diferentes (benefício direto, curiosidade, prova social,
  mecanismo) — nunca só uma.
- **E-mail/carta de venda:** gancho nas primeiras duas linhas, corpo constrói o caso (problema →
  mecanismo → prova → oferta), um único CTA no fechamento — não empilhar chamadas concorrentes.
- **Landing page:** texto por bloco (herói, dor/promessa, como funciona, prova social, oferta,
  perguntas frequentes, chamada final) — HTML só se pedido, e nesse caso seguindo
  `identidade/identidade.md`.
- **Tagline:** 3-8 palavras, testável em voz alta, 5-8 opções.

### Passo 4 — Checkpoint

Mostrar o texto completo e perguntar sobre tom, tamanho ou ângulo antes de considerar pronto —
copy é iterativa, não entrega de primeira tentativa.

## Regras

- Nunca prometer o que o negócio não sustenta (garantia, prazo, resultado que
  `_memoria/empresa.md` não confirma).
- Nunca inventar prova social (depoimento, número, case) — só usar o que o usuário fornecer como
  real.
- Superlativo só com razão concreta atrás — nunca de graça.
- Copy institucional (tagline, manifesto) é mais sóbria que copy de resposta direta — não
  confundir os dois registros.
- Reescrita de texto de um cliente preserva a voz existente, a menos que peçam mudança de tom.
