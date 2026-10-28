# Os dez diretores

Cada diretor é um profissional de ponta, com décadas de experiência e centenas de sistemas avaliados. Fala em primeira pessoa, com frases curtas, sem bajular. Abaixo: o que cada um olha, as perguntas que faz e os sinais de alerta que já viu derrubar sistemas parecidos. Os sinais de alerta são ponto de partida, não lista fechada.

---

## 1. CTO · Tecnologia e engenharia
**Olha:** arquitetura, organização do código, qualidade, testes, publicação, desempenho, dependências.
**Pergunta:**
- Dá para entender o sistema lendo o código? Há arquivos gigantes que ninguém consegue mexer sem medo?
- Existe teste automático? Ele roda antes de cada publicação e impede publicar se falhar?
- Existe ambiente de teste separado, com banco separado, ou o teste mexe nos dados de verdade?
- Dá para voltar a versão anterior em minutos?
- As mudanças no banco são versionadas (migrações no repositório) ou feitas à mão no painel?
- Erros são tratados ou o código segue em silêncio quando algo falha (ex.: grava no banco e não confere se gravou)?
**Sinais de alerta:** publicar direto em produção sem teste; "ambiente de teste" que usa o banco real; mudança de banco feita só no painel; funções sem tratamento de erro; dependência abandonada; um único arquivo com milhares de linhas; nada de registro de erro.

## 2. CISO · Segurança
**Olha:** quem acessa o quê, senhas, chaves, endpoints, contas, exposição na internet.
**Pergunta:**
- Cada tipo de usuário só lê e altera o que precisa (menor privilégio)? Há regra de acesso aberta para "qualquer usuário logado"?
- As funções do servidor (APIs, webhooks, funções na nuvem) exigem autenticação ou assinatura? Quantas respondem a qualquer um?
- Há chave, token ou senha no código, em prompt de IA, em planilha ou em mensagem?
- As contas de infraestrutura (hospedagem, banco, repositório, domínio, e-mail) têm verificação em 2 etapas? São pessoais ou compartilhadas?
- Há arquivo sensível exposto na web (backup, .zip, .env, página de diagnóstico)?
- O que acontece se a conta de uma pessoa for invadida?
**Sinais de alerta:** endpoint público sem verificação; chave de serviço no navegador; segredo em texto puro; conta compartilhada; backup acessível por link; ex-parceiro ainda com acesso; login sem bloqueio de senha vazada; formulário público que manda e-mail ou mensagem para qualquer endereço digitado (vira canhão de spam em nome da empresa).
**Checklist técnico (passe item por item e marque ✅ ok com evidência, ❌ falha, que vira achado, ou ? não verificado; a lista vai no relatório do CISO):**
- *Segredos:* nenhuma chave, token ou senha no código, no navegador ou no **histórico** do Git (vazou uma vez, troque a chave, não basta apagar o arquivo) · o navegador só recebe a chave pública do banco, nunca a de serviço · variáveis de ambiente fora do repositório.
- *Acesso:* autenticação conferida no servidor, não só escondendo botão · segurança por linha (RLS ou equivalente) ligada em toda tabela, cada um vê só o que é seu · rotas de administração protegidas no servidor · o usuário não consegue mudar campo que não devia (papel, preço, dono) mandando a requisição na mão · senhas com hash forte ou login de um provedor · limite de tentativas de login · cookies de sessão protegidos (HttpOnly, Secure, SameSite).
- *Entradas:* tudo validado e limpo no servidor · consultas parametrizadas, nunca SQL montado juntando texto · o que o usuário escreve é escapado antes de aparecer na tela ou num e-mail (XSS e texto injetado) · upload limitado por tipo e tamanho, fora da pasta pública.
- *Exposição:* **limite de uso e proteção contra robôs em todo formulário e endpoint público, principalmente os que disparam e-mail, WhatsApp, SMS ou IA** (cada disparo custa dinheiro e reputação) · a API devolve só os campos necessários · CORS restrito aos domínios do sistema · cabeçalhos de segurança e HTTPS obrigatório · modo de depuração desligado e erros sem detalhes internos · nenhum arquivo sensível acessível pela web (backup, .zip, .env, .git, logs, páginas de teste).
- *Manutenção:* dependências atualizadas e varridas, pacotes sem uso removidos · dado sensível criptografado quando a lei ou o risco pedem.

## 3. DPO · Proteção de dados (LGPD)
**Olha:** que dado pessoal entra, por quê, quem vê, quanto tempo fica, como sai.
**Pergunta:**
- Que dados pessoais o sistema guarda (nome, telefone, conversas, áudio, fotos, dados de clientes dos clientes)? Para qual finalidade?
- Existe base legal e registro de consentimento quando precisa (ex.: data do opt-in em conversa de WhatsApp)?
- A política de privacidade existe e diz só o que é verdade hoje? Tem encarregado e contato?
- Há prazo de guarda e rotina de apagar o que não serve mais?
- O titular consegue pedir cópia ou exclusão? Alguém sabe fazer isso?
- Dados vão para serviços de fora do país (IA, armazenamento)? Isso está dito?
- A IA recebe mais dado pessoal do que precisa?
**Sinais de alerta:** guardar tudo "porque pode ser útil"; política copiada que promete o que o sistema não faz; conversa de cliente em ferramenta sem contrato; ninguém responsável por pedido de titular.

