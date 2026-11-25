---
title: 'A bolha em 14 perfis'
date: '2026-11-17T13:37:35-03:00'
draft: false
description: 'Baixei 1.083 textos de 44 autores, contei o que dava para contar e pedi a um modelo que lesse o resto.'
---

Este texto começou como desculpa. No fundo eu queria praticar tratamento de dados e visualização de estatísticas, e a análise da bolha deu o corpus: grande o suficiente para valer o exercício, pequeno o suficiente para caber num projeto pessoal.

O objetivo não é ser sério nem científico. É ver o trabalho de todo mundo junto, do mesmo jeito que o Jornal da Bolha faz. Se servir para movimentar a comunidade, já valeu de algo.

Na primeira edição o foco era escrita: clareza, voz, estrutura, densidade. O foco agora é mais geral. Sete dimensões — repertório, rigor, originalidade, didática, humor, curiosidade e espírito de debate —, uma nota de 1 a 5 em cada, mais um arquétipo e um papel na bolha. 14 dos 44 autores previstos estão prontos.

Os outros 30 ficariam para uma próxima parte com os mesmos critérios, mas não haverá outra parte. Demorei demais polindo as imagens com estatísticas e acabei desanimando antes de chegar na análise da *IA* propriamente dita.

## Como isso foi feito

Três números vêm de contagem direta, sem julgamento: fôlego (mediana de palavras por texto), citações recebidas dentro da bolha (quote-notes de outros autores, sem auto-citação) e comentários recebidos.

O resto não é contável. "Repertório" e "rigor" não são propriedades que um script extrai de um texto. Montei uma rúbrica com sete dimensões e pedi ao *DeepSeek V4.1 Flash* uma nota de 1 a 5 em cada uma, mais um arquétipo, um papel na bolha e os pontos cegos. Ele lê o corpus completo do autor, não uma amostra.

Cada perfil aparece com três imagens: o pôster, com as notas e a leitura do modelo; um trecho literal do texto; e o cartão com as contagens que não dependem de julgamento, comparadas ao maior valor da bolha.

As citações dos cartões são literais e foram conferidas contra o texto original. Cada autor foi analisado separadamente.

Faria uma leitura conjunta — comparando os perfis entre si — quando todos estivessem prontos, porque a amostra é pequena demais, mas fica pra próxima.

Duas ressalvas valem para tudo abaixo. O juiz é um modelo de linguagem, e carrega o gosto de um: valoriza ensaio e precisão no lugar de estilo e esforço, evitando notas extremas. E a nota não é determinística: duas rodadas dão resultados diferentes nas margens. Por isso, quando o sinal é fraco, o campo fica vazio em vez de receber um 3 morno. Seis das 98 casas da tabela estão vazias por isso.

## O mapa

![Mapa de calor com sete dimensões para 14 autores](image-01.png)

*Sete dimensões, 14 autores. Célula hachurada = sinal insuficiente. O mapa cresce conforme novos perfis entram.*

A primeira coisa que o mapa mostra é o quanto todo mundo se parece. As médias ficam entre 3,2 (didática) e 2,8 (humor), com rigor em 2,6 e espírito de debate no fundo, 2,2.

A segunda coisa é que essa semelhança não é política. A bolha tem tradicionalista católico, nacionalista, antifeminista, místico, fabulista em latim. Em conteúdo, ninguém confunde um com o outro. Em método, quase todos escrevem o mesmo texto: ensaio de opinião, fonte de segunda mão, adversário descrito por quem discorda dele. O número mais baixo da tabela é justamente o que mede isso.

Quase ninguém ali escreve para convencer quem pensa diferente. Escreve para quem já concorda. E é o vício mais uniforme do corpus.

O papel na bolha não é uma hierarquia. Ponte, especialista, generalista e dissonante dizem como o autor se posiciona em relação aos outros. A ordem dentro de cada grupo é a média geral, a mesma do mapa.

Vale lembrar que os textos passados para o modelo foram os lançados até 17 de outubro, enquanto as imagens contém dados referentes até a data de hoje, 17 de novembro.

## As pontes

Quatro autores ligam campos que não se falam. São os que mais ampliam o alcance da bolha e os que mais dependem de outra pessoa para ter o que dizer.

![Pôster de perfil de @pavlo436312](image-02.png)

![Pôster de perfil de @pavlo436312](image-03.png)

![Pôster de perfil de @pavlo436312](image-04.png)

*@pavlo436312 — filósofo-místico amador*

O @Pav monta sistemas metafísicos com Platão e gnosticismo e depois aplica tudo a anime e política brasileira. É a ponte mais improvável do grupo: filosofia medieval e Voegelin a serviço de crítica de anime. O problema é o método. Crise de identidade nacional e estado de bem-estar descansam em anedota e analogia, sem um único dado.

![Pôster de perfil de @gaiuscaesaraugustus](image-05.png)

![Pôster de perfil de @gaiuscaesaraugustus](image-06.png)

