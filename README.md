# Skills da BIRDMAN

Skills gratuitas que usamos no nosso próprio sistema interno, abertas para quem está construindo o seu. Funcionam no Claude, no Claude Code, no Codex, no Cursor e em outros agentes. Cada uma também tem um prompt único para ChatGPT e Gemini.

| Skill | O que faz | Página |
|---|---|---|
| [`auditoria-de-sistema`](skills/auditoria-de-sistema) | Dez diretores experientes (tecnologia, segurança, proteção de dados, jurídico, financeiro, operação, gestão, produto, marketing e receita, pessoas) auditam o seu sistema com evidência e nota de 0 a 10. No fim, um CEO devolve a nota geral, os 3 riscos mais urgentes, o que fazer hoje e o plano de 30, 60 e 90 dias. | [birdman.com.br/auditoria](https://birdman.com.br/auditoria/) |
| [`conta-de-horas`](skills/conta-de-horas) | Faz a conta honesta de quanto tempo um processo manual custa, quanto um sistema devolveria, quanto isso vale em dinheiro e em quanto tempo se paga. Termina com um veredito (automatizar agora, arrumar o processo primeiro ou não vale) e, se você quiser, monta um contador de horas devolvidas ao vivo. | [birdman.com.br/angelo](https://birdman.com.br/angelo/) |

## Como instalar

### Claude (app ou site)
1. Baixe o .zip da skill: [`auditoria-de-sistema.zip`](https://birdman.com.br/auditoria/auditoria-de-sistema.zip) ou [`conta-de-horas.zip`](https://birdman.com.br/skills/conta-de-horas.zip).
2. Configurações → Capacidades → ligue **Criar e editar arquivos** (funciona no plano grátis).
3. Personalizar → Skills → **+** → Criar skill → **Enviar uma skill** → escolha o .zip.
4. Numa conversa nova, de preferência dentro do projeto onde o seu sistema está:
   > Use a skill auditoria-de-sistema para auditar o meu sistema. Leia tudo o que estiver disponível no projeto antes de dar nota.

   > Use a skill conta-de-horas para medir quanto tempo o processo X custa hoje e se vale automatizar.

### Claude Code, Codex, Cursor, Gemini CLI e outros agentes
```
npx skills add abcunhaneto/Skills-Birdmano --skill auditoria-de-sistema
npx skills add abcunhaneto/Skills-Birdmano --skill conta-de-horas
```
Ou copie a pasta `skills/auditoria-de-sistema` para a pasta de skills do seu agente (no Claude Code, `~/.claude/skills/`).

### ChatGPT, Gemini ou qualquer outra IA
Abra o arquivo da skill em [`prompts/`](prompts) (por exemplo [`auditoria-de-sistema.md`](prompts/auditoria-de-sistema.md) ou [`conta-de-horas.md`](prompts/conta-de-horas.md)), copie tudo e cole numa conversa nova. Depois mande o que tiver do seu sistema: código, prints, descrição, documentos.
Num GPT personalizado ou num Gem, suba o arquivo como conhecimento e escreva nas instruções: "Siga o arquivo à risca."

## Dicas
- Use o modelo mais forte que você tiver.
- Quanto mais a IA conseguir ler do sistema (código, banco, documentos), melhor a auditoria.
- Repita depois de 30 dias com a mesma régua e compare nota por nota.

## Aviso
As auditorias são feitas por IA a partir do que ela consegue ler e perguntar. Ajudam a priorizar, mas não substituem advogado, contador nem um teste de invasão feito por profissional.

---
Feitas por **Angelo Cunha · BIRDMAN** (São José do Rio Preto). Licença [CC BY 4.0](LICENSE): use e adapte, citando a fonte.
