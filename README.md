# TGS Site (TGS Store)

Site estático da **TGS Store** (landing page + catálogo simples), feito em **HTML/CSS/JS** sem bundler.

## Como visualizar (dev)

- **Opção 1 (simples)**: abrir o `index.html` no navegador.
  - Observação: alguns navegadores podem restringir carregamento de recursos locais dependendo do caminho. Se algo falhar, use a opção 2.
- **Opção 2 (recomendado)**: servir com um “live server” (ex.: extensão Live Server do VSCode/Cursor) apontando para a pasta `TGS Site/`.

## Estrutura

O projeto está organizado por “seções” (cada pasta tende a ter seu CSS/JS):

- `index.html`: página principal, inclui os CSS por seção e os scripts.
- `header/`: estilos e scripts do header (desktop/mobile).
- `hero/`, `products/`, `features/`, `About/`, `Footer/`: estilos por seção.
- `animations/`: animações (IntersectionObserver para fade-in).
- `utils/`: utilitários (ex.: notificações).
- `midias/`: imagens/ícones e mídias dos produtos (referenciadas no JS).

## Catálogo / produtos

O catálogo é carregado via JavaScript:

- **Fonte de dados**: `products/products.js` (array `products`).
- **Renderização**: cards são criados e inseridos no `#productsGrid`.
- **Filtros**: botões com `data-filter` filtram por `category` (`scripts`, `mods`, `graphics`, ou `all`).
- **Modal**: `openProductModal(productId)` abre detalhes.

### Adicionando um produto

Edite `products/products.js` e inclua um item no array `products`:

- `id`: número único
- `name`: nome do produto
- `category`: `scripts` | `mods` | `graphics`
- `price`: string (ex.: `US$ 20.00`)
- `description`: texto
- `features`: lista de bullets
- `media`: lista de mídias (imagens) com `src` apontando para `midias/...`

## Mídias / assets

Coloque imagens em `midias/` e referencie via caminho relativo (ex.: `midias/products/...`).

## Deploy

Como é estático, dá pra publicar em qualquer host de arquivos estáticos (GitHub Pages, Cloudflare Pages, Netlify, Nginx/Apache).

