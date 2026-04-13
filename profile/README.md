# CryptoToken DeFi

Plataforma em consolidacao para operacao financeira digital com foco em experiencia web, backend transacional, contratos compartilhados, governanca documental e evolucao gradual de frentes mobile e web3.

## Visao Geral

A organizacao `CryptoTokenDefi` esta estruturada hoje como um programa com 6 repositorios especializados:

- `Backend`: API oficial, regras de negocio, persistencia e testes
- `Frontend`: experiencia web oficial do produto
- `Infra`: operacao, deploy, CI/CD e automacao
- `Docs`: camada canonica de documentacao, contratos, auditorias e runbooks
- `Mobile`: baseline mobile oficial em consolidacao
- `Integrations`: contratos compartilhados, frentes web3 e modularizacao futura

O objetivo atual nao e apresentar um ecossistema "fechado", e sim uma plataforma com base real ja entregue, backlog explicito e governanca tecnica clara para evolucao continua.

## Estado Atual do Programa

Taxonomia usada neste perfil:

- `real`: implementado e/ou operado hoje
- `parcial`: existe, mas ainda depende de consolidacao ou ampliacao
- `planejado`: backlog futuro, ainda nao entregue
- `legado`: mantido como referencia, nao como trilha principal
- `divergente`: historico que nao deve prevalecer sobre o estado atual

Leitura executiva atual:

- backend principal: `real`
- frontend oficial em `blazor-server`: `real`
- trilha `web-static`: `legado`
- infra de operacao, Docker, nginx, CI e scripts: `real`
- documentacao central, contratos e runbooks: `real`
- integracoes compartilhadas e frente web3: `parcial`
- aplicativo mobile: `parcial` em baseline real, sem release oficial em stores

Em termos de programa, a plataforma ja possui base funcional concreta, mas ainda esta em consolidacao. A leitura canonica do estado atual distingue claramente o que ja esta entregue do que ainda e extensao futura.

## Mapa dos Repositorios

| Repositorio | Missao | Estado | Runtime / baseline atual |
|---|---|---|---|
| [Backend](https://github.com/CryptoTokenDefi/Backend) | API oficial, servicos, persistencia, webhooks e testes | `real` com partes `parcial` | ASP.NET Core 8 + MongoDB + Docker |
| [Frontend](https://github.com/CryptoTokenDefi/Frontend) | experiencia web oficial do produto | `real` | Blazor Server |
| [Infra](https://github.com/CryptoTokenDefi/Infra) | deploy, CI/CD, compose, nginx e automacao | `real` com partes `parcial` | Docker, scripts operacionais e CI |
| [Docs](https://github.com/CryptoTokenDefi/Docs) | documentacao canonica, contratos, auditorias e runbooks | `real` com harmonizacao `parcial` | repositorio documental central |
| [Mobile](https://github.com/CryptoTokenDefi/Mobile) | baseline mobile oficial em consolidacao | `parcial` | .NET MAUI com build local Android/Windows |
| [Integrations](https://github.com/CryptoTokenDefi/Integrations) | contratos compartilhados, web3 e modularizacao futura | `parcial` | contratos e stubs, nao runtime principal |

## Arquitetura Canonica Hoje

A arquitetura atual do programa deve ser lida com esta precedencia:

1. codigo e estrutura real de cada repositorio
2. `README.md` e `ROADMAP.md` do repositorio correspondente
3. matriz canonica e documentacao central em `Docs`
4. auditorias, sprints e historicos como memoria de apoio

Leitura consolidada da arquitetura:

- o `Backend` concentra a API oficial, servicos, DTOs, repositorios, testes automatizados e capacidades de pagamentos, KYC, afiliados, suporte, reporting e operacao administrativa
- o `Frontend` em `blazor-server` e a experiencia web oficial atual
- a trilha `web-static` permanece como referencia `legado`, nao como frontend principal publicado
- o `Infra` centraliza a camada operacional: Docker, nginx, workflows, scripts de bootstrap, smoke e deploy
- o `Docs` funciona como hub de contexto funcional, arquitetural, contratual e operacional
- o `Integrations` organiza contratos compartilhados e a frente web3 ainda parcial
- o `Mobile` representa a trilha oficial de consolidacao para app, ainda sem fechamento de release publico

## O Que Ja Temos

Entregas e capacidades observadas como `real` hoje:

- backend .NET 8 com superficie de API, servicos, repositorios e testes
- frontend web oficial em Blazor Server
- camada de deploy e operacao com Docker, nginx, automacoes e CI
- documentacao central com matriz canonica, inventario, contratos, runbooks e auditorias
- backlog organizado por repositorio com `README` e `ROADMAP`
- baseline mobile existente com mapa tecnico e codigo real

Frentes `parcial` ou em consolidacao:

- aprofundamento de observabilidade, auditoria e hardening operacional
- maturidade completa da frente mobile para release oficial
- consolidacao de contratos compartilhados e fronteiras web2/web3
- harmonizacao total entre historico documental e estado presente dos repositorios

Frentes `planejado`:

- evolucoes futuras de produto, integracoes e sprints posteriores
- amadurecimento adicional de web3, staking e modularizacao por dominios
- readiness mais forte de release, cobertura e governanca operacional nas trilhas ainda parciais

## Stack Principal por Camada

| Camada | Stack principal |
|---|---|
| Backend | ASP.NET Core 8, C#, MongoDB, Docker |
| Frontend web oficial | Blazor Server, ASP.NET Core 8, Docker |
| Infra | Docker, compose, nginx, GitHub Actions, scripts PowerShell |
| Documentacao | Markdown, contratos, auditorias, runbooks e roadmap distribuido |
| Mobile | .NET MAUI |
| Integrations | contratos compartilhados, Postman, stubs e frentes web3 |

## Governanca e Fonte de Verdade

O repositorio [Docs](https://github.com/CryptoTokenDefi/Docs) e a camada canonica de documentacao do programa, mas ele nao substitui o codigo como fonte de verdade operacional. Quando houver conflito, o estado real do repositorio correspondente prevalece.

Leituras antigas, auditorias e sprints historicas continuam preservadas como memoria institucional. Elas ajudam no contexto, mas nao devem sobrescrever a organizacao atual do programa quando o estado mais recente aponta outra direcao.

## Proximos Passos Prioritarios

- consolidar ainda mais interfaces estaveis entre Backend, Frontend, Infra, Mobile e Integrations
- ampliar hardening, observabilidade e correlacao operacional
- reduzir divergencias entre historico documental e baseline atual
- amadurecer a frente mobile para readiness de release
- consolidar contratos compartilhados e o enquadramento correto da trilha web3

## Acesso Rapido

- [Backend README](https://github.com/CryptoTokenDefi/Backend/blob/main/README.md)
- [Frontend README](https://github.com/CryptoTokenDefi/Frontend/blob/main/README.md)
- [Infra README](https://github.com/CryptoTokenDefi/Infra/blob/main/README.md)
- [Docs README](https://github.com/CryptoTokenDefi/Docs/blob/main/README.md)
- [Mobile README](https://github.com/CryptoTokenDefi/Mobile/blob/main/README.md)
- [Integrations README](https://github.com/CryptoTokenDefi/Integrations/blob/main/README.md)

Este perfil resume o estado consolidado atual da organizacao. Para implementacao, operacao detalhada e contratos tecnicos, a navegacao correta continua sendo o repositorio especializado de cada frente.
