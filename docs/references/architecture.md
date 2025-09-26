# English Lab

Plataforma modular para praticar provas oficiais de inglês (ex: IELTS) e melhorar o idioma online.  
Estrutura monorepo pensada para colaboração, escalabilidade e reuso.

---

## 🧠 Arquitetura

**Monorepo modular**, pronto para multi-framework, multi-linguagem e automação total via CI/CD.  
Tudo foi pensado para facilitar manutenção, colaboração e evolução.

### **Benefícios**

- **Separação clara**: entre frontend, scripts, dados e testes.
- **Reuso garantido**: cada pasta pode evoluir separadamente ou virar pacote independente.
- **Versionamento limpo**: ideal para GitHub, com PRs por módulo.
- **Escalável**: fácil adicionar backend, NLP, uploads ou IA no futuro.
- **Colaborativo**: documentação e templates prontos para onboarding.

---

## Estrutura Definitiva do Projeto

```
english-lab/
├── apps/
│   ├── web/                       # Frontend Next.js ou Vite
│   │   ├── public/
│   │   │   └── data/              # JSONs das provas
│   │   ├── src/
│   │   │   ├── components/
│   │   │   │   └── __tests__/     # Testes próximos aos componentes
│   │   │   ├── pages/
│   │   │   ├── styles/
│   │   │   └── utils/
│   │   ├── package.json           # Dependências do frontend
│   │   └── README.md
│   └── backend/                   # Futuro: API/serviços (FastAPI, etc.)
│       ├── src/
│       ├── tests/
│       ├── pyproject.toml         # Dependências do backend Python
│       └── README.md
│
├── libs/                          # Scripts Python como bibliotecas
│   └── parser/
│       ├── src/
│       │   ├── extract.py
│       │   ├── normalize.py
│       │   └── utils.py
│       ├── data/
│       │   ├── raw/               # PDFs originais (usar Git LFS se necessário)
│       │   │   └── README.md      # Explica formato, uso e limites dos dados
│       │   └── processed/         # JSONs gerados
│       ├── notebooks/
│       ├── tests/
│       ├── pyproject.toml         # Dependências do parser Python
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
│   ├── architecture.md            # Explicação técnica do projeto
│   ├── usage.md                   # Exemplos de uso real, screenshots, links cruzados
│   ├── contribution.md            # Guia de contribuição, onboarding, exemplos de PR e branch
│   ├── roadmap.md                 # Evolução planejada, links para issues
│   ├── images/
│   │   └── exemplo-uso.png        # Screenshots usadas nos tutoriais
│   └── README.md                  # Índice/guia da documentação
│
├── config/
│   ├── web/
│   │   └── tailwind.config.js     # Configurações do frontend
│   ├── parser/
│   │   └── parser_config.yaml     # Configurações do parser Python
│   └── vite.config.ts             # Config global do frontend (se necessário)
│
├── .github/
│   ├── workflows/
│   │   ├── lint.yml               # Lint global ou por módulo
│   │   ├── test.yml               # Testes unitários e integrados
│   │   ├── build.yml              # Build do frontend e outros pacotes
│   │   ├── deploy.yml             # Deploy automatizado
│   │   └── validate-json.yml      # Validação automática dos JSONs das provas
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── question.md
│   └── PULL_REQUEST_TEMPLATE.md
│
├── tests/
│   └── integration/               # Testes integrados entre módulos
│
├── Makefile                       # Comandos padronizados (ou justfile)
├── README.md                      # Visão geral do projeto
├── LICENSE                        # Licença de uso
└── .gitignore                     # Ignora arquivos temporários/secrets

```

---

## 📝 Documentação Técnica e Onboarding

- Em `docs/`, adicione exemplos de uso real, screenshots, links cruzados.
- Garanta que todos os módulos tenham README detalhado.
- Detalhe o fluxo de contribuição em `contribution.md`.
- Explique o roadmap e evolução em `roadmap.md`.

## 🤝 Contribuição

Veja `docs/contribution.md` para onboarding, padrões de PR, templates e workflows.  
Use PRs pequenos e bem documentados.  
Organize tarefas e discussões usando GitHub Projects e Discussions.


## **Checklist de Melhores Práticas**

1. **Nome dos módulos:** scripts Python ficam em `libs/`.
2. **Testes do frontend:** mantenha em `src/components/__tests__`.
3. **Dependências:** `package.json`, `pyproject.toml` dentro dos subdiretórios relevantes; na raiz só se usar workspace global.
4. **Multi-framework/multi-linguagem:** `apps/backend` ou `apps/api` como opção para o futuro.
5. **Automação centralizada:** `Makefile` ou `justfile` na raiz.
6. **Testes integrados:** `tests/integration/`.
7. **Coverage reports:** `pytest-cov` para Python, `Jest` para JS.
8. **Templates GitHub:** arquivos separados para bugs, features, dúvidas e PRs.
9. **Dados versionados:**  
   - Use Git LFS para PDFs grandes em `libs/parser/data/raw/`.
   - README em cada pasta de dados explicando formato, uso e limites.
