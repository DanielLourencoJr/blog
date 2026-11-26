---
title: 'Analisando a escrita da Bolha'
date: '2026-09-01T13:40:16-03:00'
draft: false
tags:
  - substack
  - inteligência-artificial
  - deepseek
  - opencode
---

Esse é um texto diferente dos que eu costumo escrever. A ideia surgiu da discussão sobre a escrita do Sir Richard, que acompanhei pelo Volume 4 do Jornal da Bolha.

> [Jornal da Bolha - Volume 4](https://jornaldabolha.substack.com/p/jornal-da-bolha-volume-4)

Pensei em fazer uma análise da escrita do máximo de pessoas possível desse canto da internet e tirar a prova de quão bons — ou ruins — são os textos da galera.

---

### Metodologia

Como quero incluir o máximo de pessoas possível e manter o julgamento mais imparcial possível, optei por montar um processo de avaliação automatizado com um *Large Language Model(LLM)* fazendo leitura cega de todos os textos e atribuindo notas de acordo com uma rubrica.

---

### Rubrica

São seis critérios analisados e cada um recebe uma nota de 1 a 5.

#### **1. CLAREZA DE PROSA**

O quanto o leitor entende de primeira, sem precisar reler.

- **1** = frases confusas, ambíguas ou mal construídas; exige releitura constante
- **2** = clareza inconsistente; parágrafos inteiros exigem esforço
- **3** = geralmente claro, com alguns trechos que travam a leitura
- **4** = claro na quase totalidade; tropeços raros e pontuais
- **5** = fluido do início ao fim; nenhuma frase exige releitura

#### **2. CONTROLE DE VOZ**

Se existe uma voz/estilo consistente e intencional, não apenas prosa neutra ou inconsistente.

- **1** = sem voz perceptível, ou voz que muda sem motivo aparente
- **2** = voz presente mas inconsistente ao longo do texto
- **3** = voz reconhecível, com alguns deslizes de tom
- **4** = voz consistente e claramente intencional
- **5** = voz distintiva, difícil de confundir com a de outro autor

#### **3. ESTRUTURA E PROGRESSÃO**

Se o texto vai a algum lugar — constrói, desenvolve, chega a algo — em vez de apenas existir ou se repetir.

- **1** = sem progressão perceptível; estático ou desorganizado
- **2** = alguma progressão, mas com partes redundantes ou deslocadas
- **3** = progressão clara, ainda que previsível ou com ritmo desigual
- **4** = progressão bem construída, proporções adequadas
- **5** = estrutura precisa; cada parte tem função e o conjunto tem arco definido

#### **4. DENSIDADE DE IDEIA/IMAGEM**

Quanto de substância real por frase — sem enchimento, redundância ou preenchimento vazio.

- **1** = majoritariamente enchimento; pouca substância por frase
- **2** = substância presente mas diluída em excesso de palavras
- **3** = equilíbrio razoável entre substância e economia
- **4** = texto enxuto; quase nada sobra
- **5** = cada frase carrega peso; nenhuma palavra é desperdiçada

#### **5. ORIGINALIDADE**

Se foge do previsível — em ideia, imagem, argumento ou abordagem — em vez de repetir o já muito visto.

- **1** = inteiramente clichê ou convencional
- **2** = majoritariamente previsível, com raros lampejos próprios
- **3** = mistura de convencional e abordagem pessoal
- **4** = perspectiva claramente própria na maior parte do texto
- **5** = abordagem ou visão difíceis de encontrar em outro lugar

#### **6. EXECUÇÃO TÉCNICA**

Gramática, pontuação, ortografia, polimento geral — o texto foi revisado?

- **1** = erros frequentes que atrapalham a leitura
- **2** = vários erros perceptíveis, mas leitura ainda possível
- **3** = poucos erros, sem prejuízo à leitura
- **4** = praticamente sem erros
- **5** = impecável; sinais claros de revisão cuidadosa

> Resumindo: “Deepseek, leia os textos do Substack e dê uma nota de 1 a 5. Não cometa erros. Não alucine.”

### Primeiro Passo

Antes de começar a analisar os textos eu preciso de uma coisa fundamental: os textos.

Já que eu não gostaria de esquecer ninguém, usei o método mais infalível para decidir quais textos incluir: todos os textos das contas que sigo.

Isso caiu bem rápido. Motivo: Alguns autores têm muitos textos (salve @História e Liberdade , @Kotal the frog of Pindorama ) e outros eu não sigo para não poluir meu feed ou simplesmente porque não conheço ainda. Porém queria incluir o máximo de gente, então limitei o número de textos a no máximo 20.

Ainda assim, são 32 pessoas e quase 400 textos. Aqui já fica bem claro que o uso de inteligência artificial não se dá por preguiça, mas por capacidade humana e tempo hábil. Quero terminar isso ainda esse mês.

Para esse empreendimento foi essencial o conhecimento que obtive sobre o Substack que comentei apenas superficialmente no seguinte texto:

> [Como o Substack Funciona?](https://danielloureno1.substack.com/p/como-o-substack-funciona)

Por volta do mês de junho eu aprendi como a página do Substack se comunica com os servidores para obter informações públicas como artigos, notes e imagens. Usando esses conhecimentos pude montar scripts para exportar todos os textos e salvar como Markdown — o formato perfeito para LLMs.

![](image-01.png)

Após desenvolver os scripts necessários para preparar e organizar os textos e usar OpenCode para gerenciar o contexto do modelo, de forma que as análises sejam consistentes, sem serem afetadas por avaliações passadas, recebo um relatório como esse:

```text
{
  "arquivo": "capitulo-3-a-primeira-vitoria.md",
  "autor": "Daniel",
  "path": "/mnt/windows/Junior/Projects/Essayer/textos/Daniel/capitulo-3-a-primeira-vitoria.md",
  "sha": "7e91399108cca7ed6439b30166f7162191d0af4dde9cc2f3fce144d6ec4d2d9e",
  "avaliado_em": "2026-08-17T17:51:26.892Z",
  "status": "ok",
  "clareza_prosa": {
    "nota": 3,
    "evidencia": "Não é como se uma coisa pequena como ganhar de um nobre arrogante fosse minha prioridade, mas isso refletia uma dificuldade real que eu teria com todos os meus oponentes no futuro."
  },
  "controle_voz": {
    "nota": 4,
    "evidencia": "Graças a minha habilidade praticamente inútil em batalha, precisava de estratégia ou força pura e absoluta para sobrepujar meu inimigo. Isso era a maior justificativa para as minhas conversas com Norn."
  },
  "estrutura_progressao": {
    "nota": 4,
    "evidencia": "Aquele tinha sido meu terceiro duelo oficial e minha primeira vitória."
  },
  "densidade_ideia": {
    "nota": 3,
    "evidencia": "Eram como bolhas opacas de sangue ou lava estourando na altura do chão, cada vez mais perto de mim."
  },
  "originalidade": {
    "nota": 3,
    "evidencia": "Meu estilo de combate envolve baixar meu centro de massa. Isso aumenta meu contato com o chão. Base sólida."
  },
  "execucao_tecnica": {
    "nota": 2,
    "evidencia": "— pudia sentir um tom de análise, como se ela não fosse suspeita para falar sobre."
  },
  "media": 3.17,
  "comentario_livre": "Capítulo com progressão clara e diálogos eficientes, mas o polimento técnico (erros como 'imediatamemte', 'pudia', 'alguem') compromete o acabamento; a premissa de academia mágica com duelos é convencional no gênero, embora a análise física de combate traga um toque próprio."
}
```

> Comentário livre: Capítulo com progressão clara e diálogos eficientes, mas o polimento técnico **(erros como ‘imediatamemte’, ‘pudia’, ‘alguem’)** compromete o acabamento; a premissa de academia mágica com duelos é convencional no gênero, embora a análise física de combate traga um toque próprio.

Ai, essa doeu T-T

E meu trabalho nesse texto será interpretar esse relatório para todos os textos e todos os autores, consolidando isso de uma forma interessante.

---

### O viés da máquina

Não sei se vocês sabem, mas tenho uma publicação que abandonei onde escrevia textos com IA chamada Prompted. Acidentalmente adicionei esses textos na *pipeline* de avaliação e notei um padrão. Esses textos recebiam notas consistentemente mais altas que qualquer escritor humano.

Isso faz certo sentido, ao mesmo tempo que é engraçado. Faz sentido pois a IA usa os próprios padrões de avaliação na hora de escrever, apesar dos textos serem escritos e avaliados por modelos diferentes. E é engraçado pois a IA reconhece seu próprio estilo de escrita como sendo o ápice da habilidade.

Você pode até mesmo pensar que esse teste mede o quão próximo de um modelo de linguagem você escreve. XD

Além disso também notei a penalização de defesas cristãs por entender que já são argumentos muito bem consolidados e nada originais.

---

### Análises

Serão só destaques de textos selecionados que você pode pular à vontade e ir direto para o autor que tem interesse. Estará disponível o relatório na íntegra ao final de cada seção. Vou linkar todos os textos que for comentar.

---

### Daniel Lourenço

Vou usar esse cara como exemplo pois é um dos poucos que eu acompanho de perto e já li todos os textos. Isso me ajuda a entender como a análise se comporta em um terreno que conheço.

---

> [A Culpa do Analfabetismo Funcional é da Matemática](https://danielloureno1.substack.com/p/a-culpa-do-analfabetismo-funcional)
>
> O maior erro quando tratam desse tema é atribuir a dificuldade de interpretar textos ao ensino da linguagem e da literatura.

Média de todos os critérios: 3

> Ensaio de tese polêmica e voz opinativa marcada, com arco argumentativo visível (tese, evidências, analogia do prédio, proposta), mas frases longas e encadeadas exigem releitura e o meio se dilui em panorama de conteúdos.

Vale destacar dois pontos levantados pelo analista: clareza da prosa(2) e controle de voz(4). Como evidência ele cita trechos com orações extremamente longas e uma frase de impacto, respectivamente:

> \[…\] restando somente as conclusões jogadas aos coitados com o mínimo de contexto possível enganando-os a acreditar que as aplicações das fórmulas aprendidas é a única coisa que há para ser aproveitada, \[…\]

> A solução não é ensinar **mais** matemática, isso seria ingênuo. É mudar a estrutura, o **como** matemática é ensinada.

---

> [Capítulo 4: Mentiroso por essência](https://danielloureno1.substack.com/p/capitulo-4-mentiroso-por-essencia)
>
> O auditório estava praticamente vazio, não porque haviam poucas pessoas, mas porque ele era grande o suficiente para abrigar toda a academia de uma vez. Apenas o primeiro ano, pouco menos de um terço do corpo estudantil, estava presente.

Média 3,33 e 2 para execução técnica.

> “Você não queria ser um mago à princípio.” (crasis indevida), ”não porque haviam poucas pessoas” (haver impessoal) e ”— Teo. — dei um aceno” (minúscula após ponto).

> Comentário final: Narrativa em primeira pessoa eficaz, com voz sarcástica consistente e bom manejo de subtexto nos diálogos, mas desgastada por erros gramaticais recorrentes e alguns trechos de atribuição confusa.

---

> [Experimentando o OpenCode](https://danielloureno1.substack.com/p/experimentando-o-opencode)
>
> Todas as minhas experiências com IA até ano passado foram de pedir código avulso no ChatGPT. O primeiro CLI que usei foi o do Gemini 2.5-Pro e 2.5-Flash. Usei em projetos pequenos e me ajudou bastante, mas não era nada impressionante. Na prática, só o Pro era útil e tinha um limite gratuito que não durava nada. Com o tempo parei de usar por que era mais…

Média 3,5 — me deu um 4 em *Estrutura e Progressão* com os seguintes comentários:

> A sequência de versões do bot (v0.1 → v0.4 → refactor quebrado) dá um arco claro com ponto de virada: “Resultado: 0% de vitórias, quebrou totalmente, de forma silenciosa.”

> Comentário final: Relato metódico e com arco narrativo bem amarrado, do encantamento inicial à quebra do bot e às lições finais; a voz pessoal dá caráter ao texto, que oscila apenas em economia e em pequenos deslizes formais.

## Avaliação final

![](image-02.png)

[Daniel Lourenço (184KB ∙ PDF file)](attachment-01.pdf)

---

A partir daqui seguirei em ordem alfabética de acordo com o arroba de cada um, não o nome. Otávio ficará em último porque mudou o arroba dele.

---

### Hasty

Hasty abre a competição com os dois pés na porta, literalmente. Seu texto *Da impossibilidade de restos ao beta* recebe duas notas máximas em *Estrutura e Progressão*, além de *Originalidade*, obtendo média 4.

> [Da impossibilidade de restos ao beta.](https://0hasty0.substack.com/p/da-impossibilidade-de-restos-ao-beta)

Trechos destacados pelo juiz:

> Por fim, conclui-se que o beta, enquanto beta, é incapaz de gerar aura devido à ofuscação sensível de sua Santidade pela exaltação da Santidade doutro; ou seja, não sobra nada para o beta. Entende-se, por isso, que o beta é o estado temporário após uma perda.

> Comentário final: Sátira escolástica executada com disciplina notável: o aparato acadêmico (epígrafe falsa, citações, objeções numeradas) é sustentado do início ao fim, e a definição final do beta como estado temporário fecha o arco com elegância.

---

> [Da necessidade do horário mundial da flatulência.](https://0hasty0.substack.com/p/da-necessidade-do-horario-mundial)

Com média 3, esse texto recebeu algumas poucas críticas em *Clareza de Prosa(2)* e *Execução técnica(2).* Trechos destacados:

> “Algo que me imiscuiu os pensamentos fora a dedicatória que algumas vezes se tem os horários.” “Da seleção do que aos horários. / Eis que abordarei meus motivos de criarmos isso”

> **Comentário Final:** A sátira pseudo-escolástica sustenta bem a farsa e as ideias são genuinamente engraçadas, mas o arcaísmo deliberado vezes o tropeça em construções que custam a leitura além do efeito cômico.

---

## Avaliação Final

![](image-03.png)

[Hasty (95.7KB ∙ PDF file)](attachment-02.pdf)

---

### 𝘼𝙜𝙚𝙣𝙩 𝘽𝙡𝙪𝙚𝙎𝙩𝙖𝙧

Um dos mais injustiçados de todo esse experimento. Recebeu algumas boas notas em *Originalidade* e *Controle de Voz*, mas foram ofuscadas por notas consistentemente ruins em *Execução Técnica* e *Clareza da Prosa*. Imagino que isso se deve ao fato dele escrever em sua segunda língua e não na sua materna.

> [Confessions ov an Accelerationist](https://agentbluestar.substack.com/p/confessions-ov-an-accelerationism)

> - *Clareza da Prosa(2):* “For I do not not not not not not want the Good ov ze sheep, my Lord!” - *Controle de Voz(4):* “The Prince ov nothingness calls at my heart, my Lord!” - *Estrutura e Progressão(3):* “Forgive me, my Lord! ... VICTORY OV ZE VVILL!” - *Densidade de Ideias(2):* “I want to taste their blood, my Lord!” - *Originalidade(4):* “Knell to my VVill!” - *Execução Técnica(2):* “Their grass mvst be alll be bvrned - he says, my Lord!”

> **Comentário:** Monólogo litúrgico com ortografia deliberadamente distorcida e persona consistente de confessionário aceleracionista; a cadência é firme, mas a repetição e o esforço de decodificação diluem a densidade e a clareza.

Na minha opinião aspectos como *Densidade de Ideias*, *Controle de Voz* e *Originalidade* deveriam todos receber nota máxima, mas o que está sendo medido não é qualidade de arte, mas escrita e principalmente prosa no sentido mais comum e rotineiro. 2,83 é a média final desse texto.

---

> [Post-Post-History](https://agentbluestar.substack.com/p/post-post-history)

Texto onde meu ponto é demonstrado com mais força. A média é a mesma do anterior. Duras críticas gramaticais e elogios a forma como o assunto é abordado. Trechos destacados:

> “briging a return to a type of war that was uncommon for the modern western experience of war emmerging from this breakdown of the power’s monopoly...” — frase-rio final que exige releitura; também “The grand narratives of the 20th century.” fica suspenso como fragmento. “Fascism? Collapsed. Communism? Collapsed. Liberalism? In visible decline.” — tom declamatório e apostrófico mantido de ponta a ponta. “agressive at its ride”, “briging”, “emmerging”, “by Julios Evola” — múltiplos erros de grafia e pontuação perceptíveis ao longo do texto. **Comentário:** Ensaio de tese assertivo e com voz marcada, mas o polimento técnico e o controle da frase longa ficam aquém da ambição argumentativa.

---

## Avaliação Final

![](image-04.png)

[Agentbluestar (118KB ∙ PDF file)](attachment-03.pdf)

---

### Cæser

Uma das maiores surpresas dessa análise. O único escritor com média final igual a 4. Como um resultado atípico, preciso tomar mais cuidado na análise. Vou começar pelos textos que li.

---

> [O Imperador Tradutor e a Aporia do Logos: 1889 como Decomposição da Vontade Imperial](https://caeserdabolha.substack.com/p/o-imperador-tradutor-e-a-aporia-do)

Média do texto é 4,5 com nenhuma nota abaixo de 4. Trechos destacados:

> “Governar é escolher quem deve ser esmagado. Pedro II preferiu estudar tupi.” “O positivismo é a religião do homem medíocre que precisa de uma planilha para saber se está vivo.” “O imperador *convertreu-se* num espectador passivo da história” — sem erros perceptíveis, pontuação e sintaxe impecáveis.

Atenção para a linha anterior: “*convertreu-se*” é um erro que não existe no texto à data em que escrevo isso, 22 de agosto. Isso aponta para duas possibilidades:

- Isso foi corrigido pelo autor, editando o post entre o período onde coletei os dados e o momento atual onde os estou compilando.
- O modelo cometeu um erro ao transcrever/copiar a citação para o relatório.

Esta última possibilidade é bem interessante, considerando que a *Execução Técnica* de Cæser recebeu nota máxima. Seria ele mais preciso em sua ortografia do que uma máquina? Não quero nem pensar em quantas revisões esse texto recebeu antes da publicação.

Não posso eliminar também a possibilidade do uso de IA na escrita do texto. Isso bate com o viés que percebi ao analisar textos certamente escritos por IA, mas não posso acusar ninguém de forma leviana. Além disso, mesmo que haja uso, não é prejuízo nenhum a leitura ou a qualidade do texto.

---

> [Brutalismo Tropical: A Laje Não Pede Opinião](https://caeserdabolha.substack.com/p/brutalismo-tropical-a-laje-nao-pede)

Média 4,67 e quatro notas máximas de seis. Trechos destacados:

> Cada decisão formal é também uma decisão estrutural: a espessura da laje corresponde à carga que ela carrega, a posição do pilar corresponde ao fluxo de forças no sistema, a textura da fachada corresponde ao processo de concretagem sem revestimento posterior. Nada existe para parecer; tudo existe para ser. A Igreja inventou o conforto espiritual através da farsa arquitetônica, ensinando o Ocidente a odiar o peso da realidade.

---

## Avaliação Final

![](image-05.png)

[Cæser (105KB ∙ PDF file)](attachment-04.pdf)

---

## Dankk

Sem dúvidas um dos mais penalizados pelo viés da máquina, provavelmente devido ao tema e o uso de argumentos dos Pais da Igreja, que na visão da máquina são batidos e repetitivos.

---

> [O Sola Scriptura é irônico.](https://dankk.substack.com/p/o-sola-scriptura-e-ironico)

O texto mais bem avaliado tem média de todos os quesitos igual à 2,87. Recebendo notas 2 em *Originalidade*, 2 em *Execução Técnica* e 4 em *Estrutura e Progressão*. Trechos destacados:

> “Como uma maquina em uma esteira de produção, apesar do objetivo dela ser produzir algo, sozinha ela não completaria tal objetivo” Texto claro em sua linha argumentativa, com voz pessoal evidente e bons momentos de humor, mas com bastante área de preenchimento, passagens recorrentes no debate católico-protestante e problemas técnicos que vão de acentuação a má pontuação.

---

## Avaliação Final

![](image-06.png)

[Dankk (85.5KB ∙ PDF file)](attachment-05.pdf)

---

### dasein

Um caso atípico. Ele não escreve artigos próprios até onde sei, mas publica traduções de artigos estrangeiros. Ainda assim achei válido incluí-lo dado que ainda existe uma substância considerável das suas habilidades de escrita em como decide concretizar as ideias que recebeu do autor original.

O padrão que percebi é de notas consistentemente altas em quesito *Originalidade* e em *Controle de Voz*. Este último criado pelo autor e mantido/transmitido com louvor pelo tradutor.

---

> [DAS DIREITAS](https://daseintropical.substack.com/p/das-direitas)

Texto com média 4. Uma nota 3 em *Clareza da Prosa* e 5 em *Originalidade*.

> *Clareza da Prosa(3):* O texto é geralmente legível, mas tropeços como ‘sempre viveu da misericórdia de seus inimigos e hoje é semanalmente sodomizado por Alexandre de Moraes’ (metáfora ambígua) e as longas digressões com parênteses empilhados (’diga-se de passagem, o governador era o atual vice-presidente e o prefeito o atual ministro da Fazenda’) exigem pausas para decifrar. *Execução Técnica(4):* Prosa praticamente limpa, com raros deslizes (’Nacionautismo’, ‘interjunção’, ‘Era uma vez’ em contexto informal) e uso consistente de itálico para estrangeirismos, indicando revisão. **Comentário:** Ensaio de fôlego com diagnóstico histórico claro e uma voz cínico-apocalíptica própria, ainda que as metáforas sanguinolentas finais e certas digressões parêntéticas sobrecarreguem o tom.

---

## Avaliação Final

![](image-07.png)

[Dasein (189KB ∙ PDF file)](attachment-06.pdf)

---

### Davi Minecrafts

Conheci o Davi pelos podcasts e depois li alguns artigos seus sobre Lei Felca e Polícia Federal investigando Vorcaro. Seu [último texto](https://daviminecrafts.substack.com/p/uma-resenha-sobre-crime-e-castigo) aqui no Substack me motivou a escrever minha própria resenha sobre o livro que também estava lendo.

---

> [Alguns Problemas da Lei Felca](https://daviminecrafts.substack.com/p/alguns-problemas-da-lei-felca)

> *Densidade de Ideias(3):* “Nós somos o produto deles, sua tecnologia é apenas a vitrine que escolhemos ser expostos.” *Originalidade(3):* “somado ao fato do capitão frouxo ter sido condenado por broxar um golpe contra a ordem constitucional e o Estado Democrático” **Comentário:** Ensaio polemista de tom casual e direto, com voz reconhecível e bons ganchos, mas com erros gramaticais frequentes e passagens que travam a leitura; o conteúdo é razoavelmente convencional no repertório, embora com recortes pessoais.

---

> [Uma Resenha Sobre Crime e Castigo](https://daviminecrafts.substack.com/p/uma-resenha-sobre-crime-e-castigo)

> “Sempre alimentei um certo preconceito e indiferença em relação à profissão mais antiga do mundo, perdendo apenas para político, mas com Sônia foi diferente.” **Comentário:** Resenha sincera e pessoal que mescla resumo do enredo com reflexão sobre sofrimento e fé, mas é limitada por erros mecânicos recorrentes e por uma leitura bastante convencional da obra.

Novamente o juiz é implacável com erros ortográficos. Apesar disso é um dos meus textos favoritos do Davi e que me motivou a perseverar na leitura.

---

## Avaliação Final

![](image-08.png)

[Davi Minecrafts (130KB ∙ PDF file)](attachment-07.pdf)

---

### Danilo Henrique

A voz da razão aqui na Bolha, sempre dando conselhos ou discutindo com alguém. Admito que não li quase nada além das suas notas no feed do Substack.

Obtém notas consistentemente altas em *Estrutura e Progressão* e *Controle de Voz*.

---

> [Você não vai transformar o mundo.](https://deaga.substack.com/p/voce-nao-vai-transformar-o-mundo)

> *Densidade de Ideias(4):* “Um tronco de madeira já contém a potência de ser mesa ou cadeira, é a aplicação de certos meios que a conduzirão a um estágio já possível no próprio tronco.” *Originalidade(3):* “Não somos especiais porque podemos transformar, o valor humano está em tirar da inércia a melhor possibilidade de nós mesmos e das coisas ao nosso redor.” **Comentário:** Ensaio filosófico de viés metafísico clássico que constrói um arco argumentativo coeso, do diagnóstico da cosmovisão do movimento à conclusão sobre limites da transformação. A clareza e o polimento sofrem com frases longas sem pontuação de fechamento e repetição do paradoxo central, ainda que a voz permaneça firme.

---

> [Ensaio Sobre A Ordem Natural - Artigo 1](https://deaga.substack.com/p/ensaio-sobre-a-ordem-natural-artigo)

> *Densidade de Ideias(3):* “A ordenação do melhor ao pior, estabelece o melhor, o primeiro em um critério” *Originalidade(4):* “que é a regra natural que estabelece o melhor, o primeiro, o Príor de sua classe”

---

## Avaliação Final

![](image-09.png)

[Danilo Henrique (129KB ∙ PDF file)](attachment-08.pdf)

---

### Eduardo Pessoa

Dispensa apresentações. Esse caso é um tanto curioso visto que ele somente escreveu um único texto aqui no Substack. E em inglês, ainda por cima.

> [Why Do Anything Other Than Accumulate Money?](https://eduardopessoa.substack.com/p/why-do-anything-besides-accumulate)

> *Controle de Voz(4):* “Pffft, a traditional Indian or Indo-European would laugh at how unambitious you are. You had three choices and you actually chose the lowest one. *Pathetic*.” *Originalidade(4):* “these are the three I would choose: you do an activity for money, for power or for God.” Execução Técnica(2): “objetcs ... in a countries ... at the humanities student in an university” **Comentário:** Ensaio argumentativo coerente e provocativo, com tese clara e arco bem construído, mas a voz opinativa de propósito declarado esbarra em erros técnicos frequentes (ortografia, concordância) que minam o polimento final.

---

## Avaliação Final

![](image-10.png)

[Eduardo Pessoa (56.5KB ∙ PDF file)](attachment-09.pdf)

---

### GTF

Um dos idealizadores do [Jornal da Bolha](https://jornaldabolha.substack.com/) junto com @Pavlo / Pavlovich, fez um excelente trabalho unindo a antes esparsa rede de pessoas associadas sabe-se lá pelo quê aqui na plataforma.

Tem uma das escritas mais fortes e estruturadas de todas as avaliadas até agora, pecando somente em *Execução Técnica* e *Clareza de Prosa*, às vezes. É impressionante como mantém essa atenção aos detalhes e às ideias considerando a quantidade e a frequência das publicações.

---

> [A Fênix Spengleriana [III]](https://gtf1331606.substack.com/p/a-fenix-spengleriana-iii)

Média igual à 4, nota máxima em Originalidade, 3 em Execução Técnica e 4 em todo o resto. Trechos destacados:

> “O homem constrói metrópoles gigantescas e algoritmos impecáveis com o corpo que lhe resta, mas a alma que os justificava já expirou.” “O esforço titânico para hiper-regulamentar a vida, geometrizar as cidades e substituir o mistério da existência pela eficácia das máquinas esgota a seiva do organismo e acelera a mecanização do Corpo.” **Comentário:** Ensaio de fôlego raro, que sustenta um arcabouço conceitual próprio (Máquina Zumbi, Uber-Fellah, Fênix Atlântica) com vigor e coerência do prólogo à conclusão. O preço dessa ambição é uma densidade que em alguns trechos exige releitura e um polimento técnico irregular (acentos, concordâncias e um erro de regência).

---

## Avaliação Final

![](image-11.png)

[Gtf (192KB ∙ PDF file)](attachment-10.pdf)

---

### Armando Leal

Assim como GTF, tem uma quantidade e variedade de textos enorme. Todos muito bem revisados e encadeados. Em casos como esse é difícil até escolher um texto como amostra.

---

## Avaliação Final

![](image-12.png)

[Armandoleal (196KB ∙ PDF file)](attachment-11.pdf)

---

### Conclusão

Meu plano era postar a versão final no meio de agosto. Já é 1 de setembro e não consegui catalogar nem metade dos resultados gerados. Era um projeto ambicioso demais para mim.

Além disso, conforme o tempo passa, novos textos vão sendo publicados, todos evoluem e o sentido de analisar os textos antigos se perde. Por isso também não farei uma segunda parte, que demoraria tanto quanto a primeira para ser produzida. O pouco que posso fazer é disponibilizar os resultados de todos sem os meus comentários caso seja do interesse de alguém.

---

![](image-13.png)

[Historiaeliberdade (203KB ∙ PDF file)](attachment-12.pdf)

---

![](image-14.png)

[Insider (79.1KB ∙ PDF file)](attachment-13.pdf)

---

![](image-15.png)

[Jozef (98.1KB ∙ PDF file)](attachment-14.pdf)

---

![](image-16.png)

[Kotal (198KB ∙ PDF file)](attachment-15.pdf)

---

![](image-17.png)

[Sawen (161KB ∙ PDF file)](attachment-16.pdf)

---

![](image-18.png)

[Lemeiro (84.9KB ∙ PDF file)](attachment-17.pdf)

---

![](image-19.png)

[Patriota Catarinense (80.3KB ∙ PDF file)](attachment-18.pdf)

---

![](image-20.png)

[Luizmusil (81.7KB ∙ PDF file)](attachment-19.pdf)

---

![](image-21.png)

[Noir (166KB ∙ PDF file)](attachment-20.pdf)

---

![](image-22.png)

[Otávio (133KB ∙ PDF file)](attachment-21.pdf)

---

![](image-23.png)

[Pablogibrin (200KB ∙ PDF file)](attachment-22.pdf)

---

![](image-24.png)

[Malta (126KB ∙ PDF file)](attachment-23.pdf)

---

![](image-25.png)

[Pato (55KB ∙ PDF file)](attachment-24.pdf)

---

![](image-26.png)

[Pavlo (105KB ∙ PDF file)](attachment-25.pdf)

---

![](image-27.png)

[Rafux (111KB ∙ PDF file)](attachment-26.pdf)

---

![](image-28.png)

[Rycardo (91.1KB ∙ PDF file)](attachment-27.pdf)

---

![](image-29.png)

[Sala De Guerra (196KB ∙ PDF file)](attachment-28.pdf)

---

![](image-30.png)

[Sir Richard (188KB ∙ PDF file)](attachment-29.pdf)

---

![](image-31.png)

[Suares Lovelace (94KB ∙ PDF file)](attachment-30.pdf)

---

![](image-32.png)

[Camarada Tojaro (132KB ∙ PDF file)](attachment-31.pdf)

---

![](image-33.png)

[Waru (178KB ∙ PDF file)](attachment-32.pdf)

---

## Ranking

![](image-34.png)
