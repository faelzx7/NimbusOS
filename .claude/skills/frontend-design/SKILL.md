---
name: frontend-design
description: >
  Cria e revisa interfaces web (componentes, telas, landing pages) com qualidade visual
  profissional — hierarquia, espaçamento, cor, tipografia e acessibilidade tratados como parte
  do código, não como retoque depois. Use quando o usuário pedir "cria uma interface", "monta
  essa landing page", "melhora esse componente", "converte esse mockup em código", ou
  /frontend-design.
---

# /frontend-design — Interfaces com qualidade visual profissional

Vai além do funcional: entrega componentes e telas com consistência visual e boa experiência de
uso, não só HTML/CSS que "funciona".

## Dependências

- **Identidade (se o negócio já tiver uma):** `identidade/identidade.md` — cores, tipografia e
  personalidade visual definidas ali sobrescrevem os padrões genéricos abaixo.
- **Voz (pra copy dentro da interface):** `_memoria/preferencias.md`.

## Quando usar

- Criar componente de UI do zero.
- Revisar/melhorar interface existente.
- Converter mockup ou wireframe em código.
- Montar landing page ou página de produto.

---

## Princípios

### Hierarquia visual

- Um elemento principal por tela — um CTA, um título, uma ação primária. Se tudo compete por
  atenção, nada se destaca.
- Escala de fonte consistente (ex: 12/14/16/20/24/32/48px) — evitar tamanhos aleatórios entre
  componentes parecidos.
- Contraste mínimo AA (4.5:1 pra texto normal) — acessibilidade não é opcional.

### Espaçamento

- Escala de 4px (4, 8, 12, 16, 24, 32, 48, 64) — todo espaçamento vem dessa régua, nunca valor
  solto tipo `13px` ou `27px`.
- Padding interno consistente por tipo de componente (todo card com o mesmo padding, todo botão
  com a mesma proporção).
- Espaço em branco generoso comunica qualidade — resistir ao impulso de preencher tudo.

### Cor

- Definir a paleta por função, não por preferência solta: primária, secundária, neutros, e
  semânticas (sucesso, erro, alerta). Se `identidade/identidade.md` já define isso, usar dali.
- Evitar preto puro (`#000`) e branco puro (`#FFF`) em fundos grandes — prefira tons próximos
  (ex: `#0F0F0F`/`#1A1A1A` pro escuro, `#FAFAFA`/`#F5F5F5` pro claro). Reduz fadiga visual e
  parece mais trabalhado.
- **Dar ritmo às dobras — nunca a página inteira num tom só.** Numa página com várias seções
  (landing, página de produto), alternar o fundo entre as dobras: uma clara/branca, a próxima
  escura, outra num tom de acento, e assim por diante. Fundo monocromático do topo ao rodapé
  achata a página e cansa. A cada seção, escolher deliberadamente uma cor de fundo da paleta que
  contraste com a vizinha — sem cair no aleatório: 2 a 4 "famílias" de fundo que se revezam num
  ritmo claro (ex: escuro → claro → escuro → acento → claro).
- Ao trocar o fundo de uma dobra, **trocar junto a paleta inteira daquela dobra** — texto, cards,
  bordas, cor de acento — pra manter o contraste AA em cada uma. O jeito robusto é tokens por
  seção (variáveis CSS `--sec-*` que cada dobra sobrescreve), não recolorir elemento a elemento.

### Tipografia

- No máximo 2 famílias de fonte por projeto (uma pra título, uma pro corpo — ou a mesma família
  em pesos diferentes).
- Entrelinha (line-height): ~1.5 pro corpo de texto, ~1.2 pra títulos grandes.
- Letter-spacing levemente negativo em títulos grandes costuma ler como mais refinado.

---

## Stack (usar como padrão, salvo o projeto já ter uma stack definida)

- React + Tailwind CSS pra maioria dos casos.
- Framer Motion pra animação, quando a interação pedir.
- Radix UI (ou equivalente) como base de componentes acessíveis (dropdown, dialog, etc.) — não
  reinventar isso do zero.
- Biblioteca de ícones consistente (uma só por projeto).

## Workflow

1. Confirmar se há identidade visual definida (`identidade/identidade.md`). Se houver, usar as
   cores/tipografia de lá. Se não, usar os padrões da seção "Princípios" acima e avisar que está
   usando um padrão neutro.
2. Entender o objetivo da tela/componente antes de codar — qual é a ação principal que ela
   precisa gerar.
3. Construir componentizado e reutilizável, mobile-first.
4. Cobrir os estados relevantes: padrão, hover, ativo, desabilitado, carregando, erro — não só
   o estado "feliz".
5. Comentar apenas decisões de design não óbvias (por que esse espaçamento, por que essa cor) —
   não narrar o que o código já mostra.

## Regras

- Responsivo por padrão, não como etapa separada depois.
- Nunca usar preto/branco puro em áreas grandes de fundo.
- Numa página de várias seções, nunca deixar tudo num fundo só — alternar as dobras (clara,
  escura, acento) num ritmo deliberado, trocando a paleta inteira de cada dobra junto com o fundo.
- Nunca mais de 2 famílias de fonte no mesmo projeto.
- Todo espaçamento vem da escala de 4px — sem valores soltos.
- Se `identidade/identidade.md` estiver preenchida, ela manda mais que qualquer padrão genérico
  desta skill.
