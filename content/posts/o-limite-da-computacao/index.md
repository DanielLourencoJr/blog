---
title: 'O Limite da Computação'
date: '2025-12-14T11:01:00-03:00'
draft: false
description: 'O desenvolvimento tecnológico não é perpétuo sem uma revolução de arquitetura.'
tags:
  - computação
  - hardware
  - física
---

Pensei em escrever esse texto por causa da explosão das LLMs (sei que você não aguenta mais falar disso, mas tenha calma) e por uma reflexão aleatória sobre o boom populacional da humanidade nos últimos séculos devido à urbanização, indústria e revolução verde.

O pânico em torno da IA nos últimos 3-4 anos se deve, claro, ao grande salto tecnológico, onde um modelo teórico recebeu uma atualização de performance que o permitiu ser executado de forma prática e em tempo real. Porém, esse pânico se deve, também, a uma incompreensão sobre como computadores e tecnologia em geral evoluem.

Tudo isso faz parte de uma argumentação maior que ainda não terminei, mas o objetivo agora é de expor da maneira mais didática possível como um computador funciona e construir um experimento mental que ajude a entender os limites da computação da forma como entendemos hoje.

Um computador é uma calculadora por definição. Tudo que ele é capaz de fazer é executar comandos que envolvem a alteração de números em sua memória, que chamamos de bits, por serem a menor unidade de informação que podemos manipular.

Desde o ENIAC até o meu computador ao lado da minha mesa houve vários avanços físicos, químicos e técnicos na forma como computadores são construídos, mas a sua arquitetura geral continua mais ou menos da mesma forma. O que ocorreu foram melhorias de performance para ser mais rápido e eficiente, ou seja, usar menos energia e menos tempo para fazer o ***mesmo*** processamento.

Você provavelmente já ouviu falar do quão pequenos são os transistores dos processadores de hoje em dia e de como estamos próximos do limite físico de quantos deles podemos colocar no mesmo espaço. Apesar disso, ainda há muito espaço para melhora, mas essa melhora de eficiência não levará a grandes saltos como o visto pelo campo das IAs.

Para dizer a verdade, os computadores modernos ainda estão longe dos limites impostos pelas leis da física. Os limites atuais se devem puramente a limites nas técnicas humanas para a construção deles.

Vamos imaginar um computador teórico que use toda sua massa para fazer computações. Meu objetivo é te mostrar que mesmo o melhor computador que nunca será fabricado na prática não resolveria todos os problemas da humanidade, longe disso. Sem uma revolução na arquitetura atual, mais processamento e mais velocidade são pouco impactantes.