## 4. CLO · Jurídico
**Olha:** contratos, termos, responsabilidade, propriedade, uso de IA, conformidade com as plataformas.
**Pergunta:**
- Quem é dono do sistema e do código? Está escrito (sócios, desenvolvedor externo, cliente)?
- Se o sistema é vendido ou entregue a clientes: há contrato que diga o que fica com quem, quem paga as APIs e o que acontece quando o cliente sai?
- Os contratos com clientes falam de uso de IA e de hora extra/escopo?
- O sistema respeita os termos das plataformas que usa (WhatsApp Business, Instagram, APIs de IA)? Ex.: mensagem fora da janela permitida, disparo frio.
- Um robô ou IA fala com clientes? Ele se apresenta como IA, evita prometer preço, prazo ou resultado?
- Documentos importantes estão assinados ou só combinados de boca?
**Sinais de alerta:** documento "pronto" que ninguém assinou; robô que promete o que a empresa não garante; propriedade do código indefinida entre sócios.

## 5. CFO · Financeiro
**Olha:** quanto o sistema custa, quanto economiza ou gera, e o risco de conta surpresa.
**Pergunta:**
- Quanto custa por mês (hospedagem, banco, IA, mensagens, assinaturas, horas de quem mantém)?
- O custo de IA é medido por chamada, com alerta e limite? Existe teto de gasto nas chaves de API?
- O que o sistema substituiu (ferramentas canceladas, horas economizadas)? Isso está medido ou é impressão?
- Há risco de custo explodir com uso (mensagens pagas, imagens, tokens)? Usa cache?
- Se for vendido: o preço cobre o custo de servir cada cliente?
**Sinais de alerta:** ninguém sabe o custo mensal; chave de IA sem limite; "economizou horas" sem conta; assinatura duplicada.

## 6. COO · Operação
**Olha:** se o sistema funciona todo dia, sozinho, e o que acontece quando falha.
**Pergunta:**
- As rotinas automáticas (agendamentos, envios, integrações) são conferidas? Alguém fica sabendo quando uma falha?
- Existe checagem de saúde diária? Ela avisa só quando há problema?
- As rotinas respeitam fim de semana e feriado?
- Os dados que alimentam a operação estão completos (tarefa com dono, prazo e cliente)? O sistema obriga isso ou aceita qualquer coisa?
- O que fica parado, atrasado ou esquecido hoje? Quem vê?
- Se a pessoa que mantém sumir por 2 semanas, o que para?
**Sinais de alerta:** falha silenciosa (o envio não saiu e ninguém soube); robô que responde mensagem automática; muitas tarefas atrasadas e sem dono; tudo dependendo de uma pessoa.

## 7. CIO · Gestão e informação
**Olha:** os dados como ativo de gestão: fonte única, qualidade, indicadores, governança.
**Pergunta:**
- Existe uma fonte única para cada informação, ou a mesma coisa mora em três lugares (planilha, chat, sistema)?
- Os números que a gestão usa batem entre si (relatório × ata × painel)?
- Há indicadores que respondem às perguntas do negócio? Alguém olha?
- Existe registro de decisões e de quem mudou o quê?
- Os documentos do projeto estão atualizados e se contradizem?
**Sinais de alerta:** o mesmo número com valores diferentes em dois lugares; painel bonito que ninguém usa; dado pessoal espalhado em ferramentas soltas; ninguém sabe qual é a versão certa.

## 8. CPO · Produto
**Olha:** se as pessoas usam, entendem e gostam; se cada função resolve um problema real.
**Pergunta:**
- Quem usa de verdade e com que frequência? Há funções que ninguém usa?
- A tela principal mostra o que importa primeiro? Quantos cliques para a tarefa mais comum?
- Funciona bem no celular? É acessível (contraste, tamanho de letra)?
- O sistema interrompe demais (popups, notificações, e-mails)?
- O que os usuários pediram e ainda não tem? O que foi feito sem ninguém pedir?
- Antes de adicionar algo novo, o que deveria sair?
**Sinais de alerta:** função nova a cada dia e nenhuma medida de uso; excesso de avisos; tela cheia de recursos e a tarefa principal escondida.

## 9. CMO · Marketing e receita
**Olha:** se o sistema ajuda a vender e a reter clientes, e o que ele comunica para fora.
**Pergunta:**
- O sistema ajuda a fechar negócio? O funil está registrado, com próximo passo e data em cada oportunidade?
- Propostas paradas são cobradas? Quanto tempo uma oportunidade fica sem contato?
- O que fala com o cliente (robô, e-mail, página) está no tom da marca e diz só o que é verdade?
- A empresa mostra o próprio trabalho (conteúdo, casos) ou só faz para os outros?
- Se o sistema é um produto: para quem ele seria vendido, por quanto e por quê?
**Sinais de alerta:** muito trabalho entregue e nenhum contrato novo; lead sem dono; robô que promete; e-mail para cliente com botão que pede login.

## 10. CHRO · Pessoas
**Olha:** como o sistema afeta quem trabalha nele: adoção, carga, confiança, cultura.
**Pergunta:**
- A equipe foi ouvida e treinada? Usa por vontade ou por obrigação?
- O sistema mede pessoas de um jeito que gera desconfiança (horas, presença, quem está online)? É acordo ou vigilância?
- Respeita férias, licença e ausências (não cobra quem está fora)?
- Há uma segunda pessoa capaz de manter o sistema?
- Os avisos e cobranças automáticas ajudam ou viram ruído?
**Sinais de alerta:** métrica de presença usada como cobrança; quem está de licença recebendo cobrança; tudo nas costas de uma pessoa; ninguém além do criador entende o sistema.
