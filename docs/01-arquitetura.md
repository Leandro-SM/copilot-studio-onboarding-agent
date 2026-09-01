# 01 – Arquitetura do Disparo Automático

Este documento descreve, de forma **genérica**, os componentes envolvidos no disparo automático de mensagens de onboarding com um agente do Copilot Studio.

## Componentes

| Componente | Papel |
|-----------|-------|
| **Fonte do evento** | Origem que sinaliza a entrada de um novo usuário (ex.: cadastro em um sistema, entrada em um grupo, linha nova em uma tabela). |
| **Camada de orquestração** | Responsável por detectar o evento e acionar o agente. Pode ser um fluxo de automação, um agendamento ou um webhook. |
| **Agente Copilot Studio** | Conduz a conversa de onboarding: mensagem de boas-vindas, tópicos, ações e coleta de informações. |
| **Fontes de conhecimento** | Conteúdo público/interno autorizado (FAQ, guias) que o agente usa para responder dúvidas. |
| **Canal de entrega** | Onde a mensagem chega ao usuário (ex.: Teams, site, aplicativo). |

## Fluxo lógico

1. Um **novo usuário** é registrado na fonte do evento.
2. A **orquestração** identifica o evento (por agendamento ou em tempo real).
3. O **agente** é acionado e inicia a **sequência de onboarding**.
4. O agente entrega as mensagens no **canal** configurado.
5. Interações e métricas são **monitoradas** para melhoria contínua.

## Padrões de acionamento

Existem dois padrões principais (detalhados em `02-gatilhos-e-automacao.md`):

- **Agendado**: a orquestração verifica periodicamente novos usuários (ex.: de hora em hora, diariamente).
- **Orientado a evento**: a entrada de um novo usuário dispara imediatamente o fluxo.

## Princípios de projeto

- **Idempotência**: garanta que o mesmo usuário não receba a sequência duplicada.
- **Desacoplamento**: a fonte do evento não precisa conhecer o agente diretamente; a orquestração faz a ponte.
- **Observabilidade**: registre o que foi enviado, quando e o resultado.
- **Privacidade desde o design**: minimize os dados trafegados (ver `04-seguranca-e-privacidade.md`).
