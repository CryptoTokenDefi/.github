# CryptoToken DeFi

> Plataforma financeira digital que une investimentos em criptomoedas, carteira digital, compliance regulatório e atendimento com IA — de forma segura e regulada.

[![Organização](https://img.shields.io/badge/organização-CryptoTokenDefi-8b5cf6?style=flat-square)](https://github.com/CryptoTokenDefi)
[![Stack](https://img.shields.io/badge/stack-.NET%208%20%7C%20Blazor%20%7C%20MAUI%20%7C%20MongoDB-512bd4?style=flat-square)](https://dotnet.microsoft.com/)
[![Status](https://img.shields.io/badge/status-Beta%20Web%20Controlada-22c55e?style=flat-square)](#roadmap)
[![Compliance](https://img.shields.io/badge/compliance-LGPD%20%7C%20KYC%2FAML-0ea5e9?style=flat-square)](#segurança-e-compliance)

---

## 🚀 Visão de Produto

A **CryptoToken DeFi** é uma plataforma financeira digital construída para democratizar o acesso a investimentos em ativos digitais. Reúne, em um único ecossistema, o ciclo completo do investidor: do onboarding e verificação de identidade (KYC) ao pagamento, alocação, acompanhamento de carteira e suporte assistido por inteligência artificial.

**Missão:** tornar o investimento digital acessível, seguro e regulado — com suporte inteligente em cada etapa da jornada do usuário.

**Diferenciais:**
- 🔐 **Segurança por design** — autenticação JWT, hashing BCrypt, rate limiting e sanitização de dados sensíveis em todos os logs.
- ⚖️ **Compliance nativo** — LGPD, KYC/AML e trilha de auditoria desde a fundação do projeto.
- 🤖 **Atendimento com IA** — chatbot com RAG (base de conhecimento) e handoff humano com protocolo de ticket.
- 🧩 **Arquitetura modular** — API central em .NET, web em Blazor e app em .NET MAUI, com contratos compartilhados.
- 🪙 **Web3 integrado** — carteira digital, ledger contábil e operações em blockchain EVM (via Nethereum).

---

## 🧭 Pilares da Plataforma

| Pilar | O que entrega | Estado |
|---|---|---|
| **Onboarding & Membership** | Cadastro Web2/Web3, planos de adesão e checkout de pagamento (Stripe) | `real` |
| **KYC & Compliance** | Verificação de identidade, aprovação/rejeição e bloqueio de dados sensíveis | `real` (sandbox parcial) |
| **Investimento & Rendimento** | Planos institucionais, simulação, alocação e acompanhamento de carteira | `real` |
| **Carteira & Ledger** | Depósitos/saques em cripto, registro contábil imutável e conciliação | `real` |
| **Suporte Inteligente** | Chatbot RAG, FAQ, status seguro e handoff para humano com ticket | `real` |
| **Backoffice Operacional** | Gestão de usuários, KYC, transações, relatórios e auditoria LGPD | `real` |
| **Mobile** | App .NET MAUI consumindo contratos oficiais do backend | `parcial` |
| **Web3 Avançado** | Staking e contratos Solidity modulares | `parcial` |

---

## 🛠️ Stack Tecnológica

```
┌─────────────────────────────────────────────────────────────┐
│  Camada de Experiência                                        │
│  • Web oficial: Blazor Server (.NET 8, InteractiveServer)     │
│  • Mobile: .NET MAUI 9 (Android + Windows)                    │
│  • Espelho estático legado (web-static) para transição        │
├─────────────────────────────────────────────────────────────┤
│  Camada de Serviço (Backend .NET 8)                           │
│  • ASP.NET Core Web API + MongoDB (MongoDbGenericRepository)  │
│  • Nethereum para operações Web3 / EVM                        │
│  • Ollama (LLM local) para RAG do chatbot                     │
│  • Stripe para pagamentos (REST + Webhooks idempotentes)      │
├─────────────────────────────────────────────────────────────┤
│  Infraestrutura & Governança                                  │
│  • Docker / Compose, NGINX, CI/CD (GitHub Actions)            │
│  • Docs canônicas, auditoria e contratos compartilhados       │
└─────────────────────────────────────────────────────────────┘
```

**Principais tecnologias:** `.NET 8` · `Blazor Server` · `.NET MAUI 9` · `MongoDB` · `Nethereum` · `Stripe` · `Ollama` · `Docker` · `GitHub Actions`.

---

## 📦 Repositórios da Organização

| Repositório | Missão | Acesso |
|---|---|---|
| [Backend](https://github.com/CryptoTokenDefi/Backend) | API principal, regras de negócio, persistência, webhooks e testes | Privado |
| [Frontend](https://github.com/CryptoTokenDefi/Frontend) | Experiência web oficial (Blazor) e trilha estática legada | Privado |
| [Mobile](https://github.com/CryptoTokenDefi/Mobile) | App oficial em consolidação (.NET MAUI) | Privado |
| [Infra](https://github.com/CryptoTokenDefi/Infra) | CI/CD, Docker, runtime, scripts e segurança de stack | Privado |
| [Integrations](https://github.com/CryptoTokenDefi/Integrations) | Contratos compartilhados, Postman, staking e trilha web3 | Privado |
| [Docs](https://github.com/CryptoTokenDefi/Docs) | Documentação canônica, auditoria e governança | Privado |
| [.github](https://github.com/CryptoTokenDefi/.github) | Configurações globais, templates e perfil da organização | Público |

---

## 🔒 Segurança e Compliance

A plataforma foi desenhada com conformidade regulatória como requisito não-funcional:

- **LGPD** — consentimento explícito, exportação e exclusão de dados do titular, com trilha em `DataSubjectDeletionLogs` e `UserConsents`.
- **KYC / AML** — verificação obrigatória antes de operações financeiras; dados sensíveis nunca expostos em APIs públicas.
- **Segurança financeira** — rate limiting em endpoints críticos, idempotência em webhooks de pagamento, BCrypt para senhas e JWT (15 min + refresh de 30 dias).
- **Observabilidade** — `traceId`/`correlationId` em fluxos críticos e redação de PII em logs e tickets.

> ⚠️ **Aviso:** a CryptoToken DeFi não promete rendimento garantido. Rentabilidades dependem de mercado e estão sujeitas a risco. Este perfil é institucional e não constitui recomendação de investimento.

---

## 🗺️ Roadmap

| Fase | Foco | Status |
|---|---|---|
| **Beta Web Controlada** | Backoffice operacional, UX de erro, runbooks e E2E | 🟡 Em andamento |
| **P0-04 · E2E + Gate 3** | Testes ponta a ponta com dados reais (sem mock) | ⏳ Pendente |
| **Gates 4/5 · Go/No-Go** | Homologação de segurança e decisão de lançamento | ⏳ Pendente |
| **Mobile Consolidado** | App MAUI consumindo contratos oficiais | 📋 Planejado |
| **Web3 Avançado** | Staking e contratos Solidity modulares | 📋 Planejado |

---

## 🤝 Como Engajar

- 🌐 Organização: [github.com/CryptoTokenDefi](https://github.com/CryptoTokenDefi)
- 📚 Documentação canônica: [Docs](https://github.com/CryptoTokenDefi/Docs)
- 🐞 Issues e contribuição: repositórios específicos (Frontend, Backend, etc.)
- 🔐 Repositórios técnicos são privados; este perfil é a porta de entrada pública.

---

<p align="center">
  <sub>CryptoToken DeFi — investimentos digitais seguros, regulados e com suporte inteligente.</sub>
</p>