![Pôster de perfil de @gaiuscaesaraugustus](image-07.png)

*@gaiuscaesaraugustus — poeta lírico-confessional*

O @Gaius Caesar veio das exatas, aprendeu a pintar, constrói ferramentas de IA e escreve poesia. É a ponte mais explícita entre técnica e arte, e a mais honesta sobre ser amador por escolha. A contradição está aí: defende o processo amador e lamenta a técnica que não tem. Em quatro textos diferentes ele repete "não sei terminar".

![Pôster de perfil de @mts1622652](image-08.png)

![Pôster de perfil de @mts1622652](image-09.png)

![Pôster de perfil de @mts1622652](image-10.png)

*@mts1622652 — tradutor-curador*

O @PATRIOTA CATARINENSE não escreve: traduz. Circula entre teoria política sueca, escândalo cultural americano, sátira e manifesto partidário brasileiro. O valor está na escolha do que entra e na tradução, não na análise. O ponto cego é a divulgação: quase tudo é tradução, mas nem sempre isso fica claro, e as alegações mais escuras aparecem sem fonte primária.

![Pôster de perfil de @eduardopessoa](image-11.png)

![Pôster de perfil de @eduardopessoa](image-12.png)

![Pôster de perfil de @eduardopessoa](image-13.png)

*@eduardopessoa — ensaísta tradicionalista*

O @Eduardo Pessoa escreve em inglês e reduz tudo a três motivações: dinheiro, poder e Deus. É ensaísta de tese, não de arquivo. A origem indo-europeia comum e a suposta superioridade cultural da esquerda aparecem afirmadas, não documentadas. Tem um texto só no corpus, então não há trajetória para medir; o que existe é uma tese limpa e um adversário ausente.

## Os especialistas

Sete autores, cada um dentro de um quadro só. É onde estão os melhores textos e também os mais fechados.

![Pôster de perfil de @lemeiro](image-14.png)

![Pôster de perfil de @lemeiro](image-15.png)

![Pôster de perfil de @lemeiro](image-16.png)

*@lemeiro — parodista escolástico*

O @Lemeiro, O Larpador. é o caso mais divertido e o mais difícil de avaliar. Ele pega perguntas de cultura de meme — larp, furries, brainrot — e responde em disputatio escolástica inventada, com autoridades que não existem (Plagus, Vicka, Hyper, Zynius). Como forma, é impecável e engraçado. Como argumento, nada é verificável: a estrutura é a piada.

![Pôster de perfil de @celebrercuris789274](image-17.png)

![Pôster de perfil de @celebrercuris789274](image-18.png)

![Pôster de perfil de @celebrercuris789274](image-19.png)

*@celebrercuris789274 — ideólogo nacionalista-cultural*

O @Wyatt Willie 09 constrói programas: o Pindoramismo, uma direita negra, a história do Rio. Tem o repertório histórico mais funcional do grupo. MBL, integralismo, Frente Negra e UDN aparecem fazendo trabalho argumentativo, não enfeite. Só que programa não é política pública: cotas e desfavelização são afirmadas sem dado, e "esquerda woke" é um bloco, não um interlocutor.

![Pôster de perfil de @0hasty0](image-20.png)

![Pôster de perfil de @0hasty0](image-21.png)

![Pôster de perfil de @0hasty0](image-22.png)

*@0hasty0 — apologista católico tradicionalista*

O @D. F. Freire de Teresa. filtra economia, literatura e vida urbana pelo catolicismo tradicionalista de convertido, e construiu vocabulário próprio para isso: aura, beta, homem-anjo. Dentro do quadro funciona, com Lewis, Chesterton e Aristóteles fazendo trabalho real. Fora dele não há ponte. As citações escolásticas às vezes são inventadas ("Evola, Sobre o beta"), e o adversário nunca aparece: o marxismo é refutado com um esboço de manual.

![Pôster de perfil de @insider952828](image-23.png)

![Pôster de perfil de @insider952828](image-24.png)

![Pôster de perfil de @insider952828](image-25.png)

*@insider952828 — polemista antifeminista*

O @Insider lê toda a política por um eixo: o avanço da "longhouse". Todo texto termina em decadência civilizacional, e a emancipação feminina é a causa de tudo. O argumento recente ficou mais apertado, com imposto de natalidade, incidência tributária, Murray e Sowell. Mesmo assim, correlação continua virando causalidade, e a disfunção masculina é denunciada sem que sobre alguma responsabilidade aos homens.

![Pôster de perfil de @pato244464](image-26.png)

![Pôster de perfil de @pato244464](image-27.png)

![Pôster de perfil de @pato244464](image-28.png)

*@pato244464 — divulgador de história antiga*

O @Pato estreou com 4 mil palavras sobre Alexandre e a Macedônia. É o texto mais bem informado do corpus em nomes, datas e tática, e o mais fraco em tese: a comparação prometida entre Filipe e Alexandre nunca acontece, e a narrativa vira cronologia. Ele ainda preserva um erro conhecido (Átalo e Parmênio) "para não alterar os fatos", o que é uma saída elegante para não revisar.

