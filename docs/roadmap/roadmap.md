# Roadmap — English Lab

Este roadmap apresenta a evolução planejada do projeto, principais marcos, ideias futuras e links para tarefas e discussões.  
É um guia vivo, atualizado conforme a comunidade contribui e as necessidades mudam.  
Sinta-se livre para sugerir, abrir PR ou issues e participar do crescimento do English Lab!

---

## Índice

- [Visão geral de fases](#visão-geral-de-fases)
- [Linha do tempo dos marcos](#linha-do-tempo-dos-marcos)
- [Ideias futuras e backlog](#ideias-futuras-e-backlog)
- [Como sugerir melhorias](#como-sugerir-melhorias)
- [Links para issues e discussões](#links-para-issues-e-discussões)

---

## Visão geral de fases

### Fase 0 — Infraestrutura base
- Estrutura monorepo modular
- Documentação rica e onboarding
- Workflows CI/CD para lint, test, build e deploy
- Templates de dados e de issues

### Fase 1 — MVP aberto e estático
- Parser funcional para IELTS, PDF → JSON
- Frontend Next.js/Vite exibindo provas e correções
- Correção local, cálculo de Band Score e CEFR
- Deploy gratuito (Cloudflare Pages)

### Fase 2 — Expansão e automação
- Suporte a múltiplos exames (TOEFL, Cambridge, etc.)
- Parser modular e fácil de expandir
- Testes integrados entre parser e frontend
- Validação automática dos dados via workflows

### Fase 3 — Persistência e histórico
- Backend simples (FastAPI) para armazenar resultados
- Banco de dados Postgres ou Blob Storage
- API REST para integração com apps
- Relatórios históricos e dashboards do usuário

### Fase 4 — Upload, IA e personalização
- Upload de novos PDFs via frontend
- Correção semântica com NLP (embeddings, NLI)
- Recomendações personalizadas com AI
- Expansão do frontend para mobile (React Native)

### Fase 5 — Escala e colaboração
- Multi-idioma, multi-framework (Go, Rust, etc.)
- Internacionalização e suporte a outros exames
- Comunidade ativa: projetos, discussões, eventos
- Ferramentas para professores e grupos de estudo

---

## Linha do tempo dos marcos

| Marco                        | Status      | Estimativa   | Tarefa/Issue |
|------------------------------|-------------|--------------|--------------|
| Monorepo inicial             | ✅ Concluído | 2024 Q4      | [#1](../issues/1) |
| Parser IELTS PDF → JSON      | ✅ Concluído | 2024 Q4      | [#2](../issues/2) |
| Frontend MVP                 | ✅ Concluído | 2025 Q1      | [#3](../issues/3) |
| CI/CD inicial                | ✅ Concluído | 2025 Q1      | [#4](../issues/4) |
| Testes unitários e e2e       | ⏳ Em andamento | 2025 Q2      | [#5](../issues/5) |
| Suporte TOEFL/Cambridge      | ⏳ Em andamento | 2025 Q2      | [#6](../issues/6) |
| Backend básico (resultados)  | 🚧 Planejado | 2025 Q3      | [#7](../issues/7) |
| Upload de PDFs               | 🚧 Planejado | 2025 Q3      | [#8](../issues/8) |
| Correção semântica (NLP/AI)  | 🚧 Planejado | 2025 Q4      | [#9](../issues/9) |
| App mobile                   | 🕓 Futuro    | 2026 Q1      | [#10](../issues/10) |
| Internacionalização          | 🕓 Futuro    | 2026+        | [#11](../issues/11) |

---

## Ideias futuras e backlog

- Dashboard para professores e grupos
- Gamificação: conquistas, desafios, ranking
- Integração com plataformas de ensino (Moodle, Google Classroom)
- Exportação avançada (PDF, Excel, API)
- Ferramentas para análise estatística das respostas
- Suporte para exames de outros idiomas (espanhol, francês, etc.)
- Sistema de feedback automático
- Chat e fórum integrado para dúvidas

Veja todas as ideias abertas na [label enhancement](../issues?q=is%3Aissue+label%3Aenhancement).

---

## Como sugerir melhorias

- Crie uma [issue](../issues/new/choose) detalhando sua sugestão, dúvida ou bug.
- Participe das discussões em [Discussions](../discussions).
- Proponha PRs sempre que possível, seguindo o [Guia de Contribuição](./contribution.md).
- Use os templates de issue para facilitar o triagem.

---

## Links para issues e discussões

- [Lista de Issues](../issues)
- [Issues por fase](../issues?q=is%3Aissue+sort%3Acreated-asc)
- [Discussões da comunidade](../discussions)
- [Roadmap visual (GitHub Projects)](../projects)

---

**Este roadmap é colaborativo!**  
Atualize sempre que um novo marco for atingido, uma ideia for priorizada ou novas demandas surgirem.  
Juntos, vamos construir o melhor laboratório de inglês open source 🚀

Consulte também:  
- [architecture.md](./architecture.md)  
- [usage.md](./usage.md)  
- [contribution.md](./contribution.md)  