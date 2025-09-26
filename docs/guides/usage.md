# Exemplos de Uso — English Lab

Guia rápido para rodar, testar e utilizar os recursos principais do projeto.  
Inclui comandos reais, prints e links cruzados para facilitar seu onboarding.

---

## Índice

- [Rodando o frontend localmente](#rodando-o-frontend-localmente)
- [Fluxo do parser Python](#fluxo-do-parser-python)
- [Como corrigir uma prova](#como-corrigir-uma-prova)
- [Relatórios e exportações](#relatórios-e-exportações)
- [Testes automatizados](#testes-automatizados)
- [Exemplo de CI/CD](#exemplo-de-cicd)
- [Links úteis](#links-úteis)

---

## Rodando o frontend localmente

1. Instale as dependências:
    ```bash
    cd apps/web
    pnpm install
    ```

2. Inicie o servidor de desenvolvimento:
    ```bash
    pnpm dev
    # ou
    npm run dev
    ```

3. Acesse [http://localhost:3000](http://localhost:3000) no navegador.

4. Os arquivos das provas estão em `apps/web/public/data/`.  
   Edite ou adicione novos JSONs conforme necessário.

---

## Fluxo do parser Python

1. Instale as dependências:
    ```bash
    cd libs/parser
    poetry install
    ```

2. Extraia dados de um PDF:
    ```bash
    poetry run python src/extract.py data/raw/sample.pdf
    # Gera um JSON em data/processed/
    ```

3. Normalize os dados:
    ```bash
    poetry run python src/normalize.py data/processed/sample.json
    ```

4. Confira logs e relatórios em `output/reports/` e `output/logs/`.

---

## Como corrigir uma prova

1. No app web, selecione uma prova disponível.
2. Responda as questões na interface.
3. Clique em "Corrigir" para ver o Band Score, CEFR e relatório detalhado.

![Exemplo de uso](./images/exemplo-uso.png)

4. Exporte o resultado clicando em “Exportar CSV” ou “Exportar JSON”.

---

## Relatórios e exportações

- Relatórios detalhados são gerados após a correção.
- Arquivos disponíveis em `output/reports/` ou para download pelo frontend.
- Use os templates de `templates/` para integrar com outros sistemas.

---

## Testes automatizados

- **Frontend:**  
    ```bash
    cd apps/web
    pnpm test
    ```

- **Parser Python:**  
    ```bash
    cd libs/parser
    poetry run pytest
    ```

- **Testes integrados:**  
    ```bash
    cd tests/integration
    # Execute scripts de integração conforme documentado
    ```

---

## Exemplo de CI/CD

- Commits e Pull Requests disparam workflows automáticos em `.github/workflows/`:
    - **lint.yml:** Lint e checagem de padrões
    - **test.yml:** Testes unitários e integrados
    - **build.yml:** Build do frontend/backend
    - **deploy.yml:** Deploy automático (Cloudflare Pages)
    - **validate-json.yml:** Validação dos JSONs das provas

---

## Links úteis

- [architecture.md](./architecture.md) — Estrutura técnica
- [contribution.md](./contribution.md) — Guia de colaboração
- [roadmap.md](./roadmap.md) — Evolução do projeto
- [templates/json/](../templates/json/) — Modelos de dados
- [templates/csv/](../templates/csv/) — Exportação e integração

---

**Dica:**  
Mantenha este arquivo sempre atualizado com novos comandos, prints e fluxos reais!

Consulte o [docs/README.md](./README.md) para navegação completa.