# CryptoToken DeFi

Plataforma financeira digital em operação, com backend transacional completo, experiência web oficial, infraestrutura containerizada, compliance LGPD/GDPR implementado e evolução gradual das frentes mobile e web3.

> **Atualizado em:** 2026-04-13 — Sprint LGPD-1 e LGPD-2 entregues.

---

## Visão Geral

A organização `CryptoTokenDefi` é estruturada como um programa com 6 repositórios especializados:

- `Backend` — API oficial, regras de negócio, compliance LGPD/GDPR, persistência e testes
- `Frontend` — experiência web oficial do produto (Blazor Server)
- `Infra` — operação, deploy, CI/CD e automação
- `Docs` — camada canônica de documentação, contratos, auditorias e runbooks
- `Mobile` — baseline mobile oficial em consolidação
- `Integrations` — contratos compartilhados, frentes web3 e modularização futura

---

## Estado Atual do Programa

Taxonomia usada neste perfil:

- `real` — implementado e operado hoje
- `parcial` — existe, mas depende de consolidação ou ampliação
- `planejado` — backlog futuro, ainda não entregue
- `legado` — mantido como referência, não como trilha principal

| Frente | Estado |
|--------|--------|
| Backend API + serviços + testes | `real` |
| Compliance LGPD/GDPR (núcleo) | `real` — Sprints LGPD-1 e LGPD-2 entregues |
| Frontend Blazor Server | `real` |
| Infra Docker/nginx/CI | `real` |
| Documentação central + contratos | `real` |
| Mobile (.NET MAUI) | `parcial` |
| Integrations / Web3 | `parcial` |
| Antifraude robusto, DLP, SIEM | `planejado` |
| Release público nas stores | `planejado` |

---

## Compliance LGPD/GDPR — Estado Atual

As Sprints LGPD-1 e LGPD-2 foram entregues em 2026-04-13, implementando o núcleo regulatório exigido pela **Lei 13.709/2018 (LGPD)** e **Regulamento UE 2016/679 (GDPR)** no backend .NET.

### Sprint LGPD-1 — Fundação de Segurança + Consentimento (28 pts) `entregue`

| ID | Entrega | Status |
|----|---------|--------|
| S1-01 | JWT access token (15min) + refresh token (30d) com rotation attack detection | ✅ |
| S1-02 | RBAC Admin/SuperAdmin em endpoints de gestão de usuários | ✅ |
| S1-03 | Módulo de privacidade — `UserConsents` collection + base legal LGPD Art. 7 | ✅ |
| S1-04 | `POST /privacy/consent` e `GET /privacy/status` | ✅ |
| S1-05 | Audit log wired: Login, LoginFailed, Register, SuspiciousLoginPattern | ✅ |
| S1-06 | Logs estruturados com `traceId` + `userId` em todo escopo de request | ✅ |
| S1-07 | Global exception middleware + `PrivacyConsentException` (422) | ✅ |
| S1-08 | Revisão técnica e regressão | ✅ |

### Sprint LGPD-2 — Direitos do Titular + Hardening (26 pts) `entregue`

| ID | Entrega | Status |
|----|---------|--------|
| S2-01 | `GET /privacy/me/data` — dados pessoais do titular sem exposição de PII sensível | ✅ |
| S2-02 | `GET /privacy/me/export?format=json\|csv` — portabilidade de dados (LGPD Art. 18) | ✅ |
| S2-03 | `DELETE /privacy/me/delete` — anonimização segura, coleções financeiras retidas (CVM/BACEN) | ✅ |
| S2-04 | Rate limit em `/auth/refresh` + audit de `RateLimitExceeded` | ✅ |
| S2-05 | Security headers: HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy | ✅ |
| S2-06 | Feature flag `GDPR_ENABLED` por ambiente | ✅ |
| S2-07 | Logging de `SuspiciousLoginPattern` e `RateLimitExceeded` em AuditLogs | ✅ |
| S2-08 | Checklist de homologação funcional com cliente | ✅ |

### Novas Collections MongoDB (Sprint LGPD)

| Collection | Finalidade |
|------------|------------|
| `RefreshTokens` | Tokens de renovação com TTL automático e detecção de reuso |
| `UserConsents` | Histórico de consentimentos com base legal, propósito e versão da política |
| `DataSubjectDeletionLogs` | Logs de anonimização com base legal de retenção (CVM/BACEN 5 anos) |

### Endpoints de Privacidade

```
POST   /auth/refresh               Renovação de access token via refresh token HttpOnly
POST   /auth/logout                Revogação de tokens e limpeza de cookies

POST   /privacy/consent            Gravar consentimento com base legal (LGPD Art. 7)
GET    /privacy/status             Consultar consentimentos ativos do titular

GET    /privacy/me/data            Dados pessoais completos (LGPD Art. 18 - acesso)
GET    /privacy/me/export          Exportação estruturada JSON/CSV (LGPD Art. 18 - portabilidade)
DELETE /privacy/me/delete          Anonimização de conta (LGPD Art. 18 - esquecimento)
```

### Estratégia de Anonimização (Fintech)

A exclusão completa do documento `User` violaria integridade referencial de coleções financeiras. A estratégia adotada é compatível com LGPD Art. 18 e regulação financeira brasileira:

- PII removido: email anonimizado `anon_{hash}@deleted.local`, senha apagada, carteira desvinculada
- Documento `User` preservado (referência para `Payments`, `UserInvestments`, `AuditLogs`)
- Coleções financeiras retidas por 5 anos (base legal CVM/BACEN)
- `DataSubjectDeletionLog` registra base legal e coleções retidas

---

## Mapa dos Repositórios

