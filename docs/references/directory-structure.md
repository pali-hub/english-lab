## 2. Estrutura dos Diretórios

A seguir, a estrutura definitiva do projeto e o propósito de cada pasta.

---

## Estrutura Definitiva

```
english-lab/
├── apps/
│   ├── web/                  # Frontend Next.js ou Vite
│   │   ├── public/
│   │   │   └── data/         # JSONs das provas
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   └── __tests__/ # Testes de componentes
│   │   │   ├── pages/
│   │   │   ├── styles/
│   │   │   └── utils/
│   │   ├── package.json
│   │   └── README.md
│   └── backend/              # Futuro: API/serviços (FastAPI, etc.)
│       ├── src/
│       ├── tests/
│       ├── pyproject.toml
│       └── README.md
│
├── libs/                     # Scripts Python como bibliotecas
│   └── parser/
│       ├── src/
│       ├── data/
│       │   ├── raw/          # PDFs originais (Git LFS)
│       │   │   └── README.md
│       │   └── processed/    # JSONs gerados
│       ├── notebooks/
│       ├── tests/
│       ├── pyproject.toml
│       └── README.md
│
├── templates/
│   ├── json/
│   └── csv/
│
├── output/
│   ├── reports/
│   └── logs/
│
├── docs/
│   ├── architecture.md
│   ├── usage.md
│   ├── contribution.md
│   ├── roadmap.md
│   ├── images/
│   │   └── exemplo-uso.png
│   └── README.md
│
├── config/
│   ├── web/
│   │   └── tailwind.config.js
│   ├── parser/
│   │   └── parser_config.yaml
│   └── vite.config.ts
│
├── .github/
│   ├── workflows/
│   │   ├── lint.yml
│   │   ├── test.yml
│   │   ├── build.yml
│   │   ├── deploy.yml
│   │   └── validate-json.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── question.md
│   └── PULL_REQUEST_TEMPLATE.md
│
├── tests/
│   └── integration/
│
├── Makefile
├── README.md
├── LICENSE
└── .gitignore
```

---

## Propósito de cada pasta

### apps/
**web/**: Frontend (Next.js/Vite), interface principal do usuário  
**backend/**: Backend/API (FastAPI, futuro)

### libs/
**parser/**: Scripts Python para extração e normalização das provas

### templates/
Modelos JSON/CSV para padronizar dados

### output/
Relatórios e logs gerados automaticamente

### docs/
Documentação técnica, exemplos de uso, contribuições e roadmap

### config/
Configurações separadas por módulo (ex: Tailwind, parser)

### .github/
Workflows de CI/CD, templates de issues e pull requests

### tests/
Testes integrados entre módulos

### Arquivos da raiz
Makefile, README principal, licença e gitignore

---

## Por que monorepo modular?

- **Facilita reuso e manutenção**
- **Permite automação centralizada**
- **Organização clara para múltiplas tecnologias**
- **Escalabilidade e onboarding facilitados**
- **Garante evolução sem retrabalho**

---

Consulte também o [architecture.md](./architecture.md) e o [usage.md](./usage.md).