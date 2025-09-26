## 3. Fluxos principais deste projeto específico

### 3.1 Fluxo de Dados

O pipeline de dados é o coração do projeto, garantindo que provas oficiais sejam extraídas, normalizadas e disponibilizadas para uso no frontend.

**Resumo dos passos:**

1. **Coleta dos PDFs**  
   - Provas oficiais são obtidas e armazenadas em `libs/parser/data/raw/`.
   - PDFs grandes são versionados usando Git LFS.

2. **Processamento via Parser Python**  
   - Scripts em `libs/parser/src/` extraem questões e respostas dos PDFs.
   - Dados extraídos são normalizados e salvos como JSON em `libs/parser/data/processed/`.

3. **Movimentação para Frontend**  
   - JSONs validados são copiados para `apps/web/public/data/`.
   - O frontend consome esses arquivos para exibir provas, corrigir respostas e gerar relatórios.

4. **Validação Automática**  
   - Workflow GitHub Actions (`.github/workflows/validate-json.yml`) verifica integridade dos JSONs gerados e usados.

**Diagrama do fluxo de dados:**

```
PDF (raw) ──> Parser Python ──> JSON (processed) ──> Frontend (Web) ──> Usuário
       ▲                                     │
       └───────────<── Validação CI/CD ──────┘
```

---

### 3.2 Fluxo de Testes

**Testes Unitários:**  
- Cada módulo possui testes próprios:
  - Frontend (`apps/web/src/components/__tests__`): Jest + Testing Library.
  - Parser/back-end (`libs/parser/tests` e `apps/backend/tests`): pytest.

**Testes Integrados:**  
- Validados em `tests/integration/` para garantir comunicação entre parser, frontend e backend.

**Automação CI/CD:**  
- Workflows em `.github/workflows/` automatizam:
  - Lint de código (lint.yml)
  - Execução dos testes unitários e integrados (test.yml)
  - Validação dos dados JSON (validate-json.yml)
  - Build do frontend/backend (build.yml)
  - Deploy do frontend (deploy.yml)

**Cobertura de testes:**  
- Ferramentas como Jest Coverage e pytest-cov garantem rastreio do que está sendo testado.

---

### 3.3 Fluxo de Deploy

**Frontend:**  
- O código do frontend é publicado automaticamente em **Cloudflare Pages** a cada push na branch principal.
- O workflow (`deploy.yml`) faz o build, valida os dados e realiza o deploy contínuo sem intervenção manual.

**Backend (futuro):**  
- A API poderá ser hospedada em serviços serverless ou plataformas gratuitas como Render/Railway, com deploy via workflow dedicado.

---

**Resumo visual dos fluxos:**

```
[PDF/raw] 
   │
   ▼
[Parser Python] ──> [JSON/processed] ──> [Frontend/public/data] ──> [Usuário]
   │                                │
   │                                └──> [Validação e Testes CI/CD]
   │
   └──> [Testes Unitários e Integrados]
```

**Deploy:**  
- Frontend: Cloudflare Pages automatizado  
- Backend: Serverless/API (planejado)

---

Consulte exemplos reais de uso em [usage.md](./usage.md).