# Edu Store

Loja front-end simples para exibir produtos e enviar pedido via WhatsApp.

## Rápido
- Página de entrada: [index.html](index.html)  
- Estilos principais: [src/css/style.css](src/css/style.css) e o CSS gerado por Tailwind [src/css/output.css](src/css/output.css)  
- Lógica do carrinho: [src/script/script.js](src/script/script.js) — principais funções: [`addToCart`](src/script/script.js), [`updateCartModal`](src/script/script.js), [`checkRest`](src/script/script.js)  
- Configuração do Tailwind: [tailwind.config.js](tailwind.config.js)  
- Script npm para desenvolvimento: [`scripts.dev`](package.json) em [package.json](package.json)

## Requisitos
- Node.js + npm (para gerar o CSS do Tailwind, opcional para rodar local estático)

## Desenvolvimento
1. Instale dependências (opcional, só para Tailwind):
   npm install
2. Gere/observe o CSS do Tailwind (converte [src/css/style.css](src/css/style.css) para [src/css/output.css](src/css/output.css)):
   npm run dev
   (usa o script [`scripts.dev`](package.json) em [package.json](package.json))
3. Abra [index.html](index.html) no navegador (pode usar Live Server ou abrir direto).

## Como funciona
- A interface lista produtos em [index.html](index.html).
- Botões "add-to-cart" chamam a função [`addToCart`](src/script/script.js) em [src/script/script.js] que adiciona itens ao array do carrinho.
- O modal do carrinho é atualizado por [`updateCartModal`](src/script/script.js) e exibe total (formatado em BRL).
- Ao finalizar, o pedido é preparado e enviado via WhatsApp (abre uma nova aba com a URL de envio).
- O estado "Aberto / Fechado" é calculado por [`checkRest`](src/script/script.js) e controla os elementos com id `data-span` e `data-span-close` em [index.html](index.html).

## Estrutura do projeto
- index.html — entrada da aplicação ([index.html](index.html))
- src/
  - script/script.js — lógica do cliente ([src/script/script.js](src/script/script.js))
  - css/style.css — arquivo fonte com diretivas do Tailwind ([src/css/style.css](src/css/style.css))
  - css/output.css — CSS gerado ([src/css/output.css](src/css/output.css))
  - img/ — imagens do catálogo (ver [src/img](src/img) na árvore do projeto)
- tailwind.config.js — configuração do Tailwind ([tailwind.config.js](tailwind.config.js))
- package.json — script de desenvolvimento (`dev`) ([package.json](package.json))

## Notas
- O envio de pedido abre o WhatsApp com o número fixo presente em [src/script/script.js](src/script/script.js).
- Trocar o número e adaptar a mensagem pode ser feito em [src/script/script.js](src/script/script.js).
- Para produção estática basta servir `index.html` e os arquivos em `src/`.

## Licença
Projeto pessoal — adaptar conforme necessário.