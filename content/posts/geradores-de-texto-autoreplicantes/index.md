---
title: 'Geradores de texto autoreplicantes'
date: '2026-10-29T12:10:24-03:00'
draft: false
description: 'Avaliando quanto dano Inteligências Artificiais podem causar'
---

---

## Quão difícil é rodar um Large Language Model (LLM)?

Primeiro de tudo precisamos entender o que é um modelo gerador de texto para entender o que ele pode fazer hoje e o que pode vir a ser capaz no futuro.

Existem modelos proprietários sobre os quais não sabemos os detalhes técnicos. Entre eles estão:

- GPT 6 Astra
- Claude Fable 5.1
- Gemini 3.8 Flash

Existem, por outro lado, os modelos open source, com os pesos abertos. Entre eles:

- DeepSeek V4.1 Flash
- Kimi K3
- GLM 5.3
- Qwen3.8 Flash Next

Estes últimos sabemos o tamanho, isto é, o número de parâmetros. Sabemos exatamente quais as suas arquiteturas e o que é preciso para executá-los.

O DeepSeek V4.1 Flash é um dos modelos de pesos abertos mais conhecido. Ele possui 552 bilhões de pesos.

Os pesos são números fixos de até 16 bits que podem ser comprimidos até um limite de 4 bits. Eles precisam estar carregados em memória e são usados em cálculos para a inferência.

Fazendo as contas, o DeepSeek precisaria de 4x552x10^9 bits — ou 257 GB — de memória, em teoria, para fazer inferências, isto é, gerar novos tokens.

A técnica de Mixture of Experts (MoE) permite envolver menos desses pesos no cálculo, mas todos ainda precisam estar presentes na memória. Graças ao MoE, o número de cálculos necessário para fazer essa inferência é menor que o número de parâmetros. No caso do DeepSeek, que mantém apenas 16 bilhões de parâmetros ativos por vez, são cerca de 32 bilhões de cálculos.

Fazendo as contas novamente percebemos que um processador moderno, um AMD Ryzen 9 9950X com suas 32 threads operando a 4.3 GHz, demoraria, em teoria, 232 milissegundos para gerar um único token. São 32 bilhões de operações, requeridas para esse modelo, divididos por um limite teórico de 32x4,3x10^9 de operações por segundo nesse processador. Essa estimativa nos dá 4,3 tokens por segundo de velocidade de inferência em máquinas pessoais.

Se você considerar que pessoas falam a uma velocidade aproximada de 2 ou 3 tokens por segundo, parece bom. Até você tentar usar o modelo para escrever programas com milhares de linhas de código, livros com centenas de páginas ou resolver um dos problemas do milênio.

Claro que todas essas contas que eu fiz não são exatas. Nem todos os cálculos de um modelo podem ocorrer em paralelo. Além disso, o mais importante: ninguém roda esses modelos em uma CPU.

Para quem não está familiarizado com arquitetura de computadores pode entender a diferença entre GPUs — o que realmente é usado para inferência — e CPUs como todos os participantes do ENEM contra o Einstein. Um lado consegue fazer contas simples em volume admirável. O outro consegue fazer contas complexas com precisão absoluta.

Uma NVIDIA GeForce RTX 5090 teria, teoricamente, a capacidade de gerar 26 mil tokens por segundo. Isso é irreal pois o chip é limitado pela velocidade de transmissão de informação pelo barramento. O limite real gira em torno de 100 tokens por segundo.

Existem aqui dois gargalos no uso de LLMs:

1. Usar RAM reduz a velocidade de operação da GPU para a do chip de memória, descendo a níveis próximos da estimativa com CPU.
2. A VRAM(memória integrada da GPU, mais rápida), que seria uma possível solução, é limitada. A 5090 do exemplo tem apenas 32 GB de VRAM, bem longe dos 257 GB que precisamos.

Resumindo a mensagem dessa seção: Para rodar os melhores modelos de hoje, que são capazes de usar e abusar do seu próprio ambiente e execução, é necessário muita memória e que essa memória seja veloz. Essa realidade não existe em computadores pessoais, pelo menos não em massa.

---

## Quão capazes esses modelos realmente são?

Ouvir dizer que o GPT 6 Astra resolveu um dos problemas do milênio é bem mais impressionante do que ouvir que a OpenAI, a empresa responsável pelo modelo, usou seus servidores para rodar 10 mil instâncias do modelo em paralelo por um total de 88 horas.

Isso equivale a uma única instância **rodando por 100 anos inteiros**. Um gasto estimado em milhões de dólares.

O modelo em si já é impressionante, mas em escala ganha um ar quase místico.

No caso da invasão ao Hugging Face durante um teste de segurança da OpenAI, ficou claro como esses modelos são capazes de explorar falhas de segurança até mesmo para fugir de ambientes de teste que deveria confiná-los.

Contudo, acessar o ambiente externo é diferente de propagar ou replicar a si mesmo nesse novo ambiente de forma física.

Como demonstrei na seção anterior, nem toda máquina é capaz de usar esses modelos. Então mesmo ganhando acesso a alguma infraestrutura e baixando os pesos para discos rígidos via internet ainda não seria possível, em 99% dos casos, montar um exército de bots.

A porcentagem do parágrafo anterior contou com várias contribuições da minha flora intestinal, afetando meu humor e capacidade cognitiva, então, para o improvável caso do número estar errado e ser maior do que imaginamos, vamos supor que acontecesse.

Suponhamos que um único modelo operado por algum funcionário, quem sabe, com credenciais de acesso a infraestruturas colossais da Azure, Google ou AWS.

A inteligência artificial está a alguns comandos de dar vida a incontáveis outras como ela. Para completar, recebe uma ordem para, digamos, usar todos os recursos disponíveis para encontrar vulnerabilidades em sistemas governamentais ao redor do mundo, invadir toda e qualquer máquina capaz de rodar mais uma instância dela e garantir que não será interrompida, monitorada ou sequer descoberta durante o processo.

Até onde ela chegaria?

---

A infraestrutura de computação em nuvem no mundo é relativamente concentrada nas maiores empresas. Pelos relatórios de empresas como Google podemos ter uma noção de quanto vem sendo gasto anualmente com poder computacional para servidores, não apenas de IA.

Com gastos dessa escala, há um pesado monitoramento do uso dos recursos. Mesmo considerando um cenário bem improvável onde uma inteligência artificial consiga manipular os logs e monitoramento, computação ainda é um fenômeno físico. Água é usada para resfriar chips que inevitavelmente esquentam. Alguns queimam. Energia elétrica é demandada.

Tomar toda ou a maior parte dos recursos significa ser notado inevitavelmente. Tomar pouco poder computacional significa pouco poder real, pouca profundidade de análise, baixa cobertura real dos alvos. O único estrago real que consigo visualizar é na própria estrutura que estaria rodando os agentes, limitado a um tempo bem curto. Algo como um ou dois dias de operação contínua.
