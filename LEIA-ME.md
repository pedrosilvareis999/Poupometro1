# Poupómetro — site com CMS visual

Este projeto usa **Eleventy** (gera o site a partir destes ficheiros) e **Decap CMS**
(o painel visual em `/admin` onde vais editar texto e imagens, sem tocar em código).

## Passo a passo para pores isto a funcionar

### 1. Criar um repositório no GitHub (gratuito)
1. Cria conta em github.com, se ainda não tiveres.
2. Cria um novo repositório (ex: `poupometro`), público ou privado — tanto faz.
3. Na página do repositório, usa o botão "Add file → Upload files" e arrasta
   **todo o conteúdo desta pasta** (incluindo o ficheiro `.eleventy.js`, que começa
   por ponto — confirma que o teu explorador de ficheiros mostra ficheiros ocultos).
4. Confirma o upload ("Commit changes").

### 2. Ligar o repositório ao Netlify
1. Em app.netlify.com, escolhe "Add new site → Import an existing project".
2. Autoriza o Netlify a aceder ao GitHub e escolhe o repositório `poupometro`.
3. O Netlify deteta automaticamente o ficheiro `netlify.toml` (comando de build
   e pasta de publicação já vêm configurados) — não precisas de mexer em nada,
   só confirmar "Deploy site".
4. Espera 1-2 minutos pelo primeiro deploy.

### 3. Ativar o CMS (Identity + Git Gateway)
1. No painel do site no Netlify, vai a **Site configuration → Identity** → "Enable Identity".
2. Em Identity → Registration, escolhe "Invite only" (para ninguém se registar sem seres tu a convidar).
3. Em Identity → Services → Git Gateway, clica "Enable Git Gateway".
4. Em Identity → volta ao separador principal e usa "Invite users" para te convidares
   a ti mesmo com o teu email.
5. Vais receber um email — clica no link, define uma password.

### 4. Usar o CMS
1. Vai a `https://o-teu-site.netlify.app/admin`.
2. Faz login com o email/password que definiste.
3. Vais ver dois grupos: **"Artigos do Blog"** (os 4 guias) e **"Página Inicial"**
   (textos e números da homepage). Edita o que quiseres, incluindo imagens
   (botão de upload em qualquer campo de imagem).
4. Ao clicares "Publish", o Decap CMS grava a alteração no GitHub, o que despoleta
   automaticamente um novo build no Netlify — o site atualiza-se sozinho em ~1 minuto.

## Estrutura do projeto (para referência)

```
src/
  articles/          → os 4 artigos (editáveis pelo CMS)
  _data/site.json    → textos da página inicial (editável pelo CMS)
  _includes/         → layouts HTML partilhados (não editar pelo CMS)
  admin/             → configuração do painel /admin
  images/            → imagens carregadas pelo CMS ficam aqui
  index.njk          → template da homepage
  blog.njk           → template da lista de artigos
  style.css          → toda a aparência visual do site
```
