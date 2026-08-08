# CodeX Docs Theme Rokain — Arquitetura

## 1. Objetivo

Este documento descreve a estrutura interna do CodeX Docs utilizada
como base para o desenvolvimento do tema Rokain.

O objetivo é identificar os arquivos responsáveis pela interface,
recursos visuais, configuração e comportamento da aplicação.

---

## 2. Ambiente analisado

### Aplicação

CodeX Docs

### Versão da imagem

`ghcr.io/codex-team/codex.docs:v2.2`

### Ambiente

Runtipi

### Container

`ab4184163a6e`

### Diretório da aplicação

`/usr/src/app`

---

## 3. Estrutura principal

```text
/usr/src/app
├── db/
├── dist/
├── docs-config.yaml
├── node_modules/
├── public/
└── uploads/

---

## 4. Configuração

Arquivo:

/usr/src/app/docs-config.yaml

Este arquivo é montado pelo Runtipi a partir de:

/root/runtipi/app-data/migrated/codex-docs/data/docs-config.yaml

A configuração permite alterar propriedades da aplicação sem modificar
diretamente o código-fonte.

---

## 5. Frontend

Os recursos públicos do frontend estão localizados em:

/usr/src/app/public/
Arquivos principais
public/
├── favicon.png
└── dist/
    ├── main.css
    ├── main.bundle.js
    ├── editor.bundle.js
    ├── table-of-content.bundle.js
    └── code-styling.css

---
## 6. SVG

Os SVG utilizados pela interface estão em:

/usr/src/app/dist/frontend/svg/

Arquivos identificados:

pencil.svg
search.svg
arrow-right.svg
loader.svg
copy.svg
trash.svg
frog.svg
arrow-left.svg
arrow-up.svg
plus.svg
aside-logo.svg
menu.svg
arrow-down.svg
check.svg
Logo principal da sidebar
/usr/src/app/dist/frontend/svg/aside-logo.svg

Este arquivo é utilizado pelo componente da sidebar.

---

## 7. Backend

O backend está localizado em:

/usr/src/app/dist/backend/

Principais áreas:

backend/
├── controllers/
├── database/
├── exceptions/
├── models/
├── routes/
├── uploads/
├── utils/
├── views/
├── app.js
└── server.js

---

## 8. Templates Twig

A interface HTML utiliza templates Twig.

Diretório:

/usr/src/app/dist/backend/views/
Layout
layout.twig

Responsável pela estrutura geral das páginas.

Componentes
components/
├── sidebar.twig
├── header.twig
├── navigator.twig
├── sidebar-section.twig
├── button.twig
└── copy-button.twig

___

## 9. Sidebar

Arquivo:

/usr/src/app/dist/backend/views/components/sidebar.twig

Responsabilidades identificadas:

Renderização da sidebar.
Logo.
Navegação.
Informações de versão.
Rodapé.
Texto "Powered by CodeX Docs".

---

## 10. Header

Arquivo:

/usr/src/app/dist/backend/views/components/header.twig

Responsável pelos elementos do cabeçalho da aplicação.

---

## 11. CSS

Arquivo principal:

/usr/src/app/public/dist/main.css

Este arquivo controla grande parte da aparência da interface.

Elementos identificados incluem:

Header
Sidebar
Logo
Navegação
Conteúdo
Botões
Formulários
Responsividade

---

## 12. JavaScript

Principais bundles:

/usr/src/app/public/dist/
├── main.bundle.js
├── editor.bundle.js
├── table-of-content.bundle.js
└── code-styling.bundle.js

O JavaScript será modificado somente quando a personalização via
Twig/CSS não for suficiente.

---

## 13. Arquivos prioritários para o tema

Os seguintes arquivos são considerados prioritários:

Arquivo	Função	Prioridade
aside-logo.svg	Logo	Alta
sidebar.twig	Sidebar/Rodapé	Alta
header.twig	Cabeçalho	Alta
layout.twig	Estrutura geral	Alta
main.css	Estilo	Alta
favicon.png	Favicon	Média
main.bundle.js	Comportamento	Baixa

---

## 14. Estratégia de personalização

O tema Rokain deverá evitar alterações desnecessárias na lógica
principal do CodeX Docs.

A prioridade será:

Configuração YAML
SVG
Templates Twig
CSS
JavaScript

JavaScript compilado deverá ser alterado somente quando não houver
outra alternativa.

---

## 15. Persistência

Os arquivos personalizados deverão ser mantidos fora do container.

Diretório planejado:

/opt/projects/codex-docs-theme-rokain/

O projeto Git armazenará:

Tema.
Scripts.
Documentação.
Configurações.
Testes.

Os arquivos originais do CodeX Docs não deverão ser versionados
desnecessariamente.

---

## 16. Objetivo final

Criar um tema reutilizável chamado:

CodeX Docs Theme Rokain

O tema deverá permitir:

Personalização do logo.
Personalização do favicon.
Personalização das cores.
Personalização do header.
Personalização da sidebar.
Personalização do rodapé.
CSS personalizado.
Instalação automatizada.
Backup e restauração.
Atualização do tema.
Compatibilidade com instalações Docker/Runtipi.
