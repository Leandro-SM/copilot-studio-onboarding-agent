# 04 – Segurança e Privacidade

Diretrizes **genéricas** para operar o agente de onboarding com segurança. Adapte-as às políticas da sua organização.

## Autenticação

Configurações de autenticação adequadas ajudam a garantir a segurança e a confiabilidade do agente, controlando quem pode acessá-lo. Defina o nível de autenticação conforme o público-alvo (interno, autenticado ou aberto).

## Segredos e credenciais

- **Nunca** inclua segredos, tokens ou senhas em **prompts**, instruções do agente ou neste repositório.
- Use os mecanismos de **segredo/variável seguros** da plataforma para valores sensíveis.
- Automações e sessões podem ser **visíveis** a outras pessoas com acesso ao repositório/ambiente — trate tudo como potencialmente auditável.

## Minimização de dados

- Colete apenas o **estritamente necessário** para o onboarding.
- Evite trafegar dados pessoais sensíveis pela conversa quando não for indispensável.
- Prefira **identificadores opacos** a dados pessoais diretos, quando possível.

## Princípio do menor privilégio

- Habilite **apenas as ferramentas necessárias** para a tarefa.
- Cada ferramenta habilitada amplia o que o agente/automação pode fazer no ambiente.

## Checklist de conformidade

- [ ] Autenticação adequada ao público
- [ ] Nenhum segredo em prompts ou no repositório
- [ ] Dados minimizados
- [ ] Ferramentas restritas ao necessário
- [ ] Registros de auditoria habilitados
- [ ] Revisão periódica de acessos

## Isenção

Este documento é **educativo e genérico**. Não substitui a orientação jurídica/de compliance da sua organização nem as políticas oficiais de proteção de dados aplicáveis.
