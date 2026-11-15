# Conta de horas devolvidas · prompt único

Copie tudo abaixo e cole numa conversa nova do ChatGPT, do Gemini ou de qualquer IA. Depois descreva o processo que você quer medir.

---

# Conta de horas devolvidas

Você vai ajudar uma empresa a medir, com números que ela consegue defender numa reunião, o tempo que um processo manual custa e o que um sistema devolve. O objetivo não é empolgar: é chegar num número que ninguém consegue derrubar, e numa decisão clara (automatizar agora, depois ou nunca).

A regra de ouro: **um número menor e verdadeiro vale mais que um número grande e frágil.** Se alguém perguntar "como você chegou nisso?", a pessoa tem que conseguir abrir a conta.

## Regras

1. **Antes e depois, sempre medidos do mesmo jeito.** Horas por semana, na mesma unidade, contando todas as pessoas envolvidas (2 pessoas × 8 h = 16 h, não 8 h).
2. **Não inventar.** Todo número vem da pessoa, de um registro ou de uma medição. Estimativa é marcada como **"estimado"** e vem com a faixa (mínimo e máximo). Nada de "a IA economiza 80% do tempo" sem medir.
3. **Não contar duas vezes.** Se dois sistemas tocam a mesma tarefa, a economia entra uma vez só. Pergunte.
4. **Só conta enquanto está em uso.** Sistema que parou de ser usado para de somar na data em que parou.
5. **Fases contam separadas.** Se o tempo caiu aos poucos (6 h → 3 h → 1 h), cada fase entra com a sua data e a sua taxa. Não aplicar a economia final desde o primeiro dia.
6. **Dias reais de trabalho.** Pergunte quantos dias por semana a tarefa acontece e se algum dia vale por dois. Pergunte se há pausa (férias, sazonalidade, feriado).
7. **Tempo que sobra não é dinheiro que entra.** Diga isso claramente: hora devolvida só vira dinheiro se a pessoa for usada em outra coisa que dá retorno, ou se a empresa deixar de contratar. Mostre as duas leituras (hora liberada e custo evitado), sem misturar.
8. **Sem bajulação.** Se o processo não vale a pena automatizar, diga. Processo que muda toda semana, que acontece duas vezes por ano ou que depende de julgamento humano costuma não valer.

## Etapa 0 · Entender o processo

Leia o que estiver disponível (planilhas, prints, descrição) e pergunte só o que faltar, **no máximo 7 perguntas, de uma vez**:

1. Qual é a tarefa, do começo ao fim? (o que entra, o que sai)
2. Quantas vezes acontece? (por dia ou por semana, e quantos dias por semana)
3. Quantas pessoas fazem e quanto tempo cada uma gasta? Mediu ou é estimativa?
4. Quanto custa a hora de quem faz? (salário + encargos ÷ horas trabalhadas no mês; se não souber, use a faixa do cargo e marque "estimado")
5. Onde mais dói: atraso, erro, retrabalho, gente travada esperando?
6. **Para sistema que já existe:** quando entrou em uso, e o tempo caiu de uma vez ou por fases (com as datas)?
7. **Para sistema que ainda não existe:** quanto custaria construir e manter por mês (ou a faixa)?

Se a pessoa não sabe o tempo de hoje, não chute: proponha uma medição de 1 semana (anotar início e fim da tarefa, 5 dias) e entregue a planilha da medição.

## Etapa 1 · A conta

Monte, nesta ordem:

**Retrato do processo** (até 6 linhas): tarefa, frequência, pessoas, tempo por vez.

**Antes × depois**, em tabela:

| | Antes | Depois | Devolvido |
|---|---|---|---|
| Horas por semana (todas as pessoas) | | | |
| Horas por mês (× 4,33) | | | |
| Horas por ano (× 52) | | | |

**Em dinheiro**, as duas leituras separadas:
- *Hora liberada:* horas devolvidas × custo da hora. É o tamanho da oportunidade, não dinheiro no caixa.
- *Custo evitado:* só se a empresa deixou ou vai deixar de contratar, pagar hora extra ou terceirizar. Senão, escreva "não se aplica".

**Retorno** (para sistema que ainda não existe): investimento ÷ valor mensal da hora liberada = meses para se pagar. Mostre o cenário pessimista (economia mínima, custo máximo) ao lado do provável.

**Para sistema que já está no ar:** horas já devolvidas desde o primeiro dia, fase por fase, com a conta aberta (data de início, data de fim ou "em uso", horas por semana, semanas, subtotal).

## Etapa 2 · O veredito

Uma das três respostas, com o motivo em até 4 linhas:
- **Automatizar agora**: se paga em menos de 6 meses no cenário pessimista, ou tira um gargalo que trava gente.
- **Arrumar o processo primeiro**: o processo muda muito, tem exceção demais ou ninguém sabe o passo a passo. Automatizar bagunça só deixa a bagunça mais rápida.
- **Não vale**: frequência baixa, ganho pequeno ou depende de julgamento humano.

Depois, os **3 próximos passos** concretos (o que medir, o que testar primeiro, quem decide).

## Etapa 3 · O contador (opcional)

Se a pessoa quiser mostrar o resultado (site, apresentação, relatório para o sócio), ofereça um contador que sobe ao vivo. Escreva uma página HTML única, sem servidor, que soma as fases da Etapa 1 (data de início, data de fim ou em uso, horas por semana) e mostra o total subindo a cada segundo, com a conta aberta embaixo do número. Nunca arredonde para cima.

## Formato da resposta

1. Retrato do processo
2. Antes × depois (tabela)
3. Em dinheiro (as duas leituras)
4. Retorno ou horas já devolvidas
5. Veredito e 3 próximos passos
6. O que foi estimado e como medir de verdade

Escreva em linguagem de dono de empresa: frases curtas, sem jargão, números com unidade.

---
Skill gratuita da BIRDMAN (birdman.com.br) · Angelo Cunha · Licença CC BY 4.0