10. **Configuração modular:** subpastas específicas em `config/` por módulo.
11. **Documentação rica:** exemplos reais, screenshots, links cruzados em `docs/`.
12. **Automatização:**  
    - Workflows para lint, test, build, deploy.
    - Workflow para validação automática dos JSONs das provas.
13. Cada subpasta guarda as configs específicas do módulo correspondente. ejemplo:

```
config/
├── web/
│   └── tailwind.config.js        # Configurações do frontend (Next.js/Vite)
├── parser/
│   └── parser_config.yaml        # Configurações do parser Python
└── vite.config.ts                # Config global (se necessário)

```


14. Coloque um pequeno README.md explicando o propósito das configs, parâmetros importantes e exemplos de uso em cada subpasta se útil.

## **Documentação com exemplos reais, screenshots e links cruzados**

Como estruturar a pasta docs/ para facilitar navegação:

```

├── architecture.md     # Explicação técnica do projeto
├── usage.md            # Exemplos reais de uso, capturas de tela, passo a passo para rodar e testar
├── contribution.md     # Guia de contribuição, onboarding, exemplos de PR e branch
├── roadmap.md          # Evolução planejada, links para issues
├── images/
│   └── exemplo-uso.png # Screenshots usadas nos tutoriais
└── README.md           # Índice/guia da documentação

```

 ## **Documentação com exemplos reais, screenshots e links cruzados**

- Em usage.md, inclua seções como:
- Como rodar o frontend localmente (com comandos reais)
- Fluxo de uso do parser (mostrando saída real, exemplos de comando Python)
- Exemplo de prova corrigida (com captura de tela do relatório gerado)
- Adicione imagens reais em docs/images/ e referencie nos tutoriais

## **Como criar links cruzados entre arquivos** 

No topo ou fim de cada arquivo markdown, adicione links para outros documentos relevantes:

```
Consulte também o [Guia de Contribuição](./contribution.md) ou veja o [Roadmap](./roadmap.md).
```
No README.md da pasta docs/, crie um índice navegável

```
# Documentação English Lab

- [Arquitetura](./architecture.md)
- [Exemplos de Uso](./usage.md)
- [Contribuição](./contribution.md)
- [Roadmap](./roadmap.md)
```

**Dicas:**

- Use exemplos reais de comandos, capturas de tela do produto, outputs de scripts.
- Atualize os links cruzados sempre que adicionar novos arquivos importantes.
- Se possível, use GIFs ou vídeos curtos para tutoriais visuais em docs/images/ (referenciando com ![]).

## Automatização

- **Use workflows do GitHub Actions** para garantir qualidade e automação:
  - Execute lint, test, build e deploy em cada Pull Request (PR) e push na branch principal.
  - Configure workflows específicos para cada módulo (ex: frontend, libs/parser).

- **Exemplo de estrutura em `.github/workflows/`:**
  ```
  .github/
    workflows/
      lint.yml           # Lint global ou por módulo
      test.yml           # Testes unitários e integrados
      build.yml          # Build do frontend e outros pacotes
      deploy.yml         # Deploy automatizado (ex: Vercel, Cloudflare, etc.)
      validate-json.yml  # Validação automática dos arquivos JSON das provas
  ```

- **Workflow para validação dos JSONs das provas:**
  - Crie um arquivo `validate-json.yml` que roda automaticamente em cada PR ou push para verificar se os arquivos em `apps/web/public/data/` estão válidos (sintaxe, formato, schema).
  - Exemplo de etapa no workflow:
    ```yaml
    - name: Valida todos os JSONs das provas
      run: |
        for file in apps/web/public/data/*.json; do
          jq type "$file"
        done
    ```

- **Benefícios:**
  - Garante que erros de formatação não sejam incluídos via PR.
  - Automatiza todo o ciclo de qualidade e entrega contínua.

---

**Resumo das melhores práticas:**
- Sempre mantenha workflows de automação para lint, test, build, e deploy.
- Inclua validação automática dos dados críticos do projeto (ex: JSONs das provas).
- Documente os workflows relevantes na seção de automatização do README.
---

## 📚 Referências

- [Serverless e Jamstack](https://www.jamstack.org/)
- [Guia Monorepo](https://github.com/monorepo/monorepo-guide)
- [Cloudflare Pages com GitHub](https://developers.cloudflare.com/pages/framework-guides/deploy-a-nextjs-site/)
- [GitHub Actions para Next.js](https://github.com/marketplace/actions/deploy-to-cloudflare-pages)
- [Guia de CONTRIBUTING.md](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/adding-a-contributing-file)
- [Dependabot](https://docs.github.com/en/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically)

---

## 📑 Licença

Projeto sob licença [LICENSE](./LICENSE).