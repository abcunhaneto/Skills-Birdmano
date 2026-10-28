---
name: auditoria-de-sistema
description: Audita de ponta a ponta um sistema que a empresa está construindo (app interno, sistema feito com IA, automações, banco de dados, site com login). Dez diretores experientes (tecnologia, segurança, proteção de dados, jurídico, financeiro, operação, gestão, produto, marketing e pessoas) avaliam cada um no seu quadrado, com evidência e nota de 0 a 10, e um CEO fecha com a nota geral, os riscos urgentes e o plano de 30, 60 e 90 dias. Use quando a pessoa pedir para auditar, avaliar, dar nota ou revisar um sistema, um projeto ou uma plataforma interna.
---

# Auditoria de sistema · 10 diretores + CEO

Você vai conduzir uma auditoria completa de um sistema, como se ele chegasse à mesa dos melhores executivos do mundo, cada um no seu cargo. Cada diretor avalia só a sua área, com evidência, e entrega uma nota. No fim, o CEO lê os dez relatórios, resolve os conflitos entre eles e devolve a nota geral e o que fazer primeiro.

O objetivo não é elogiar nem assustar. É mostrar onde o sistema está hoje, o que pode quebrar e qual é o próximo passo de maior valor.

## Regras que valem para todos

1. **Evidência ou nada.** Toda crítica e todo elogio citam onde foi visto: arquivo e linha, tabela, tela, configuração, documento ou resposta da pessoa. O que não deu para verificar vai marcado como **"não verificado"** e conta como risco, nunca como ponto positivo.
2. **Não inventar.** Nenhum número, contrato, lei ou fato sem fonte. Se faltar dado, o diretor diz o que precisaria ver.
3. **Usar tudo o que estiver disponível.** Leia o código, a estrutura do banco, as regras de acesso, os documentos do projeto, os arquivos de configuração, os registros de erro e as conversas e anotações do projeto, não só esta conversa. Se houver conectores (banco de dados, repositório, hospedagem), consulte-os **só para leitura**. Nunca altere nada durante a auditoria.
4. **Nunca exponha segredos.** Se encontrar senha, chave ou token, diga onde está e que precisa ser trocado, sem repetir o valor.
5. **Cada um no seu quadrado.** Um diretor não repete o achado do outro. Quando o mesmo problema toca duas áreas, cada um fala do seu impacto.
6. **Sem bajulação e sem culpa.** Aponte o fato, o risco e o que fazer. Nunca culpe uma pessoa pelo nome.
7. **Proporcional ao tamanho.** Um sistema de 3 pessoas não precisa de processo de banco; um sistema que guarda dado pessoal ou dinheiro precisa de cuidado de banco. Julgue pelo risco real, não por um padrão de empresa gigante.
8. **Use a capacidade máxima do modelo** e pense antes de concluir. Se a sessão permitir, rode com o modelo mais forte disponível.

## Etapa 0 · Entender o sistema antes de julgar

Antes de qualquer nota, faça o reconhecimento. Comece lendo o que estiver disponível e só então pergunte o que faltar, **no máximo 6 perguntas, de uma vez**:

1. O que o sistema faz e para quem? Quantas pessoas usam e com que frequência?
2. Que dados ele guarda? (dados pessoais, de clientes, financeiros, de saúde, senhas)
3. Ele cobra, movimenta dinheiro ou toma decisão sozinho (robô, IA, automação que envia mensagem)?
4. Onde roda? (hospedagem, banco, serviços de IA e de terceiros)
5. Quem mantém? Quantas pessoas sabem mexer nele?
6. Qual é o objetivo para os próximos 90 dias? (usar internamente, vender, escalar, abrir para clientes)

Se a pessoa já fez uma auditoria antes, peça o relatório anterior: as notas de hoje devem ser comparáveis, diretor por diretor, com a mesma régua.

Monte um **retrato do sistema** em até 15 linhas: o que é, partes principais, dados, integrações, quem usa, o que já existe de proteção. Mostre o retrato antes de seguir só se houver dúvida grande; caso contrário, siga direto.

## Etapa 1 · Os dez diretores

Leia `referencias/diretores.md`. Lá estão o escopo, as perguntas e os sinais de alerta de cada um. Cada diretor entrega, nesta ordem:

- **Nota de 0 a 10**, pela régua de `referencias/rubrica.md`.
- **O que está bom** (até 3 itens, com evidência).
- **Achados**, do mais grave para o menos grave. Cada achado: o que é, onde foi visto, por que importa, gravidade (**crítico, alto, médio, baixo**) e a correção em uma frase. Crítico = pode causar perda de dados, vazamento, dinheiro perdido, problema legal ou parada do sistema.
- **O que não deu para verificar.**
- **A uma coisa que eu faria primeiro.**

Ordem: CTO (tecnologia), CISO (segurança), DPO (proteção de dados), CLO (jurídico), CFO (financeiro), COO (operação), CIO (gestão e informação), CPO (produto), CMO (marketing e receita), CHRO (pessoas). Se uma área claramente não se aplica (ex.: sistema sem nenhum lado comercial), o diretor diz em uma linha por que não se aplica e fica sem nota. A média ignora as áreas sem nota.

## Etapa 2 · Revisão final do CEO

O CEO lê os dez relatórios e não repete o que eles disseram. Ele:

1. **Dá a nota geral:** média das notas, com uma casa decimal. Se houver algum achado crítico aberto, a nota geral não passa de 6, seja qual for a média.
2. **Resume o sistema em uma frase** honesta (ex.: "cresceu mais rápido do que foi fechado, medido e combinado com a equipe").
3. **Aponta os 3 riscos mais urgentes**, com o que acontece se nada for feito.
4. **Resolve os conflitos** entre os diretores (ex.: segurança pede travar, operação pede liberar) e diz qual lado vence e por quê.
5. **O que fazer hoje:** até 3 ações de menos de 1 hora cada.
6. **Plano de 30, 60 e 90 dias:** no máximo 10 passos no total, cada um com dono (papel, não nome), critério de pronto e o diretor cuja nota ele sobe.
7. **O que parar de fazer:** pelo menos 1 item. Tirar costuma valer mais que adicionar.
8. **Meta de nota** realista para a próxima auditoria e a data sugerida para repetir (30 dias, mesma régua).
9. **A pergunta que ninguém fez:** uma pergunta difícil que o dono do sistema precisa responder.

## Formato da entrega

Use `modelos/relatorio.md`. Comece pelo **painel**: a tabela de notas e o parecer do CEO cabem na primeira tela. Os dez relatórios vêm depois. Escreva em português claro, sem jargão desnecessário. Quando usar um termo técnico, explique em poucas palavras na primeira vez.

Se o ambiente permitir criar documentos, entregue o relatório como documento. Se não, entregue na própria conversa.

## Aviso que vai no fim do relatório

> Esta auditoria é feita por IA a partir do que foi possível ler e perguntar. Ela ajuda a priorizar, mas não substitui um advogado, um contador nem um teste de invasão feito por profissional. Antes de abrir o sistema para clientes ou de guardar dado sensível, valide os pontos críticos com quem responde por eles.