| Repositório | Missão | Estado | Runtime atual |
|-------------|--------|--------|---------------|
| [Backend](https://github.com/CryptoTokenDefi/Backend) | API oficial, compliance LGPD/GDPR, serviços, persistência e testes | `real` | ASP.NET Core 8 + MongoDB + Docker |
| [Frontend](https://github.com/CryptoTokenDefi/Frontend) | Experiência web oficial | `real` | Blazor Server |
| [Infra](https://github.com/CryptoTokenDefi/Infra) | Deploy, CI/CD, compose, nginx e automação | `real` | Docker, scripts, GitHub Actions |
| [Docs](https://github.com/CryptoTokenDefi/Docs) | Documentação canônica, contratos, auditorias e runbooks | `real` | Repositório documental central |
| [Mobile](https://github.com/CryptoTokenDefi/Mobile) | Baseline mobile oficial em consolidação | `parcial` | .NET MAUI |
| [Integrations](https://github.com/CryptoTokenDefi/Integrations) | Contratos compartilhados, web3 e modularização futura | `parcial` | Contratos e stubs |

---

## Stack Principal

| Camada | Stack |
|--------|-------|
| Backend | ASP.NET Core 8, C#, MongoDB, Docker |
| Autenticação | JWT Bearer + Refresh Token (HttpOnly cookies) |
| Compliance | LGPD/GDPR — consentimento, auditoria, direitos do titular |
| Segurança | Rate limiting, RBAC, security headers, correlation ID |
| Frontend | Blazor Server, ASP.NET Core 8, Tailwind CSS, Docker |
| Infra | Docker, Compose, nginx, GitHub Actions, PowerShell |
| Documentação | Markdown, OpenAPI, Postman, contratos, runbooks |
| Mobile | .NET MAUI |
| Integrations | Contratos compartilhados, Postman, stubs, web3 |

---

## Capacidades do Backend (estado atual)

| Domínio | Capacidade | Estado |
|---------|-----------|--------|
| Auth | Login, registro, Web3/MetaMask, JWT, refresh token, logout | `real` |
| Auth | RBAC Admin/SuperAdmin/Cliente | `real` |
| Compliance | Consentimento LGPD + base legal (POST/GET /privacy) | `real` |
| Compliance | Direitos do titular: acesso, portabilidade, exclusão | `real` |
| Compliance | Audit log rastreável por request, IP, userId | `real` |
| Compliance | Detecção de padrão suspeito de login | `real` |
| Compliance | KYC / pre-onboarding state machine | `real` |
| Pagamentos | Checkout, memberships, webhooks, gateway | `real` |
| Investimentos | Planos, rendimentos, compound, saques | `real` |
| Afiliados | Programa unilevel, cashback | `real` |
| Suporte | Chatbot educacional, tickets | `real` |
| Admin | Backoffice completo: users, investments, KYC, withdrawals | `real` |
| Reporting | Audit logs, export CSV, dashboard | `real` |
| Blockchain | Staking, Web3 auth (MetaMask) | `parcial` |
| Notificações | Serviço de notificação | `parcial` |

---

## Sprints do Programa

| Sprint | Tema | Estado |
|--------|------|--------|
| Sprint 0 | Reorganização estrutural e baseline | `concluído` |
| Sprint 1 | Núcleo financeiro (ledger, wallets) | `concluído` |
| Sprint 2 | Jornadas e contratos | `concluído` |
| Sprint 3 | Wallets, balance, compound | `concluído` |
| Sprint LGPD-1 | Segurança + consentimento LGPD/GDPR | `concluído` |
| Sprint LGPD-2 | Direitos do titular + hardening | `concluído` |
| Sprints 4–8 | Escalabilidade, mobile stores, go-live global | `planejado` |

---

## Governança e Fonte de Verdade

O repositório [Docs](https://github.com/CryptoTokenDefi/Docs) é a camada canônica de documentação. Quando houver conflito, o estado real do repositório correspondente prevalece sobre históricos e auditorias.

Precedência de leitura:

1. Código e estrutura real de cada repositório
2. `README.md` e `ROADMAP.md` do repositório correspondente
3. Matriz canônica e documentação central em `Docs`
4. Auditorias, sprints e históricos como memória de apoio

---

## Próximos Passos Prioritários

- Homologação funcional LGPD com cliente (checklist em `Backend/docs/SPRINT_LGPD_2_ACCEPTANCE_CHECKLIST.md`)
- Ampliar cobertura de testes nos novos endpoints de privacidade
- Implementar antifraude robusto, DLP e SIEM (fase posterior)
- Amadurecer trilha mobile para release oficial nas stores
- Consolidar contratos compartilhados e enquadramento correto da trilha web3

---

## Acesso Rápido

- [Backend README](https://github.com/CryptoTokenDefi/Backend/blob/main/README.md)
- [Frontend README](https://github.com/CryptoTokenDefi/Frontend/blob/main/README.md)
- [Infra README](https://github.com/CryptoTokenDefi/Infra/blob/main/README.md)
- [Docs README](https://github.com/CryptoTokenDefi/Docs/blob/main/README.md)
- [Sprint LGPD-1 Plan](https://github.com/CryptoTokenDefi/Docs/blob/main/sprints/SPRINT_LGPD_1_PLAN.md)
- [Sprint LGPD-2 Plan](https://github.com/CryptoTokenDefi/Docs/blob/main/sprints/SPRINT_LGPD_2_PLAN.md)
- [Checklist de Homologação LGPD](https://github.com/CryptoTokenDefi/Backend/blob/main/docs/SPRINT_LGPD_2_ACCEPTANCE_CHECKLIST.md)

---

Este perfil resume o estado consolidado atual da organização. Para implementação, operação detalhada e contratos técnicos, navegue pelo repositório especializado de cada frente.
