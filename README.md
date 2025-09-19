# 🔐 Projeto de Segurança Cibernética – LojaZeta  

Desafio Final do módulo de Fundamentos em Cibersegurança do curso Formação CyberSec da escola Vai na Web juntamente com a Kensei Cybersec.  

💼 **Projeto de Arquitetura de Defesa em Camadas e Monitoramento – LojaZeta (e-commerce fictício)**  
Este repositório contém a proposta completa de segurança para a LojaZeta, um e-commerce em crescimento hospedado em infraestrutura de nuvem (IaaS), que enfrentou incidentes recentes de **SQLi, XSS e brute-force** em `/login`.  

---

## 🧠 Objetivo do Projeto  
Desenvolver uma **arquitetura de defesa em camadas**, com foco em **monitoramento centralizado, resposta a incidentes estruturada (NIST IR)** e **plano de implementação viável** dentro das restrições de equipe e orçamento, garantindo **resiliência, visibilidade e redução de riscos**.  

---

## 🏗️ Etapas de Desenvolvimento  

### 1. Escopo e Metodologia  
- Cobertura: aplicação web, banco de dados, logs e identidade.  
- Premissas: equipe pequena e orçamento limitado → solução enxuta e priorizada.  

### 2. Arquitetura de Defesa em Camadas  
- **Fluxo principal**: Internet → WAF/CRS → Load Balancer → App Node.js → PostgreSQL.  
- IDS/IPS, segmentação de rede, firewall, backup seguro.  
- Identidade com MFA e centralização de logs no SIEM.  
```mermaid
flowchart LR
    A[🌐 Internet] --> B[🛡️ WAF / CRS]
    B --> C[⚖️ Load Balancer]
    C --> D[💻 App Node.js]
    D --> E[(🗄️ PostgreSQL DB)]

    %% Monitoramento
    D --> F[📊 Logs - Aplicação]
    E --> G[📊 Logs - Banco de Dados]
    C --> H[📊 Logs - Nginx]
    subgraph SIEM
        F --> I[SIEM Centralizado]
        G --> I
        H --> I
    end

    %% Identidade
    J[🔑 MFA / Identidade Segura] --> D

### 3. Monitoramento & SIEM  
- Fontes: Nginx, App, DB, Sistema Operacional.  
- Correlação de eventos e alertas acionáveis.  
- **KPIs**: MTTD, MTTR, tentativas bloqueadas, % de cobertura de logs.  

### 4. Resposta a Incidentes (NIST IR)  
- Fases: **Detecção → Contenção → Erradicação → Recuperação → Lições Aprendidas**.  
- Runbooks específicos para SQLi, XSS, brute-force e indisponibilidade.  

### 5. Plano de Implementação (80/20)  
- **Quick wins (30 dias)**: MFA, WAF/CRS, centralização de logs.  
- **Médio prazo (90 dias)**: correlações no SIEM, dashboards e KPIs.  
- **Longo prazo (180 dias)**: EDR, automação de respostas e auditorias periódicas.  

### 6. Riscos, Custos e Assunções  
- **Riscos**: equipe reduzida, dependência da nuvem, ataques em evolução constante.  
- **Custos**: priorização de soluções open-source.  
- **Assunções**: equipe treinada e foco em soluções escaláveis e viáveis.  

### 7. Conclusão e Próximos Passos  
- Maior visibilidade e redução imediata de riscos.  
- Resposta estruturada a incidentes.  
- Roadmap para evolução contínua da segurança.  
- **Critérios de sucesso**:  
  - Redução do MTTD/MTTR  
  - 100% de sucesso em testes de backup  
  - 80% de cobertura de logs  

---

## 📌 Recursos Utilizados  
- Diagramas criados no **Draw.io** e **Mermaid (GitHub)**  
- Documentação estruturada em **Markdown e Google Docs**   
- Baseado em boas práticas de **NIST, MITRE ATT&CK e CIS Controls**  

---
## ✅ Conclusão  
Este projeto apresenta uma solução prática e viável para aumentar a segurança da LojaZeta, unindo **defesa em camadas, monitoramento inteligente e resposta a incidentes**. Mesmo com restrições de equipe e orçamento, a empresa poderá **reduzir riscos críticos**, **melhorar a resiliência operacional** e **garantir continuidade de negócios**.

---
## 📘 Documentação do Projeto  
📘 O documento PDF completo do projeto está disponível logo acima deste README ☝️

---

✍️ **Autor**  
George Silva Monteiro  
Entusiasta em Cybersegurança 📍 Brasil  
