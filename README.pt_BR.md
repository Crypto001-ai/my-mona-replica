<!-- l10n-sync: source-file="README.md" -->
🌐 [English](README.md) | [Español](README.es.md) | Português (Brasil) | [한국어](README.ko.md)

# 🎮 Mona Mayhem

**Workshop de VS Code e GitHub Copilot CLI** — Construa uma Arena de Batalha de Contribuição do GitHub

Um template de workshop para criar um site temático de arcade retrô com Astro que compara os gráficos de contribuição do GitHub de dois usuários. Este é o **ponto de partida** — você vai construir o app passo a passo usando o GitHub Copilot.

![Mona Mayhem Screenshot](https://github.com/user-attachments/assets/5eca79e2-cb9f-4e93-aa0d-23666ebde3b7)
*O que você vai construir ao final do workshop*

## 📚 Workshop

O workshop oferece dois caminhos — siga aquele que combina com o seu fluxo de trabalho preferido:

- **Caminho do VS Code** — Chat, Plan Mode, Agent Mode, agentes em segundo plano e ciclos de revisão nativos do editor
- **Caminho do CLI** — `copilot`, contexto com `@file`, `/plan`, edições autônomas, `/fleet`, `/delegate` e `/review`

| Parte | Título | Foco do Copilot |
|------|--------|-----------------|
| [00](workshop/pt_BR/00-overview.md) | Visão geral | Seleção do caminho e objetivos de aprendizagem |
| [01](workshop/pt_BR/01-setup.md) | Configuração e engenharia de contexto | Instruções, permissões e preparação do ambiente |
| [02](workshop/pt_BR/02-plan-and-scaffold.md) | Planejar e estruturar | Planejamento da API e da arquitetura da página |
| [03](workshop/pt_BR/03-agent-mode.md) | Construir o jogo | Implementação e iteração com agentes |
| [04](workshop/pt_BR/04-design-vibes.md) | Tematização orientada ao design | Planejamento e implementação visual |
| [05](workshop/pt_BR/05-polish.md) | Polimento e trabalho paralelo | Paralelismo, revisões e refinamentos de qualidade |
| [06](workshop/pt_BR/06-bonus.md) | Bônus e extensões | Ideias extras e experimentos com Copilot |

## 🚀 Início rápido

1. **Crie seu próprio repositório primeiro** usando qualquer uma dessas opções:
   - clicando em **Use this template** para criar um novo repositório, ou
   - fazendo um fork deste repositório.
2. Escolha o caminho do workshop:
   - **VS Code:** clone seu repositório e abra-o no VS Code.
   - **GitHub Copilot CLI:** clone-o localmente, instale `copilot` e trabalhe no terminal.
3. Siga o [guia do workshop](workshop/pt_BR/00-overview.md)

## Pré-requisitos

### Compartilhados

- GitHub Copilot (Pro, Business ou Enterprise)
- Git
- Node.js

### Caminho do VS Code

- VS Code v1.107+
- Extensão do GitHub Copilot conectada

### Caminho do CLI

- GitHub Copilot CLI (`copilot`)
- Node.js 22+ se você planeja instalar a CLI com `npm install -g @github/copilot`
- Ou Homebrew / WinGet se preferir um gerenciador de pacotes nativo

## Stack tecnológica

- **Framework**: [Astro](https://astro.build/) v6
- **Runtime**: Node.js com adaptador [@astrojs/node](https://docs.astro.build/en/guides/integrations-guide/node/)
- **Fonte**: Press Start 2P (fonte retrô arcade)
- **API**: API de gráficos de contribuição do GitHub

## Observações de implantação

### Configuração atual do GitHub Pages

O workflow em `.github/workflows/deploy.yml` atualmente faz o deploy do conteúdo estático do workshop em `docs/` e `workshop/` para o GitHub Pages. Ele não compila nem faz deploy do app Astro de `src/`.

### Se você quiser implantar o app Astro no GitHub Pages

O GitHub Pages é hospedagem estática, então o app Astro deve usar saída estática.

1. Altere `output` em `astro.config.mjs` de `server` para `static`.
2. Remova o adaptador Node (`@astrojs/node`) de `astro.config.mjs` e `package.json`.
3. Atualize o workflow do GitHub Actions para executar `npm ci` e `npm run build`, e então enviar `dist/` como artefato do Pages.
4. Se você estiver implantando em uma página de projeto (`https://<user>.github.io/<repo>/`), defina `site` e `base` em `astro.config.mjs`.

Se você planeja manter as rotas de API em execução em produção, use uma plataforma com servidor em vez do GitHub Pages (por exemplo, Vercel, Netlify ou um host Node).

## Licença

MIT
