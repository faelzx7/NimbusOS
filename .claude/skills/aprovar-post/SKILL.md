---
name: aprovar-post
description: >
  Publica um conteúdo já pronto (criado por /publicar-tema): tira o artigo do modo rascunho, sobe
  as imagens do carrossel pro site, faz commit/push (deploy automático assume o resto), e posta o
  carrossel no Instagram e Facebook via Meta Graph API. Use quando o usuário disser "aprova esse
  post", "publica o conteúdo de X", "pode postar", ou /aprovar-post <slug>.
---

# /aprovar-post — Publicação de um conteúdo aprovado

Ponte entre o conteúdo já criado (blog + carrossel + legendas) e a publicação real no ar.

## Quando não usar

- Conteúdo ainda não existe → rodar `/publicar-tema` primeiro.
- Usuário ainda está revisando o rascunho → esperar confirmação explícita de aprovação.
- Site sem deploy automático ou API do Meta sem configurar → seguir o setup abaixo antes.

## Pré-requisitos (configurar uma vez)

- `.env` na raiz (nunca commitado — já coberto pelo `.gitignore`) com:
  - `META_PAGE_ACCESS_TOKEN`, `META_PAGE_ID`, `META_IG_USER_ID`
  - `SITE_URL`
- Deploy automático do site a partir do branch principal (Netlify, Vercel, ou equivalente).
- Conta Instagram Business conectada à Página do Facebook, com permissões da Meta App em ordem.

Se algo estiver faltando, parar e apontar exatamente o que falta configurar antes de continuar.

## Argumento

`/aprovar-post <slug>` — slug do artigo (nome do arquivo em `marketing/conteudo/`, sem `.md`).
Sem argumento, listar os artigos em rascunho e perguntar qual.

## Workflow

### Passo 1 — Localizar os arquivos

- Artigo: `marketing/conteudo/<slug>.md`.
- Pasta do carrossel: `marketing/conteudo/<slug>-*` (sufixo de data).
- Confirmar que existem os PNGs dos slides e as legendas (`legenda.md`,
  `legenda-linkedin.md`). Se faltar algo, parar e relatar o que falta.

### Passo 2 — Confirmação final

Mostrar: título do artigo, quantos slides tem o carrossel, primeiras linhas da legenda, e a URL
final. Perguntar explicitamente: **"Confirma a publicação?"** — só seguir com "sim".

### Passo 3 — Publicar o artigo

Tirar o artigo do modo rascunho no frontmatter.

### Passo 4 — Subir as imagens

Copiar os PNGs do carrossel pra pasta pública do site (criar destino se não existir).

### Passo 5 — Commit e push

```bash
git add <arquivo do artigo> <pasta de imagens>
git commit -m "publica: <título>"
git push origin main
```

### Passo 6 — Confirmar deploy

Aguardar o deploy automático (1-3 min típico) e checar que a URL responde:

```bash
curl -sf -o /dev/null -w "%{http_code}" "$SITE_URL/blog/<slug>/"
```

Sem HTTP 200 dentro de um tempo razoável, avisar o usuário e perguntar se quer continuar mesmo
assim ou abortar (a Meta API precisa da imagem acessível publicamente pra funcionar).

### Passo 7 — Postar no Instagram e Facebook

Rodar os scripts de publicação (via `.env` com as credenciais da Meta). Capturar o ID do post
retornado. Se o Instagram falhar, **não seguir pro Facebook** — parar e relatar.

### Passo 8 — LinkedIn

Publicação de empresa no LinkedIn normalmente exige API própria com aprovação. Até isso estar
configurado, mostrar o texto de `legenda-linkedin.md` pronto pra o usuário colar manualmente.

### Passo 9 — Resumo

```
✓ Publicado: <título>
Site:      <SITE_URL>/blog/<slug>/
Instagram: <link do post>
Facebook:  <link do post>
LinkedIn:  pendente — cole o texto de legenda-linkedin.md manualmente
```

## Tratamento de erro

- Push falhou → reverter o frontmatter pra rascunho, relatar, parar.
- Deploy não confirmado a tempo → relatar e perguntar se segue mesmo assim.
- Instagram falhou → parar (site e blog já publicados, só o post no feed pendente).
- Facebook falhou com Instagram OK → relatar e sugerir tentar de novo só o Facebook.

## Princípios

1. Nunca pular a confirmação humana do Passo 2 — publicação é irreversível na prática.
2. Rodar de novo com o mesmo slug deve detectar que já foi publicado e perguntar se é
   republicação ou só atualização, em vez de duplicar.
3. Qualquer pré-requisito faltando é motivo pra abortar e explicar, não pra seguir com gambiarra.
