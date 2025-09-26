# Guia de Contribuição — English Lab

Bem-vindo(a)! Este projeto foi pensado para ser colaborativo, modular e fácil de evoluir.  
Aqui você encontra as boas práticas, padrões de branch/PR, exemplos reais e dicas para contribuir de forma eficiente.

---

## Índice

- [Como começar](#como-começar)
- [Padrão de branch e PR](#padrão-de-branch-e-pr)
- [Checklist para Pull Request](#checklist-para-pull-request)
- [Como abrir uma issue](#como-abrir-uma-issue)
- [Estrutura de commits](#estrutura-de-commits)
- [Boas práticas de código](#boas-práticas-de-código)
- [Automação e testes](#automação-e-testes)
- [Onboarding rápido](#onboarding-rápido)
- [Links úteis](#links-úteis)

---

## Como começar

1. **Fork o repositório:**  
   - Clique em "Fork" no topo da página, se quiser trabalhar isoladamente.
   - Ou clone direto se já tiver acesso de escrita.

2. **Clone o projeto localmente:**  
    ```bash
    git clone https://github.com/pali-hub/english-lab.git
    cd english-lab
    ```

3. **Instale as dependências:**  
   - Frontend:  
     ```bash
     cd apps/web
     pnpm install
     ```
   - Parser Python:  
     ```bash
     cd libs/parser
     poetry install
     ```

4. **Confira o [usage.md](./usage.md) para comandos reais e exemplos.**

---

## Padrão de branch e PR

- **Branch principal:**  
  - Não faça commits diretos na `main` (ou `master`).  
- **Crie branches descritivos:**  
  - `feature/nome-da-feature`
  - `fix/descricao-do-bug`
  - `docs/atualiza-guia`
- **Sempre faça PRs pequenos e objetivos.**  
- **Inclua uma descrição clara no PR:**  
  - O que mudou, por quê, como testar.

### Exemplo de comandos:
```bash
git checkout -b feature/parser-novo-formato
git add .
git commit -m "feat(parser): suporta novo formato de resposta"
git push origin feature/parser-novo-formato
```

---

## Checklist para Pull Request

- [ ] O código está lintado (rodou o lint.yml)?
- [ ] Os testes unitários passaram (test.yml)?
- [ ] Incluiu ou atualizou testes relevantes?
- [ ] Atualizou a documentação se necessário?
- [ ] Não incluiu dados sensíveis ou grandes fora do Git LFS?
- [ ] A descrição explica o motivo da mudança e como testar?

---

## Como abrir uma issue

- Use os templates de [bug_report.md](../.github/ISSUE_TEMPLATE/bug_report.md), [feature_request.md](../.github/ISSUE_TEMPLATE/feature_request.md) ou [question.md](../.github/ISSUE_TEMPLATE/question.md).
- Seja objetivo no título e claro na descrição.
- Adicione passos para reproduzir, prints, anexos ou exemplos se possível.
- Marque o tipo (bug, feature, dúvida) e prioridade.

---

## Estrutura de commits

- Use o padrão [Conventional Commits](https://www.conventionalcommits.org/pt/v1.0.0/):
    - `feat`: nova funcionalidade
    - `fix`: correção de bug
    - `docs`: documentação
    - `chore`: tarefas internas
    - `refactor`: melhorias no código
    - `test`: adiciona ou corrige testes

### Exemplos:
```bash
git commit -m "feat(web): adiciona cálculo automático do CEFR"
git commit -m "fix(parser): resolve erro ao normalizar respostas"
git commit -m "docs(usage): inclui exemplo real de exportação"
```

---

## Boas práticas de código

- Respeite o padrão de cada módulo (ver README de cada pasta).
- Evite duplicação de lógica.
- Comente apenas quando necessário — prefira código autoexplicativo.
- Siga o padrão dos arquivos de configuração (`pyproject.toml`, `package.json`, etc).
- Se criar novo módulo/lib/app, siga a estrutura sugerida em [architecture.md](./architecture.md).

---

## Automação e testes

- Sempre rode os testes antes de abrir PR:
    - Frontend: `pnpm test`
    - Python: `poetry run pytest`
- Workflows automáticos (CI/CD) farão lint, test e validação de JSONs.
- Se adicionar novo workflow, explique no PR ou na documentação.

---

## Onboarding rápido

- Consulte [docs/README.md](./README.md) para índice da documentação.
- Veja exemplos em [usage.md](./usage.md).
- Dúvidas? Abra uma issue de tipo "question" ou participe das discussões.

---

## Links úteis

- [architecture.md](./architecture.md) — Estrutura técnica e modular
- [usage.md](./usage.md) — Exemplos reais de uso
- [roadmap.md](./roadmap.md) — Planejamento e evolução
- [templates/json/](../templates/json/) — Modelos de dados
- [.github/workflows/](../.github/workflows/) — Automação CI/CD

---

**Obrigado por contribuir!**  
Ajude a manter o projeto organizado, colaborativo e escalável 🚀  
Qualquer sugestão de melhoria neste guia é bem-vinda — basta abrir um PR ou uma issue.