![Pôster de perfil de @anajoquebede1](image-29.png)

![Pôster de perfil de @anajoquebede1](image-30.png)

![Pôster de perfil de @anajoquebede1](image-31.png)

*@anajoquebede1 — lírica confessional cristã*

A @anajoquebede1 escreve luto e fé. O melhor texto do corpus junta Hécuba, a Mater Dolorosa e a própria mãe, e a comparação é dela, não vem pronta de nenhum lugar. A força é a voz; a fraqueza é o método. As afirmações sobre detectores de IA ficam sem evidência, e objeções seculares não entram no texto: a fé argumenta dentro da fé.

![Pôster de perfil de @claraalexandre](image-32.png)

![Pôster de perfil de @claraalexandre](image-33.png)

![Pôster de perfil de @claraalexandre](image-34.png)

*@claraalexandre — serialista de horror cósmico*

A @Clara Miranda Alexandre publica um serial de terror cósmico semanal sobre uma cifra e uma criança albina. É a única ficção seriada do corpus, e o único caso de autor que também solta um ensaio patriótico no meio da série. O clima funciona; a repetição também aparece, com sangue por todos os orifícios, espelhos e a mesma cena. Com um só texto de não ficção, não dá para medir evolução.

## Os generalistas

Dois autores que escrevem sobre tudo e não respondem por nada em especial.

![Pôster de perfil de @pataquada](image-35.png)

![Pôster de perfil de @pataquada](image-36.png)

![Pôster de perfil de @pataquada](image-37.png)

*@pataquada — polemista antissistema*

O @Malta é o generalista clássico: sátira, história da aviação, política educacional, religião e verso, sem especialidade visível. A voz sarcástica segura o texto. As contradições também. Detona a escola pública e propõe escolas públicas seletivas, quer religião oficial e tolerância ao mesmo tempo, e fala dos pobres como "shudras".

![Pôster de perfil de @dankk](image-38.png)

![Pôster de perfil de @dankk](image-39.png)

![Pôster de perfil de @dankk](image-40.png)

*@dankk — apologista católico devocional*

O @Dankk defende doutrina católica versículo por versículo, em tom devocional, e aos poucos migrou para um tomismo didático. A circularidade é o método: "a verdade, e ela é Católica" resolve o que devia ser argumentado. Fora da apologética, política e literatura entram como ilustração, nunca como assunto.

## O dissonante

![Pôster de perfil de @pineus](image-41.png)

![Pôster de perfil de @pineus](image-42.png)

![Pôster de perfil de @pineus](image-43.png)

*@pineus — fabulista neolatino*

O @Heitor escreve ficção em latim, original e latinizada de jogos, e trata a língua morta como meio criativo, não como tema. Não há prosa argumentativa no corpus, então nenhuma posição dele é testada, e quase não há interlocução. É o autor mais isolado da bolha, e provavelmente o que mais se diverte escrevendo.

## O que a média esconde

As notas medem sete critérios que eu escolhi em quinze minutos sem qualquer cuidado ou reflexão. Um poeta pode sair mal em "rigor" e continuar sendo um bom poeta. O contrário também acontece.

Por fim, o juiz é um modelo lendo 1.083 textos. Ele erra, repete preferências e às vezes inventa uma justificativa plausível. Foi por isso que as citações passaram por conferência literal e que os campos de sinal fraco ficaram vazios. O perfil inteiro de cada autor, com notas, justificativas e pontos cegos, é o que está nas imagens. Se uma nota parecer errada, me diz qual e por quê: o material para discordar é o próprio texto do autor.

## Saída bruta do modelo

[0hasty0 (72.7KB ∙ PDF file)](attachment-01.pdf)

[Anajoquebede1 (73.8KB ∙ PDF file)](attachment-02.pdf)

[Celebrercuris789274 (68.9KB ∙ PDF file)](attachment-03.pdf)

[Claraalexandre (67.9KB ∙ PDF file)](attachment-04.pdf)

[Dankk (70.9KB ∙ PDF file)](attachment-05.pdf)

[Eduardopessoa (64.4KB ∙ PDF file)](attachment-06.pdf)

[Gaiuscaesaraugustus (73.4KB ∙ PDF file)](attachment-07.pdf)

[Insider952828 (68.9KB ∙ PDF file)](attachment-08.pdf)

[Lemeiro (69KB ∙ PDF file)](attachment-09.pdf)

[Mts1622652 (70.6KB ∙ PDF file)](attachment-10.pdf)

[Pataquada (74.3KB ∙ PDF file)](attachment-11.pdf)

[Pato244464 (63.7KB ∙ PDF file)](attachment-12.pdf)

[Pavlo436312 (73.6KB ∙ PDF file)](attachment-13.pdf)

[Pineus (67KB ∙ PDF file)](attachment-14.pdf)
