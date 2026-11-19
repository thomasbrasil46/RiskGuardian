# 🛡️ RiskGuardian

### Plataforma de Orquestração e Análise de Risco para Transações Financeiras

![Status](https://img.shields.io/badge/Status-Em%20desenvolvimento-yellow)
![.NET](https://img.shields.io/badge/.NET-10-512BD4?logo=dotnet)
![C#](https://img.shields.io/badge/C%23-Backend-239120?logo=sharp)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Sobre o projeto

O **RiskGuardian** é um projeto de estudo e portfólio voltado ao desenvolvimento de uma plataforma de análise de risco e prevenção a fraudes em transações financeiras.

A proposta é simular um cenário do setor financeiro no qual diferentes sinais de risco precisam ser coletados, processados e avaliados para apoiar decisões automatizadas sobre transações.

O sistema será desenvolvido com foco em **engenharia de software backend, arquitetura distribuída, resiliência, segurança e observabilidade**, utilizando o ecossistema C#/.NET.

Mais do que construir uma API funcional, o projeto busca explorar desafios técnicos relacionados à construção de aplicações confiáveis, escaláveis e de fácil manutenção.

> **Nota:** Este é um projeto educacional independente. Não representa uma solução bancária real e não possui vínculo com qualquer instituição financeira. Dados, critérios e políticas de risco utilizados serão fictícios.

---

## 🎯 Objetivos

- Desenvolver APIs RESTful utilizando ASP.NET Core.
- Aplicar princípios SOLID, Clean Architecture e boas práticas de desenvolvimento.
- Modelar regras de negócio para análise e classificação de riscos.
- Explorar comunicação síncrona e assíncrona entre serviços.
- Implementar padrões de resiliência e tolerância a falhas.
- Garantir idempotência e consistência no processamento de eventos.
- Estudar orquestração de processos de negócio com BPMN.
- Implementar testes automatizados e observabilidade.
- Investigar estratégias de segurança, CI/CD e implantação em cloud.

## ⚙️ Funcionalidades planejadas

### Análise de transações

Recebimento de solicitações de avaliação de risco por meio de uma API REST.

Cada solicitação poderá conter informações como valor, identificador do cliente, dispositivo utilizado e destinatário da transação.

### Motor de pontuação de risco

Avaliação de sinais com base em regras configuradas, produzindo uma pontuação e uma decisão.

| Score | Classificação | Decisão |
|---|---|---|
| 0–39 | Baixo risco | `APPROVED` |
| 40–69 | Risco moderado | `REVIEW` |
| 70–100 | Alto risco | `REJECTED` |

*Intervalos iniciais ilustrativos, sujeitos à evolução das regras de negócio.*

### Integração com fornecedores de sinais

Simulação de serviços externos responsáveis por fornecer informações sobre:

- Reputação de dispositivos.
- Comportamento transacional.
- Histórico e reputação de destinatários.
- Frequência de operações.

### Processamento orientado a eventos

Publicação e consumo de eventos relacionados às avaliações de risco, permitindo o desacoplamento de atividades como auditoria e notificações.

### Orquestração de processos

Utilização de BPMN para modelar fluxos de decisão automática, encaminhamento para revisão e tratamento de exceções.

### Auditoria e rastreabilidade

Registro das decisões, regras aplicadas e eventos relevantes para permitir a análise e o acompanhamento das operações.

---

## 🏗️ Arquitetura

O desenvolvimento seguirá uma abordagem incremental.

Inicialmente, o domínio e as regras de negócio serão implementados em uma aplicação modular. Posteriormente, determinados componentes poderão ser extraídos para serviços independentes, conforme os requisitos de comunicação, escalabilidade e isolamento de falhas.

### Componentes previstos

| Componente | Responsabilidade |
|---|---|
| Risk Orchestrator | Receber e coordenar solicitações de análise |
| Signals Provider | Disponibilizar sinais de risco simulados |
| Risk Scoring Engine | Calcular pontuações e aplicar políticas de decisão |
| Workflow Engine | Orquestrar processos de análise e revisão |
| Message Broker | Distribuir eventos de forma assíncrona |
| Audit Worker | Consumir eventos e manter registros de auditoria |

### Princípios arquiteturais

O projeto buscará aplicar:

- Clean Architecture e separação de responsabilidades.
- Domain-Driven Design (DDD), quando adequado à complexidade do domínio.
- Dependency Injection e inversão de dependências.
- Event-Driven Architecture.
- Transactional Outbox e processamento idempotente.
- Circuit Breaker, Retry e Timeout.
- Observabilidade e rastreamento distribuído.

As decisões técnicas e seus trade-offs serão documentados durante o desenvolvimento.

---

## 🛠️ Tecnologias

As tecnologias abaixo compõem a stack planejada e serão incorporadas progressivamente.

| Categoria | Tecnologias |
|---|---|
| Linguagem | C# |
| Framework | .NET 10 / ASP.NET Core |
| Persistência | PostgreSQL / Entity Framework Core |
| Mensageria | RabbitMQ |
| Resiliência | Polly |
| BPM | Camunda 8 |
| Containers | Docker / Docker Compose |
| Testes | xUnit / Testcontainers |
| Observabilidade | OpenTelemetry / Prometheus / Grafana |
| Testes de carga | k6 |
| CI/CD | GitHub Actions |
| Cloud | AWS ou Azure (a definir) |

---

## 🔄 Fluxo de análise de risco

O fluxo conceitual de avaliação seguirá as seguintes etapas:

1. **Recebimento:** a API recebe uma solicitação de avaliação.
2. **Validação:** os dados da requisição são validados.
3. **Coleta de sinais:** os serviços responsáveis fornecem informações relevantes.
4. **Pontuação:** o motor aplica as políticas de risco.
5. **Decisão:** a transação é classificada como aprovada, rejeitada ou encaminhada para revisão.
6. **Persistência:** o resultado da avaliação é armazenado.
7. **Publicação:** eventos são disponibilizados para consumidores assíncronos.
8. **Auditoria:** o histórico da operação é registrado.

O fluxo deverá considerar falhas de integração, solicitações duplicadas e indisponibilidade temporária de dependências.

---

## 📚 Documentação técnica

Conforme o projeto evoluir, serão disponibilizados materiais referentes à arquitetura, modelagem do domínio, contratos da API, decisões arquiteturais e resultados de testes.

O propósito é documentar não apenas as soluções implementadas, mas também o raciocínio técnico, as alternativas consideradas e os trade-offs envolvidos.

## 🚧 Status do projeto

**Em desenvolvimento — fase inicial.**

O projeto será construído de maneira incremental. Funcionalidades, componentes e documentos apresentados neste README representam o planejamento inicial e poderão ser revisados conforme os desafios identificados durante a implementação.

## 👨‍💻 Autor

**Thomas Brasil**

Desenvolvedor de Software com foco em engenharia backend, C#/.NET, arquitetura de software e sistemas distribuídos.

- [GitHub](https://github.com/thomasbrasil46)
- [LinkedIn](https://www.linkedin.com/in/thomasbrasil46/)

---

*RiskGuardian — Projeto independente de estudo e experimentação em engenharia de software para sistemas financeiros.*