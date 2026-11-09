<div align="center">

<picture>
  <source media="(min-width: 481px)" srcset="./assets/profile-visual.svg" />
  <img src="./assets/profile-visual-mobile.svg" alt="Arte abstrata com conexões em tons de azul e verde, representando arquitetura e sistemas digitais" />
</picture>

# Alexandre Souza

**Software Architect · Senior Software Engineer · AI Engineer**

**.NET · Distributed Systems · Cloud Architecture · AI Engineering · Digital Products**

Arquiteto de Software e Engenheiro de Software Sênior, sou responsável pelo desenho, arquitetura e construção de produtos da [DevsForYou](https://devsforyou.com.br/), incluindo WorkTime, SportsForYou e ReleaseHub. Com foco em .NET e modernização, conecto decisões arquiteturais às necessidades de negócio e acompanho as soluções da concepção à operação.

[LinkedIn](https://www.linkedin.com/in/alexandre-roberto-souza-software-engineer/) · [DevsForYou](https://devsforyou.com.br/) · [SportsForYou](https://sportsforyou.com.br/)

**Cases técnicos:** [WorkTime — integração idempotente](https://github.com/ALRSO85/worktime-showcase#integra%C3%A7%C3%B5es-resilientes) · [SportsForYou — worker independente](https://github.com/ALRSO85/sportsforyou-showcase#architecture-decision-independent-background-processing) · [ReleaseHub — rollback com reconciliação](https://github.com/ALRSO85/releasehub-showcase#recupera%C3%A7%C3%A3o-de-rollback)

**Navegação:** [Cases](#projetos-em-destaque) · [Outros produtos](#outros-produtos) · [Open source](#open-source) · [Engenharia de IA](#engenharia-de-ia) · [Competências](#compet%C3%AAncias-t%C3%A9cnicas) · [Segurança](#seguran%C3%A7a-aplicada) · [GitHub](#github) · [Contato](#contato)

</div>

---

## Projetos em destaque

Cases que demonstram arquitetura de software, engenharia .NET, integrações e governança de releases.

### [WorkTime](https://worktime.devforyou.com.br/)

Aplicação para gestão e conciliação de horas, jornadas, equipes, férias, fechamentos, auditoria e relatórios.

- **Cenário e desafio:** conciliar apontamentos internos e externos preservando a rastreabilidade, inclusive quando o provedor não confirma se processou um envio.
- **Decisão:** reservar cada escrita com uma chave idempotente antes da chamada; diante de confirmação incerta, registrar `Unknown` e não reenviar automaticamente.
- **Efeito técnico e princípio:** falha confirmada e resultado incerto são estados distintos. Retries automáticos ficam restritos a `GET` e `HEAD` transitórios; escritas exigem conferência antes de nova tentativa.

- **Integrações:** Businessmap/Kanbanize, com sincronização de apontamentos, e Ahgora, com importação de horas.
- **Stack:** `C#` `.NET 10` `ASP.NET Core` `EF Core` `SQL Server`
- **Infra:** `Ubuntu Server` · `Cloudflare Tunnel`
- [Entrar no WorkTime](https://worktime.devforyou.com.br/) · [Ver showcase técnico](https://github.com/ALRSO85/worktime-showcase) · [Pontos para entrevista](https://github.com/ALRSO85/worktime-showcase/blob/main/docs/interview-talking-points-ptbr.md)

---

### [SportsForYou](https://sportsforyou.com.br/)

Plataforma esportiva para atletas, organizadores, comunidades e parceiros, com eventos, perfis e integrações.

- **Cenário e desafio:** a plataforma combina módulos web com tarefas assíncronas que precisam de ciclo operacional próprio.
- **Decisão:** executar o `JobCenter` como serviço .NET Worker separado, com container, health check e ciclo de operação próprios.
- **Efeito técnico e princípio:** o processamento em segundo plano tem uma fronteira operacional explícita, separada da aplicação web.

- **Engenharia:** arquitetura modular, qualidade automatizada, governança de dados, acessibilidade e SEO.
- **Stack:** `C#` `.NET 10` `ASP.NET Core` `SQL Server` `Docker`
- **Infra:** `Ubuntu Server` · `Cloudflare Tunnel`
- [Acessar produto](https://sportsforyou.com.br/) · [Ver showcase técnico](https://github.com/ALRSO85/sportsforyou-showcase) · [Pontos para entrevista](https://github.com/ALRSO85/sportsforyou-showcase/blob/main/docs/interview-talking-points-ptbr.md) · [Artigo sobre arquitetura modular](https://pt.linkedin.com/pulse/arquitetura-modular-aplicada-uma-plataforma-digital-para-souza-g8btf)

---

### [ReleaseHub](https://releasehub.devforyou.com.br/)

Plataforma self-hosted para governança e execução de releases, com aprovações, validações e auditoria.

- **Cenário e desafio:** um rollback altera o ambiente remoto e o catálogo local em etapas; uma falha entre elas pode deixar os estados divergentes.
- **Decisão:** reservar a operação como `Revertendo`, confirmar o rollback remoto e atualizar o catálogo antes de concluir como `Revertida`; manter falhas explícitas e reconciliáveis.
- **Efeito técnico e princípio:** o sistema não declara sucesso antes de confirmar e reconciliar os estados; operações recuperáveis usam uma chave idempotente.

- **Engenharia:** rastreabilidade de artefatos e políticas de integridade para releases.
- **Stack:** `.NET 10` `ASP.NET Core` `Docker` `SQL Server`
- **Infra:** `Ubuntu Server` · `Cloudflare Tunnel`
- [Entrar no ReleaseHub](https://releasehub.devforyou.com.br/) · [Ver showcase técnico](https://github.com/ALRSO85/releasehub-showcase) · [Pontos para entrevista](https://github.com/ALRSO85/releasehub-showcase/blob/main/docs/interview-talking-points-ptbr.md)

## Outros produtos

### [Chegou Inteiro](https://chegouinteiro.devforyou.com.br/)

Plataforma para consulta regional de experiências de entrega.

- **Estado da demonstração:** exemplos sintéticos, sem cobertura real comprovada; novos cadastros e relatos estão desativados.
- **Stack:** `ASP.NET Core MVC` · `Ubuntu Server` · `Docker`
- [Acessar demonstração](https://chegouinteiro.devforyou.com.br/) · [Ver showcase técnico](https://github.com/ALRSO85/chegouinteiro-showcase)

### [Doguinhos 220v](https://doguinhos220v.com.br/)

Portal pet com artigos, eventos, vídeos e recomendações de produtos.

- **Contribuição:** desenvolvimento do portal pela DevsForYou.
- **Stack:** `PHP 8.5` · `Bootstrap 5.3` · `Ubuntu Server` · `Apache`
- [Acessar portal](https://doguinhos220v.com.br/) · [Ver showcase técnico](https://github.com/ALRSO85/doguinhos-showcase)

## Open source

**[FingerBridge](https://github.com/ALRSO85/fingerbridge)** — Projeto open source criado e mantido por mim: biblioteca para integrar leitores biométricos a aplicações Windows em .NET Framework 4.8, com providers independentes.

`C#` `.NET Framework` `WinForms` `Biometria` · [Licença MIT](https://github.com/ALRSO85/fingerbridge/blob/main/LICENSE) · [Explorar repositório](https://github.com/ALRSO85/fingerbridge)

## Engenharia de IA

Tenho aprofundado meus estudos em engenharia de IA e explorado o uso de LLMs no desenvolvimento de software. No [showcase do SportsForYou](https://github.com/ALRSO85/sportsforyou-showcase#what-this-demonstrates), descrevo fluxos assistidos por IA para documentação, análise de logs, planejamento arquitetural e decisões de engenharia. Também escrevi sobre [arquitetura AI-First no ecossistema .NET](https://pt.linkedin.com/pulse/ai-first-software-architecture-o-que-muda-quando-artificial-souza-mjcgf), abordando orquestração, busca semântica e guardrails.

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

Parte da minha atuação acontece em repositórios privados e ambientes corporativos. Os cartões abaixo são gerados pela [GitHub Action](.github/workflows/profile-summary-cards.yml) e podem não refletir toda essa atividade.

<div align="center">

<picture>
  <source media="(max-width: 480px) and (prefers-color-scheme: dark)" srcset="./profile-summary-card-output/mobile/github_dark/0-profile-details.svg" />
  <source media="(min-width: 481px) and (prefers-color-scheme: dark)" srcset="./profile-summary-card-output/github_dark/0-profile-details.svg" />
  <source media="(min-width: 481px)" srcset="./profile-summary-card-output/github/0-profile-details.svg" />
  <img src="./profile-summary-card-output/mobile/github/0-profile-details.svg" alt="Resumo de atividade no GitHub" />
</picture>

</div>

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./profile-summary-card-output/github_dark/2-most-commit-language.svg" />
  <img src="./profile-summary-card-output/github/2-most-commit-language.svg" width="320" alt="Linguagens com mais commits nos repositórios analisados pelo GitHub" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./profile-summary-card-output/github_dark/3-stats.svg" />
  <img src="./profile-summary-card-output/github/3-stats.svg" width="320" alt="Estatísticas do GitHub: estrelas, commits, pull requests, issues e repositórios contribuídos" />
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
