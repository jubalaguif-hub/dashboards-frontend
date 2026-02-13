# Gestão de Planilhas e Categorias – Front-end

Interface web para gerenciar **planilhas (dashboards)** e **categorias**, consumindo a API Flask hospedada no Render.

Repositório: `https://github.com/jubalaguif-hub/dashboards-frontend`

Front publicado via **GitHub Pages**.

---

## Tecnologias

- HTML5
- CSS3 (layout responsivo e moderno)
- JavaScript (ES6, `fetch` API)
- Integração com API REST

---

## Estrutura

- `index.html` – página principal (layout, sidebar, modais).
- `style.css` – estilos visuais e responsividade.
- `app.js` – lógica de front-end e integração com a API.
- `img/` – imagens e logo.

---

## Como funciona

- A **sidebar** lista as categorias cadastradas.
- O usuário pode:
  - Criar/editar/deletar **categorias**.
  - Criar/editar/deletar **planilhas** associadas a uma categoria.
- As planilhas aparecem como **cards**, cada um podendo ter:
  - título,
  - link para o Google Sheets,
  - imagem opcional de fundo (URL externa ou `/img/arquivo.png`).

Toda a persistência de dados é feita pela **API back-end**  
(`dashboards-backend`); o front apenas consome esses endpoints.

---

## Configuração da URL da API

A URL base da API é configurada diretamente no `index.html`:

```html
<script>
  // Backend publicado no Render
  window.API_BASE_URL = 'https://dashboards-backend-m8mv.onrender.com';
</script>
```

Se o endereço do back-end mudar (outro serviço ou domínio), basta alterar
esse valor e publicar novamente.

---

## Como rodar localmente

1. Clonar este repositório:

   ```bash
   git clone https://github.com/jubalaguif-hub/dashboards-frontend.git
   cd dashboards-frontend
   ```

2. Garantir que o back-end esteja rodando (local ou em produção).

3. Abrir o `index.html` diretamente no navegador **ou** servir com um servidor estático simples:

   ```bash
   # Exemplo com Python 3
   python -m http.server 8000
   ```

   Depois acessar:

   ```text
   http://localhost:8000/
   ```

Se for usar o back-end local (por exemplo, Flask em `http://localhost:5000`),  
é só ajustar em `index.html`:

```html
<script>
  window.API_BASE_URL = 'http://localhost:5000';
</script>
```

---

## Deploy no GitHub Pages

Este repositório está preparado para ser publicado no GitHub Pages.

1. Código na branch `main`.
2. Em **Settings → Pages** do repositório:
   - Source: **Deploy from a branch**
   - Branch: `main` / pasta `/root`.
3. O GitHub gera uma URL semelhante a:

   ```text
   https://github.com/jubalaguif-hub/dashboards-frontend
   ```

Quando um usuário acessa essa URL, o front consome a API apontada em
`window.API_BASE_URL` (por padrão, o back-end no Render).


