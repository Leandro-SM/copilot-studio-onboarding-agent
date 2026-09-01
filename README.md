# Copilot Studio – Agente de Onboarding Automático

Template **genérico e reutilizável** para disparar mensagens de **onboarding** automaticamente por meio de um agente do **Microsoft Copilot Studio**.

Este repositório é **agnóstico de organização**: não contém dados, credenciais, endpoints ou processos de nenhuma empresa específica. Use-o como ponto de partida para construir seu próprio fluxo de boas-vindas.

## 🎯 Objetivo

Quando um novo usuário entra (novo colaborador, novo cliente, novo membro de comunidade), o agente envia uma **sequência de mensagens de boas-vindas** — apresentando recursos, coletando informações iniciais e respondendo dúvidas comuns — sem intervenção manual.

## 🧩 Como funciona (visão geral)

```mermaid
flowchart LR
    A[Novo usuário<br/>registrado] --> B{Camada de<br/>orquestração}
    B -->|Agendado| C[Verificação<br/>periódica]
    B -->|Evento| D[Disparo<br/>imediato]
    C --> E[Agente<br/>Copilot Studio]
    D --> E
    E --> F[Sequência de<br/>onboarding]
    F --> G[/Canal de entrega/]
    G --> H([Teams])
    G --> I([Site / Web])
    G --> J([E-mail])
    E -.consulta.-> K[(Fontes de<br/>conhecimento)]
```

### Sequência de mensagens

```mermaid
sequenceDiagram
    participant U as Novo usuário
    participant O as Orquestração
    participant Ag as Agente Copilot Studio
    O->>Ag: Aciona onboarding (idempotente)
    Ag->>U: 1. Boas-vindas 👋
    Ag->>U: 2. Primeiros passos / checklist
    Ag->>U: 3. Recursos e FAQ
    U->>Ag: Dúvida?
    Ag->>U: Resposta (ou encaminha p/ suporte)
```

No Copilot Studio você descreve com suas próprias palavras o que quer que o agente faça, e a IA gera nome, descrição, instruções e sugere gatilhos, canais, fontes de conhecimento e ferramentas.

## 📚 Documentação

| Documento | Conteúdo |
|-----------|----------|
| [`docs/01-arquitetura.md`](docs/01-arquitetura.md) | Componentes e fluxo do disparo automático |
| [`docs/02-gatilhos-e-automacao.md`](docs/02-gatilhos-e-automacao.md) | Tipos de gatilho (agendado x evento) e boas práticas |
| [`docs/03-mensagens-onboarding.md`](docs/03-mensagens-onboarding.md) | Estrutura e exemplos de sequência de mensagens |
| [`docs/04-seguranca-e-privacidade.md`](docs/04-seguranca-e-privacidade.md) | Autenticação, segredos e dados sensíveis |
| [`docs/05-publicacao-por-canal.md`](docs/05-publicacao-por-canal.md) | Como publicar o agente em Teams, site e demonstração |
| [`templates/onboarding-sequence.example.json`](templates/onboarding-sequence.example.json) | Exemplo de configuração de sequência (fictício) |

## 🚀 Primeiros passos

1. Crie um agente no Copilot Studio descrevendo seu objetivo de onboarding.
2. Defina a **mensagem introdutória** (boas-vindas) — veja [`docs/03-mensagens-onboarding.md`](docs/03-mensagens-onboarding.md).
3. Configure o **gatilho** de disparo — veja [`docs/02-gatilhos-e-automacao.md`](docs/02-gatilhos-e-automacao.md).
4. Conecte fontes de conhecimento (FAQ, guias públicos).
5. Teste no chat de teste e **publique** em um canal — veja [`docs/05-publicacao-por-canal.md`](docs/05-publicacao-por-canal.md).

## ⚠️ Escopo e isenção

Este material é **educativo e genérico**. Ajuste-o à realidade e às políticas da sua organização. Não inclua segredos ou dados confidenciais em prompts ou neste repositório.

## Licença

MIT
