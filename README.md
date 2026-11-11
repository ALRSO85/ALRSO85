<div align="center">

<picture>
  <source media="(min-width: 481px)" srcset="./assets/profile-visual.svg" />
  <img src="./assets/profile-visual-mobile.svg" alt="Arte abstrata com conexões em tons de azul e verde, representando arquitetura e sistemas digitais" />
</picture>

# Alexandre Souza

**Software Architect · Senior Software Engineer · AI Engineer**

**.NET · Distributed Systems · Cloud Architecture · AI Engineering · Digital Products**

Na [DevsForYou](https://devsforyou.com.br/), sou responsável pelo desenho, pela arquitetura e pela construção de WorkTime, SportsForYou e ReleaseHub. Trabalho principalmente com .NET, arquitetura de sistemas e modernização de produtos.

[LinkedIn](https://www.linkedin.com/in/alexandre-roberto-souza-software-engineer/) · [DevsForYou](https://devsforyou.com.br/) · [SportsForYou](https://sportsforyou.com.br/)

**Cases técnicos:** [WorkTime — integração idempotente](https://github.com/ALRSO85/worktime-showcase#integra%C3%A7%C3%B5es-resilientes) · [SportsForYou — worker independente](https://github.com/ALRSO85/sportsforyou-showcase#background-processing) · [ReleaseHub — rollback com reconciliação](https://github.com/ALRSO85/releasehub-showcase#recupera%C3%A7%C3%A3o-de-rollback)

**Navegação:** [Cases](#projetos-em-destaque) · [Experimento técnico](#experimento-t%C3%A9cnico) · [Outros produtos](#outros-produtos) · [Open source](#open-source) · [Engenharia de IA](#engenharia-de-ia) · [Competências](#compet%C3%AAncias-t%C3%A9cnicas) · [Segurança](#seguran%C3%A7a-aplicada) · [GitHub](#github) · [Contato](#contato)

</div>

---

## Projetos em destaque

Três exemplos de decisões sobre integrações, processamento assíncrono e releases.

### [WorkTime](https://worktime.devforyou.com.br/)

Aplicação para gestão e conciliação de horas, jornadas, equipes, férias, fechamentos, auditoria e relatórios.

Um dos desafios é sincronizar apontamentos quando o provedor pode processar a escrita sem confirmar a resposta. O WorkTime reserva uma chave idempotente antes do envio, registra `Unknown` quando não consegue confirmar o resultado e não repete a operação às cegas. Os retries automáticos ficam restritos a leituras transitórias `GET` e `HEAD`. Integra-se ao Businessmap/Kanbanize e ao Ahgora, e usa C#, .NET 10, ASP.NET Core, EF Core e SQL Server. Roda em Ubuntu Server, com Cloudflare Tunnel. [Acessar o WorkTime](https://worktime.devforyou.com.br/) · [Ver o showcase técnico](https://github.com/ALRSO85/worktime-showcase).

---

### [SportsForYou](https://sportsforyou.com.br/)

Plataforma esportiva para atletas, organizadores, comunidades e parceiros, com eventos, perfis e integrações.

No SportsForYou, os módulos de negócio ficam na aplicação web e os jobs rodam no `Sport.Worker.JobCenter`, um .NET Worker com container e health check próprios. Essa separação dá ao processamento assíncrono um ciclo operacional independente. A plataforma usa C#, .NET 10, ASP.NET Core, SQL Server e Docker, em Ubuntu Server com Cloudflare Tunnel. [Acessar o produto](https://sportsforyou.com.br/) · [Ver o showcase técnico](https://github.com/ALRSO85/sportsforyou-showcase) · [Ler o artigo sobre arquitetura modular](https://pt.linkedin.com/pulse/arquitetura-modular-aplicada-uma-plataforma-digital-para-souza-g8btf).

---

### [ReleaseHub](https://releasehub.devforyou.com.br/)

Plataforma self-hosted para governança e execução de releases, com aprovações, validações e auditoria.

No ReleaseHub, o rollback precisa atualizar o ambiente remoto e o catálogo local. A operação passa por `Revertendo` e só chega a `Revertida` depois das confirmações; falhas ficam registradas para reconciliação. O serviço usa .NET 10, ASP.NET Core, Docker e SQL Server em Ubuntu Server, com Cloudflare Tunnel. [Acessar o ReleaseHub](https://releasehub.devforyou.com.br/) · [Ver o showcase técnico](https://github.com/ALRSO85/releasehub-showcase).

## Experimento técnico

### [Financial](https://github.com/ALRSO85/Financial) — API demonstrativa

API em C#/.NET para registrar créditos e débitos e consultar saldos atuais ou históricos.

O experimento usa ledger imutável, escritas idempotentes, outbox transacional e projeção de leitura assíncrona, com .NET 10, ASP.NET Core Minimal APIs, PostgreSQL, JWT e OpenTelemetry. [Explorar o código e a arquitetura](https://github.com/ALRSO85/Financial).

## Outros produtos

### [Chegou Inteiro](https://chegouinteiro.devforyou.com.br/)

Plataforma para consulta regional de experiências de entrega.

A demonstração usa dados sintéticos e está em modo de consulta; não representa cobertura real de entregas. Novos cadastros e relatos estão desativados. O projeto usa ASP.NET Core MVC, Ubuntu Server e Docker. [Abrir a demonstração](https://chegouinteiro.devforyou.com.br/) · [Ver o showcase técnico](https://github.com/ALRSO85/chegouinteiro-showcase).

### [Doguinhos 220v](https://doguinhos220v.com.br/)

Portal pet com artigos, eventos, vídeos e recomendações de produtos.

O portal foi desenvolvido pela DevsForYou com PHP 8.5 e Bootstrap 5.3, e roda em Ubuntu Server com Apache. [Acessar o portal](https://doguinhos220v.com.br/) · [Ver o showcase técnico](https://github.com/ALRSO85/doguinhos-showcase).

## Open source

**[FingerBridge](https://github.com/ALRSO85/fingerbridge)** — Projeto open source criado e mantido por mim: biblioteca para integrar leitores biométricos a aplicações Windows em .NET Framework 4.8, com providers independentes.

`C#` `.NET Framework` `WinForms` `Biometria` · [Licença MIT](https://github.com/ALRSO85/fingerbridge/blob/main/LICENSE) · [Explorar repositório](https://github.com/ALRSO85/fingerbridge)

## Engenharia de IA

Tenho aprofundado meus estudos em engenharia de IA e explorado o uso de LLMs no desenvolvimento de software. No [showcase do SportsForYou](https://github.com/ALRSO85/sportsforyou-showcase#background-processing), apresento a arquitetura do produto e a separação do processamento assíncrono. Também escrevi sobre [arquitetura AI-First no ecossistema .NET](https://pt.linkedin.com/pulse/ai-first-software-architecture-o-que-muda-quando-artificial-souza-mjcgf), com foco em orquestração, busca semântica e guardrails.

## Competências técnicas

- **Backend e APIs:** `C#` `.NET` `ASP.NET Core` `Node.js` `APIs REST`
- **Design de software e arquitetura:** `DDD` `Clean Architecture` `Arquitetura modular` `Microsserviços` `Sistemas orientados a eventos`
- **Dados:** `SQL Server` `MySQL` `PostgreSQL` `Redis` `Entity Framework Core`
- **Web:** `HTML` `CSS` `Bootstrap` `JavaScript` `TypeScript` `Interfaces responsivas`
- **Cloud e entrega:** `Docker` `Linux` `Ubuntu Server` `Azure` `AWS` `Cloudflare DNS` `Cloudflare Tunnel` `CI/CD`
- **Segurança:** `CSRF` `Cookies seguros` `Rate limiting` `SHA-256` `SBOM` `Dados biométricos`
- **Engenharia de software:** `Modernização` `Integrações` `Desempenho` `Resiliência` `Observabilidade`
- **Qualidade de código:** análise estática com `SonarQube`
- **Testes de carga:** `Apache JMeter`

## Segurança aplicada

- **Doguinhos 220v:** senhas com bcrypt, proteção CSRF, sessões administrativas com cookies HttpOnly/SameSite, rate limiting e validação de uploads.
- **WorkTime:** ações protegidas contra CSRF, cookies de autenticação HttpOnly e políticas configuráveis de expiração, SameSite e Secure, além de rate limiting.
- **ReleaseHub:** validação de hashes SHA-256 e políticas configuráveis para exigir assinatura, proveniência e SBOM de artefatos.
- **[FingerBridge](https://github.com/ALRSO85/fingerbridge):** [política de segurança e relato privado](https://github.com/ALRSO85/fingerbridge/blob/main/SECURITY.md); orientações para não armazenar imagens biométricas nem registrar templates em logs e criptografar templates persistidos.

## Temas de interesse

Sistemas distribuídos, produtos SaaS, infraestrutura self-hosted e IA aplicada à engenharia de software.

## GitHub

Parte da minha atuação acontece em repositórios privados e ambientes corporativos. O cartão abaixo é gerado pela [GitHub Action](.github/workflows/profile-summary-cards.yml) e mostra a atividade que o GitHub disponibiliza para este perfil.

<div align="center">

<picture>
  <source media="(max-width: 480px) and (prefers-color-scheme: dark)" srcset="./profile-summary-card-output/mobile/github_dark/0-profile-details.svg" />
  <source media="(min-width: 481px) and (prefers-color-scheme: dark)" srcset="./profile-summary-card-output/github_dark/0-profile-details.svg" />
  <source media="(min-width: 481px)" srcset="./profile-summary-card-output/github/0-profile-details.svg" />
  <img src="./profile-summary-card-output/mobile/github/0-profile-details.svg" alt="Resumo de atividade no GitHub" />
</picture>

</div>

## Contato

Estou aberto a conversar sobre arquitetura, engenharia de software e produtos digitais.

- [LinkedIn](https://www.linkedin.com/in/alexandre-roberto-souza-software-engineer/)
- [DevsForYou](https://devsforyou.com.br/)
- Belo Horizonte, Minas Gerais, Brasil

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=ALRSO85&label=visitas&color=6e7681&style=flat-square" alt="Visualizações do perfil" />
</p>
