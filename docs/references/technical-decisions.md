## 4. Decisões Técnicas e Ferramentas

### Frontend (`apps/web`)
- **Framework:** Next.js  
  - Justificativa: Suporte SSR e SSG, ótima integração com React, comunidade forte, fácil deploy (Vercel/Cloudflare).
- **Linter:** ESLint + Prettier
- **Testes:** Jest + Testing Library (unitários), Cypress (e2e)
- **Coverage:** Jest Coverage
- **Styles:** TailwindCSS
- **Gerenciador de pacotes:** pnpm (mais rápido e workspace-friendly)
- **Deploy:** Vercel ou Cloudflare Pages (automatizado via GitHub Actions)

### Backend (`apps/backend`)
- **Framework:** FastAPI  
  - Justificativa: Rápido, tipado, docs automáticas, fácil integração com Python libs.
- **Testes:** pytest + pytest-cov
- **Lint:** flake8 + black + isort
- **Gerenciador de dependências:** Poetry
- **Deploy:** Render, Railway, ou serverless (Cloudflare Workers/Functions)
- **Coverage:** pytest-cov

### Libs Python (`libs/parser`)
- **Scripts:** Python 3.11+
- **Testes:** pytest
- **Lint:** flake8 + black
- **Notebooks:** Jupyter (para protótipos e análises)
- **Dependências:** Poetry

### Dados/Assets
- **Versionamento de PDFs:** Git LFS
- **Validação de JSON:** jq (CLI) + workflows customizados (GitHub Actions)
- **Templates:** Modelos JSON/CSV versionados em `templates/`

### Automação e CI/CD
- **Orquestração:** GitHub Actions
  - Workflows para lint, test, build, deploy, validação de dados.
- **Makefile/justfile:** Scripts globais para comandos padronizados (test, lint, build, etc).

### Documentação
- **Docs:** Markdown (`docs/`), diagramas em Mermaid e screenshots reais.
- **Roadmap:** Markdown + issues GitHub
- **Onboarding:** CONTRIBUTING.md + templates GitHub

---

### Por que essas escolhas?

- **Next.js + Tailwind:** Rapidez, reuso, comunidade forte, fácil deploy.
- **FastAPI:** Moderno, tipado, docs automáticas, fácil integração Python.
- **Poetry/pnpm:** Gerenciadores modernos, facilitam workspace e múltiplos módulos.
- **GitHub Actions:** Automatização total e grátis para open source.
- **Jest/pytest:** Ferramentas líderes para testes e coverage.
- **Lint/Format:** Padrão de qualidade, evita retrabalho e divergências.
- **Git LFS:** Essencial para dados grandes (PDFs, áudios).

---

**Links úteis:**  
- [Next.js](https://nextjs.org/)  
- [FastAPI](https://fastapi.tiangolo.com/)  
- [Poetry](https://python-poetry.org/)  
- [pnpm](https://pnpm.io/)  
- [GitHub Actions](https://docs.github.com/actions)

---

Consulte também o [architecture.md](./architecture.md) para detalhes da estrutura.