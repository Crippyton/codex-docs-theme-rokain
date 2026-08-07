# Estrutura do CodeX Docs

## Diretório principal

```
/usr/src/app
```

### public/

Arquivos públicos da aplicação.

```
favicon.png
dist/
```

### public/dist/

Arquivos compilados do frontend.

```
main.css
main.bundle.js
editor.bundle.js
table-of-content.bundle.js
```

### dist/frontend/

Recursos SVG.

```
aside-logo.svg
menu.svg
search.svg
...
```

### dist/backend/

Código do backend.

```
controllers/
routes/
models/
views/
utils/
```

### Views

```
layout.twig
header.twig
sidebar.twig
navigator.twig
```

### Uploads

```
/usr/src/app/uploads
```

### Banco

```
MongoDB
```

### Configuração

```
docs-config.yaml
```
