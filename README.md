# English Lab

[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/pali-hub/english-lab/ci.yml?branch=main)](https://github.com/pali-hub/english-lab/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/pali-hub/english-lab/blob/main/LICENSE)
[![Contributors](https://img.shields.io/github/contributors/pali-hub/english-lab)](https://github.com/pali-hub/english-lab/graphs/contributors)

# Plataforma de idiomas grátis no Brasil para melhorar o acesso a educação


Plataforma open source para praticar e corrigir provas oficiais de inglês (IELTS, TOEFL, Cambridge, etc).  
Extraia questões de exames reais, corrija localmente, exporte relatórios e contribua com a evolução do laboratório!

---

## 🚀 Visão Geral

- Correção automática, Band Score e CEFR estimados
- Frontend Next.js/Vite + TailwindCSS
- Parser Python para extração de PDFs
- Monorepo modular, fácil de expandir e contribuir
- Hospedagem gratuita (Cloudflare Pages)
- Automação total via GitHub Actions (CI/CD)

---

## 📦 Estrutura do Projeto

```
english-lab/
├── apps/           # Frontend e futuros apps
├── libs/           # Scripts, parsers e libs Python
├── templates/      # Modelos de dados (JSON/CSV)
├── output/         # Relatórios e logs gerados
├── docs/           # Documentação completa
├── config/         # Configs separadas
├── .github/        # Workflows e templates automáticos
├── tests/          # Testes integrados
├── README.md       # Este arquivo
├── LICENSE
└── .gitignore
```
Explore a [estrutura completa e propósito de cada pasta](./docs/02.estrutura.md).

---

## 💻 Guia Rápido de Instalação

```bash
# Instale dependências do frontend
cd apps/web
npm install

# Instale dependências do parser Python
cd ../../libs/parser
poetry install

# Volte à raiz e configure conforme [usage.md](./docs/usage.md)
```

---

## 📝 Documentação

- [Documentação técnica](./docs/README.md)
- [Arquitetura detalhada](./docs/architecture.md)
- [Guia de contribuição](./docs/contribution.md)
- [Roadmap de evolução](./docs/roadmap.md)
- [Exemplos de uso](./docs/usage.md)
- [Templates de dados](./templates/)

---

## 🎬 Exemplo de Uso

```bash
# Executar parser para extrair questões de um PDF
poetry run python src/main.py data/raw/exemplo.pdf

# Rodar frontend localmente
cd apps/web
npm run dev
```
Veja mais exemplos em [docs/usage.md](./docs/usage.md).

---

## 🤝 Como contribuir

- Leia o [CONTRIBUTING.md](./CONTRIBUTING.md)
- Use os templates automáticos de issues e PRs
- Faça PRs pequenos, claros e bem testados
- Dúvidas? [Abra uma issue](https://github.com/pali-hub/english-lab/issues) ou [inicie uma discussão](https://github.com/pali-hub/english-lab/discussions)

---

## 📋 Licença

MIT — uso livre, colaboração incentivada!

---

## 🔗 Links rápidos

- [Issues](https://github.com/pali-hub/english-lab/issues)
- [Discussões](https://github.com/pali-hub/english-lab/discussions)
- [GitHub Projects (Roadmap Visual)](https://github.com/pali-hub/english-lab/projects)
- [Demo Cloudflare Pages](#) <!-- Adicione link se tiver demo online -->

---

**Colabore, sugira, evolua — este laboratório é seu também!**
