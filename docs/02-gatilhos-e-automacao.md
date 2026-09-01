# 02 – Gatilhos e Automação

Este documento explica, de forma **genérica**, como acionar o agente de onboarding.

## Tipos de gatilho

Automações costumam ser executadas de duas formas: **por agendamento** (em um intervalo recorrente) ou **em resposta a um evento**.

### 1. Agendado

A orquestração verifica periodicamente se há novos usuários e dispara a sequência.

- **Quando usar**: quando não há um evento em tempo real disponível, ou quando um pequeno atraso é aceitável.
- **Intervalos comuns**: de hora em hora, diário ou semanal.
- **Cuidado**: mantenha um controle de "já processado" para evitar reenvios.

### 2. Orientado a evento

A entrada de um novo usuário dispara o fluxo imediatamente (ex.: via webhook ou conector).

- **Quando usar**: quando a experiência exige boas-vindas imediatas.
- **Vantagem**: baixa latência.
- **Cuidado**: trate falhas e re-tentativas com idempotência.

## Boas práticas de automação

- **Descreva a tarefa com clareza**: ao configurar a automação, descreva de forma objetiva o que deve acontecer a cada execução.
- **Filtros**: quando disponível, use filtros para restringir quais eventos disparam o fluxo.
- **Selecione apenas as ferramentas necessárias** para a tarefa, seguindo o princípio do menor privilégio.
- **Nunca inclua segredos no prompt**. Para valores sensíveis, utilize mecanismos de segredo/variável seguros da plataforma.
- **Teste antes de produção**: execute a automação manualmente para validar o comportamento antes de depender do gatilho.

## Checklist de configuração

- [ ] Fonte do evento definida
- [ ] Padrão de acionamento escolhido (agendado x evento)
- [ ] Controle de idempotência implementado
- [ ] Ferramentas mínimas selecionadas
- [ ] Segredos fora do prompt
- [ ] Teste manual executado com sucesso