O [Limite de Bremermann](https://en.wikipedia.org/wiki/Bremermann's_limit) diz que um sistema computacional fechado, ou seja, uma caixa preta que não depende de mais nada além de si mesmo para computar, não pode ultrapassar a quantidade de energia que ele tem armazenado em sua massa dividido pela quantidade mínima de energia necessária para realizar uma única computação. A energia do sistema é dada por E = mc² (grande Einstein).

Fazendo todas as contas chegamos ao número máximo de 1.3563925 × 10⁵⁰ operações por segundo por quilograma. Da mesma ordem de grandeza do número de átomos da Terra — muito maior que o número de grãos de areia ou estrelas visíveis. Grande o suficiente para ter dificuldade em encontrar um exemplo temporal que humanos entendam.

Isso significa que esse sistema hipotético poderia contar os milissegundos que se passaram desde o Big Bang antes que você pudesse decidir assinar, ou não, minha newsletter.

Agora que temos o computador mais rápido permitido pelas leis da física na arquitetura atual podemos ver o quão rápido ele é em coisas mais complicadas do que contar.

## Força Bruta

No exemplo anterior a tarefa era somar 1 num número na memória do computador, mas para as atividades que usamos computadores são necessárias operações mais complexas.[^1]

Numa pesquisa rápida vi que uma inferência do GPT-4 requer 560 trilhões de operações com ponto flutuante (números fracionários). O nosso computador hipotético conseguiria computar mensagens das mais longas instantaneamente. Pode levar um tempo diferente de 0 (na ordem de 10⁻³⁵ segundos), mas menor que a precisão de qualquer relógio que a humanidade tenha inventado até agora.

Partindo para tarefas mais difíceis temos criptografia. Fácil de usar, difícil de quebrar com força bruta. Absolutamente todos os algoritmos de criptografia têm sua confiança baseada nessa dificuldade. Algoritmos como:

- AES-128
- ECC-256
- RSA-2048 (demoraria um pouco)

Seriam quebrados em frações de segundos. Porque, na prática, um segundo é suficiente para esgotar o espaço efetivo de busca desses algoritmos. Já algoritmos como:

- AES-256
- SHA-256
- bcrypt (dependendo da quantidade de caracteres)

Estão seguros. Levando 10²⁷ segundos para quebrar o SHA-256, por exemplo[^2]. Para quebrar essas criptografias nosso computador precisaria crescer até escalas continentais se quiséssemos terminar no tempo de vida humano.

É nesse momento que começamos a sentir os limites da força bruta e da velocidade do melhor computador possível no nosso universo. Nem mesmo ele é o bastante para lidar com certos problemas.

Chegamos nos problemas não determinísticos de tempo polinomial (NP), que incluem classes de problemas cuja melhor solução conhecida cresce de forma exponencial. Aqui entram coisas como o [Caixeiro Viajante](https://en.wikipedia.org/wiki/Travelling_salesman_problem).

Mas nem só de hardware vive a humanidade, não é mesmo?

Agora que vimos os limites da força bruta e da velocidade da computação, vamos aos limites da arquitetura. No fim das contas, tecnologia é técnica. Além das técnicas de construção de computadores, a humanidade também desenvolveu técnicas para acelerar a computação em certas situações para transformar problemas exponenciais em problemas resolvíveis em tempo constante, e isso é a chave para entendermos que o futuro da tecnologia está em uma revolução na arquitetura atual dos computadores.

## Busca Binária

O exemplo mais fresco em minha memória é a busca em bases de dados. Técnicas como busca binária cortam o tempo de encontrar uma informação na memória, causando uma economia proporcional à quantidade de informações.

A maior utilidade da computação no dia a dia é o armazenamento e processamento desses dados para fins comerciais. Espero que entenda que atividades como atualizar, consultar e cadastrar novos dados requerem manipular a memória do computador. E como o volume de dados só cresce, precisamos fazer isso o mais rápido possível.

Exemplo: Tenho uma lista com as informações de todos os meus clientes ordenada pelo valor da renda que me trazem mensalmente. Consigo rapidamente, por meio de uma busca binária, achar um cliente específico entre milhões buscando por esse número que chamamos de chave de busca. Eu consulto o meio da minha lista e vejo que o número no meio é maior que a minha chave, então procuro somente na primeira metade da lista. Repito o processo para a lista menor que obtive.

Traduzindo: Em uma lista com N elementos podemos encontrar um elemento desejado sem ter que comparar com cada elemento individualmente mas com log N elementos, ao custo de manter a lista ordenada de forma crescente (custo típico O(N log N)).

Caso tenha alguma familiaridade com logaritmos, você sabe que quanto maior a lista, maior será a economia. Porém existe um limite econômico para quanta memória temos para armazenamento. E a memória de trabalho (a famosa RAM) é ainda mais escassa. Raramente é possível em bases de dados grandes colocar toda a lista na RAM para usar a busca binária.

Então chegamos em Árvores B para achar com velocidade os dados que precisamos em equipamentos mais lentos como HDs e SSDs. O gargalo aqui não é a comparação, mas o número de acessos ao armazenamento persistente.

Vale notar que, nesse caso, estamos usando uma técnica para burlar limites impostos pela própria arquitetura dos computadores, não limites teóricos. Ou seja, com RAM infinita busca binária sempre seria melhor, mas como ela é menor que o armazenamento persistente, precisamos de outras técnicas para expandir nossos limites práticos.

## Conclusão

Eu poderia continuar esse texto falando sobre como criptografias funcionam e porque elas são resistentes à força bruta, mas não é algo que eu tenha domínio ou possa escrever sobre com uma tarde de pesquisa.

Eu poderia continuar esse texto explicando o limite físico e teórico de armazenamento em um espaço com massa finita, e aplicar ao computador hipotético para mostrar que para uma quantidade de dados próxima da que a humanidade lida hoje em dia, mesmo o nosso computador perfeito teria que lidar com o deslocamento dos dados na memória interna e mostrar os gargalos insuperáveis, independentes da arquitetura.

Porém esse texto tem que sair antes que eu perca meu interesse nesse assunto. E pesquisar tudo isso e manter o texto coeso demoraria algumas semanas.

Para alguns esse texto pode ter ficado técnico demais. Para outros pode ter ficado vago demais. No mais espero que isso possa abrir espaço para discussão sobre o que compete à computação e que ela é só mais uma tecnologia, não a cura para todos os nossos problemas.

[^1]: A operação mais simples para um computador não é realmente somar, mas mudar um bit de 0 para 1 ou vice-versa. Omiti isso do texto principal pois o objetivo dos cálculos não é ser preciso, mas dar noção da ordem de grandeza que estamos lidando.

[^2]: Veja esse vídeo mostrando o quão difícil é quebrar o SHA-256. [LINK](https://youtu.be/S9JGmA5_unY?si=T1oGRZ-rLCGIIbyM)
