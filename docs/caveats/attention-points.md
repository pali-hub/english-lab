## 6. Pontos de atenção

Esta seção destaca limitações, riscos e aspectos críticos que merecem validação constante no projeto.

---

### 1. Dados grandes e performance

- **PDFs extensos:** O processamento de provas grandes pode ser lento ou exigir muita memória. É importante limitar o tamanho dos arquivos ou processar em lotes.
- **Git LFS:** O uso de Git LFS é necessário para arquivos grandes, mas há limites gratuitos (ex: 1GB por repositório no GitHub). Considere alternativas se o volume crescer.
- **Armazenamento:** JSONs gerados e relatórios podem ocupar espaço significativo. Recomenda-se limpezas periódicas ou armazenamento externo em nuvem se houver muitos dados históricos.
- **Performance do parser:** Scripts Python podem ser otimizados (paralelismo, uso de cache, etc.) conforme a demanda aumenta.

---

### 2. Validação de dados

- **Estrutura dos JSONs:** É fundamental validar os dados extraídos, pois erros de parsing podem comprometer o frontend e os relatórios.
- **Automação:** Workflows de CI/CD devem sempre validar os JSONs antes de aprovar merges ou deploys.
- **Testes integrados:** Garantem que mudanças no parser não quebrem o consumo dos dados pelo frontend/backend.

---

### 3. Limites de plataformas gratuitas

- **Cloudflare Pages:** Possui limites de build, armazenamento e requisições mensais. Para projetos grandes, pode ser necessário migrar para planos pagos ou outras plataformas.
- **GitHub Actions:** Limites de minutos grátis para CI/CD. Em projetos open source, o uso é amplo, mas deve-se acompanhar o consumo.
- **Render/Railway (backend):** Planos gratuitos têm limites de RAM, CPU e tempo de execução. Ideal para protótipos, mas pode exigir upgrade em produção.

---

### 4. Padrão e consistência

- **Estrutura dos arquivos:** Mudanças na estrutura dos dados ou nas pastas exigem atualização da documentação, templates e scripts.
- **Dependências:** Atualizações em frameworks ou libs podem causar incompatibilidades. Sempre testar em ambiente isolado antes do merge.

---

### 5. Segurança e privacidade

- **Dados sensíveis:** Certifique-se de não commitar dados confidenciais ou informações pessoais nos repositórios.
- **.gitignore e GitHub Secrets:** Use corretamente para evitar vazamento de dados ou credenciais.

---

### 6. Escalabilidade e evolução

- **Novos módulos:** Adição de novos parsers ou apps pode aumentar a complexidade dos workflows, testes e integração. Planeje a modularidade desde o início.
- **Multi-linguagem:** Integração entre diferentes stacks pode exigir padronização de APIs, schemas de dados e documentação clara.

---

**Resumo:**  
Manter validação constante, monitorar limites de plataformas e garantir automação de testes são essenciais para evitar gargalos e problemas de escala ou manutenção.

---

Consulte também o [architecture.md](./architecture.md) e mantenha o [roadmap.md](./roadmap.md) atualizado.