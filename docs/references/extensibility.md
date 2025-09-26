## 5. Extensibilidade

Este projeto foi desenhado para facilitar evolução contínua, inclusão de novas tecnologias e colaboração em múltiplas áreas.

---

### Adicionar novos módulos

**Novo parser**
- Crie uma nova pasta em `libs/` (ex: `libs/parser-ielts/` ou `libs/parser-toefl/`).
- Siga o padrão de estrutura: `src/`, `data/raw/`, `data/processed/`, `tests/`, `README.md`.
- Configure dependências em `pyproject.toml` (usando Poetry).
- Adicione testes unitários em `tests/`.
- Atualize os workflows do GitHub Actions para incluir lint e testes desse novo módulo.
- Documente o fluxo e exemplos no `docs/usage.md` e `docs/architecture.md`.

**Novo app**
- Crie uma pasta em `apps/` (ex: `apps/mobile/` para um app React Native ou `apps/cli/` para interface de linha de comando).
- Siga o padrão de estrutura: `src/`, dependências do app, testes, `README.md`.
- Integre o novo app com os dados já processados (JSONs em `libs/` ou API do backend).
- Adicione workflows de CI/CD conforme necessário.
- Documente o novo app em `docs/usage.md` e `docs/architecture.md`.

---

### Evoluir para multi-linguagem/framework

- **Separação física por pasta:** Cada app/lib pode ter sua própria stack (ex: Node.js, Python, Go, Rust), com dependências e configuração isoladas.
- **Gerenciadores de dependência modernos:** Use `pnpm` (Node.js), `Poetry` (Python), ou outros adequados, facilitando o controle por módulo.
- **Configuração modular:** Pastas `config/` por tecnologia garantem ajustes separados e seguros.
- **Workflows customizados:** CI/CD pode ser ajustado para rodar testes, lint e build de múltiplos stacks, usando GitHub Actions.
- **Documentação centralizada:** O `docs/` detalha como cada módulo se relaciona, como instalar e integrar novas tecnologias.
- **Comunicação por API ou dados padronizados:** Módulos de linguagens diferentes podem interagir via API REST (backend) ou arquivos padronizados (ex: JSON, CSV, Avro).

---

**Exemplo prático:**
- Para adicionar um parser em Go para provas Cambridge, crie `libs/parser-cambridge-go/` com estrutura Go, integre o resultado JSON com os apps existentes e configure workflows de build/test para Go.
- Para criar um app mobile, adicione `apps/mobile/` com React Native, consuma os dados via API ou arquivos, e configure deploy/CI próprio.

---

Consulte o [Guia de Contribuição](./contribution.md) para exemplos de PR e onboarding.