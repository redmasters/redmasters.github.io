# Hextra Starter Template

[![Deploy Hugo site to Pages](https://github.com/imfing/hextra-starter-template/actions/workflows/pages.yaml/badge.svg)](https://github.com/imfing/hextra-starter-template/actions/workflows/pages.yaml)
[![Netlify Status](https://api.netlify.com/api/v1/badges/6e83fd88-5ffe-4808-9689-c0f3b100bfe3/deploy-status)](https://app.netlify.com/sites/hextra-starter-template/deploys)
![Vercel Deployment Status](https://img.shields.io/github/deployments/imfing/hextra-starter-template/production?logo=vercel&logoColor=white&label=vercel&labelColor=black&link=https%3A%2F%2Fhextra-starter-template.vercel.app%2F)


🐣 Minimal template for getting started with [Hextra](https://github.com/imfing/hextra)

![hextra-template](https://github.com/imfing/hextra-starter-template/assets/5097752/c403b9a9-a76c-47a6-8466-513d772ef0b7)

[🌐 Demo ↗](https://imfing.github.io/hextra-starter-template/)

## Quick Start

Use this template to create your own repository:

<img src="https://docs.github.com/assets/cb-77734/mw-1440/images/help/repository/use-this-template-button.webp" width=400 />

You can also quickly start developing using the following online development environment:

- [GitHub Codespaces](https://github.com/codespaces)

    [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/imfing/hextra-starter-template)

    Create a new codespace and follow the [Local Development](#local-development) to launch the preview


## Deployment

### GitHub Pages

A GitHub Actions workflow is provided in [`.github/workflows/pages.yaml`](./.github/workflows/pages.yaml) to [publish to GitHub Pages](https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/) for free. 

For details, see [Publishing with a custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).

Note: in the settings, make sure to set the Pages deployment source to **GitHub Actions**:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/99676430-884e-42ab-b901-f6534a0d6eee" width=600 />

[Run the workflow manually](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow) if it's not triggered automatically.

### Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/imfing/hextra-starter-template)

### Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fimfing%2Fhextra-starter-template&env=HUGO_VERSION)

Override the configuration:

<img src="https://github.com/imfing/hextra-starter-template/assets/5097752/e2e3cecd-c884-47ec-b064-14f896fee08d" width=600 />

## Local Development

Pre-requisites: [Hugo](https://gohugo.io/getting-started/installing/), [Go](https://golang.org/doc/install) and [Git](https://git-scm.com)

```shell
# Clone the repo
git clone https://github.com/imfing/hextra-starter-template.git

# Change directory
cd hextra-starter-template

# Start the server
hugo mod tidy
hugo server --logLevel debug --disableFastRender -p 1313
```

### Update theme

```shell
hugo mod get -u
hugo mod tidy
```

See [Update modules](https://gohugo.io/hugo-modules/use-modules/#update-modules) for more details.

## Traduções (i18n)

O site é multilíngue, com o português (pt-br) como idioma padrão e traduções em inglês e espanhol:

| Idioma | Código | URL |
| --- | --- | --- |
| Português (Brasil) | `pt-br` | `/` |
| English | `en` | `/en/` |
| Español | `es` | `/es/` |

### Como funciona

- Os idiomas são declarados em `hugo.yaml` (seção `languages`). O `defaultContentLanguage: pt-br` faz o português ser servido na raiz, enquanto os demais idiomas ganham um prefixo (`/en/`, `/es/`).
- Cada idioma tem seu próprio menu principal (ex.: "Sobre" em pt-br, "About" em inglês e "Sobre mí" em espanhol).
- Os textos da interface do tema (botões de busca, tema, idioma, "última atualização", etc.) ficam em `i18n/<idioma>.yaml`. Os arquivos do projeto sobrescrevem as chaves do tema Hextra e as demais chaves continuam vindo do tema.
- A navbar do Hextra monta o seletor de idiomas a partir da seção `languages` do `hugo.yaml`. Caso ele não apareça, verifique a versão do tema.

### Traduzir uma página

Hugo usa o sufixo de idioma no nome do arquivo. O arquivo sem sufixo pertence ao `defaultContentLanguage`:

```text
content/blog/_post-1.md      # pt-br (idioma padrão, servido em /blog/_post-1/)
content/blog/_post-1.en.md   # inglês (servido em /en/blog/_post-1/)
content/blog/_post-1.es.md   # espanhol (servido em /es/blog/_post-1/)
```

Para publicar um post novo nos três idiomas, crie os três arquivos com o mesmo nome base. Os links internos com `ref`/`relref` apontam automaticamente para a página equivalente no idioma corrente.

### Pré-visualizar

```shell
hugo server
```

Depois acesse `http://localhost:1313/` (pt-br), `http://localhost:1313/en/` e `http://localhost:1313/es/`.
