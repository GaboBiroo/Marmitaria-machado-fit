# Marmitaria Machado Fit 🍱💪

Sistema moderno de autoatendimento e pedidos online de marmitas fitness, saladas e sucos. Permite aos clientes adicionarem itens ao carrinho de compras de forma dinâmica e efetuarem pedidos com envio e integração direta via WhatsApp.

---

## 🛠️ Stack Tecnológica (Backend & Frontend)

A aplicação está localizada no diretório `marmitaria-marchado-fit/` e adota as tecnologias mais recentes do ecossistema Javascript:

*   **Framework Core:** `Next.js 16` (App Router) integrado com `React 19`.
*   **Gerenciamento de Estado:** `Zustand` para um carrinho de compras reativo e veloz.
*   **Estilização:** `Tailwind CSS v4` com `@tailwindcss/postcss` para renderização otimizada de layouts modernos e responsivos.
*   **Animações:** `Framer Motion` para transições fluidas e microinterações premium.
*   **Banco de Dados & ORM:** `Prisma Client` mapeado com banco de dados local `SQLite` (`prisma/schema.prisma`).
*   **Manipulação de Datas:** `date-fns`.
*   **Ícones:** `Lucide React`.

---

## 📂 Estrutura do Repositório

*   `marmitaria-marchado-fit/`: O projeto de código-fonte Next.js.
    *   `src/app/`: Roteamento e páginas da aplicação (Admin, API de Pedidos, Home).
    *   `src/components/`: Componentes modulares reutilizáveis (layouts, CartDrawer, etc.).
    *   `prisma/`: Arquivos de migração e o arquivo `schema.prisma` que define as tabelas `Product`, `Order` e `OrderItem`.
    *   `fetch_*.js`: Scripts independentes de seed para consumir e popular dados de APIs de alimentos (MealDB, Wikipedia, Unsplash).
*   `documentos_e_midias/`: Pasta que organiza arquivos e registros auxiliares enviados durante o desenvolvimento, como comprovantes de endereço, áudios explicativos do WhatsApp e especificações do projeto (`tarefa.pdf`), garantindo a limpeza da raiz do workspace.

---

## 🚀 Como Executar o App Localmente

### 1. Configurar o Ambiente
Entre na pasta do aplicativo Next.js:
```bash
cd marmitaria-marchado-fit
```

Instale as dependências npm:
```bash
npm install
```

Configure o arquivo `.env`:
```bash
cp .env.example .env
```
*(Nota: Certifique-se de preencher a URL de banco de dados apropriada, por padrão: `file:./dev.db`)*

### 2. Banco de Dados & Seed
Gere o Prisma Client localmente:
```bash
npx prisma generate
```

Crie as tabelas e execute as migrations no SQLite:
```bash
npx prisma db push
```

(Opcional) Popule o banco rodando os scripts de fetch de alimentos:
```bash
node fetch_local.js
```

### 3. Rodar em Modo Desenvolvimento
Inicie o servidor de desenvolvimento Next.js:
```bash
npm run dev
```

Abra `http://localhost:3000` no seu navegador para visualizar e testar o sistema de marmitas.
Para o painel do administrador de pedidos, acesse `http://localhost:3000/admin`.
