# CryptoToken DeFi

Atualizado em: 2026-04-24

Plataforma organizada em 6 repositorios com responsabilidade separada para produto, operacao, integracoes e governanca documental.

## Taxonomia Canonica

- `real`: implementado e evidenciado no codigo versionado.
- `parcial`: existe no codigo, mas depende de consolidacao para operacao plena.
- `planejado`: backlog futuro sem evidencia de entrega no codigo atual.
- `divergente`: documento ou narrativa que conflita com o estado real atual.
- `legado`: material mantido para referencia historica, fora da trilha oficial.

## Repositorios Oficiais

| Repositorio | Missao | Estado Atual |
|---|---|---|
| `Backend` | API principal, regras de negocio, persistencia, testes e webhooks | `real` no core API, `parcial` em frentes web3 avancadas |
| `Frontend` | Experiencia web oficial em Blazor e trilha estatica legada ativa | `real` no Blazor, `legado` ativo no `web-static` |
| `Infra` | CI/CD, docker, runtime, scripts operacionais e seguranca de stack | `parcial` |
| `Docs` | Camada canonica de documentacao, auditoria, contratos e governanca | `real` |
| `Mobile` | Baseline .NET MAUI, contratos mobile/backend e consolidacao de app | `parcial` |
| `Integrations` | Contratos compartilhados, Postman, staking e trilha web3 modular | `parcial` |

## Estado Real Consolidado (codigo + docs canonicas)

- Backend: 14 controllers e 108 rotas HTTP mapeadas no codigo.
- Frontend Blazor: 27 paginas e 29 rotas ativas.
- Frontend `web-static`: 44 paginas HTML mantidas como legado ativo (nao-oficial para runtime principal).
- Mobile: 9 controllers, 22 viewmodels, 26 views XAML.
- Infra: 11 scripts operacionais e 1 workflow versionado.
- Integrations: 7 contratos markdown, 1 OpenAPI, 1 Postman, 1 contrato Solidity.

## Fonte de Verdade

Precedencia oficial:

1. codigo e estrutura real do repositorio correspondente
2. `README.md` e `ROADMAP.md` do repositorio correspondente
3. documentacao canonica no repositorio `Docs`
4. historico/auditorias como memoria de apoio

## Navegacao Rapida

- [Backend](https://github.com/CryptoTokenDefi/Backend)
- [Frontend](https://github.com/CryptoTokenDefi/Frontend)
- [Infra](https://github.com/CryptoTokenDefi/Infra)
- [Mobile](https://github.com/CryptoTokenDefi/Mobile)
- [Integrations](https://github.com/CryptoTokenDefi/Integrations)
- [Docs](https://github.com/CryptoTokenDefi/Docs)
