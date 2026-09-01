# 03 – Mensagens de Onboarding

Guia **genérico** para estruturar a sequência de mensagens de boas-vindas do agente.

## A mensagem introdutória

A mensagem introdutória substitui a saudação padrão e é a primeira impressão do agente. Uma boa mensagem introdutória deve **cumprimentar o usuário, dizer o que o agente faz e como começar a interagir**, podendo incluir um exemplo de pergunta.

### Exemplo (genérico)

```
Olá! 👋 Sou seu assistente de boas-vindas.
Estou aqui para te ajudar a dar os primeiros passos.

Você pode me perguntar coisas como:
• "Por onde eu começo?"
• "Quais recursos estão disponíveis?"
• "Como falo com o suporte?"
```

## Prompts sugeridos

Você pode configurar prompts sugeridos que aparecem na página de boas-vindas do agente, antes do início da conversa, para orientar o usuário sobre como iniciar a interação.

Exemplos:
- "Por onde começar?"
- "Mostrar checklist inicial"
- "Falar com o suporte"

## Estrutura recomendada da sequência

| Etapa | Mensagem | Objetivo |
|-------|----------|----------|
| 1 | Boas-vindas | Acolher e explicar o propósito |
| 2 | Orientação | Apresentar os primeiros passos / checklist |
| 3 | Recursos | Indicar guias, FAQ e materiais úteis |
| 4 | Coleta | (Opcional) Perguntar preferências básicas |
| 5 | Suporte | Explicar como obter ajuda humana |

## Boas práticas de escrita

- **Tom consistente**: defina o tom nas instruções do agente (ex.: acolhedor e claro).
- **Mensagens curtas**: prefira blocos objetivos e escaneáveis.
- **Uma ação por mensagem**: evite sobrecarregar o usuário.
- **Sempre ofereça saída para humano**: nem tudo o agente resolve.

## Testando

Use o chat de teste do Copilot Studio para validar as mensagens. Reinicie a sessão de teste para revisar a mensagem introdutória a cada ajuste.

> **Observação**: prompts sugeridos são destinados a canais como Teams e Microsoft 365 e não aparecem no chat de teste do Copilot Studio.
