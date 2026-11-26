---
title: 'Entenda como 10 milhões de bitcoins não têm dono'
date: '2026-02-16T13:41:48-03:00'
draft: false
description: 'E como o SegWit causou isso'
tags:
  - bitcoin
  - blockchain
  - criptografia
  - protocolos
---

### Introdução

Se você roda um full node de Bitcoin e ao mesmo tempo mora numa caverna, no dia 24 de Agosto de 2017 você viu algo **sem precedentes** acontecendo na blockchain: transações sem endereço definido. Semelhantes àquelas feitas para scripts e smart contracts, mas um tipo específico que podia ser realizado por **literalmente qualquer pessoa**.

Sim, você leu corretamente: **Qualquer um poderia gastar aqueles bitcoins**. Mas claro que a história não é tão simples assim.

### SegWit

O que acontece é que à época estava sendo lançado uma alteração no Bitcoin: o *SegWit*.

*SegWit*, uma abreviação para **Segregated Witness**, é um conjunto de BIPs que reorganiza a estrutura dos blocos, separando as assinaturas (witness) das transações base. Isso permite que os dados de assinatura “contem menos” para o limite de 1 MB, aumentando a capacidade efetiva dos blocos.

Outra vantagem crucial foi **resolver a maleabilidade de transações** — permitindo que o ID da transação (txid) não pudesse mais ser alterado. Isso abriu caminho para protocolos de segunda camada como a **Lightning Network**. Pretendo escrever sobre isso no futuro.

### Soft Fork vs Hard Fork

Por se tratar de uma mudança nas regras de consenso, isso necessariamente gera um fork, uma divisão na rede entre **nós que adotam** a mudança e **nós que não adotam**.

*Hard Forks* são divisões brutas da rede, onde cada lado aceita e trabalha em cima de uma *blockchain* diferente.

*Soft Forks* são divisões onde as regras de um dos lados se torna **mais restritiva**, mas ainda dentro do que os dois lados aceitam. Assim, a *blockchain* não se divide.

### Retrocompatibilidade

O resultado disso é uma atualização retrocompatível. Todos os blocos aceitos pelos novos nós, são aceitos pelos antigos. Mas **nem todos** os blocos aceitos pelos nós antigos são aceitos pelos novos.

> Regras antigas: “X é válido se condições A, B e C”
>
> Soft fork: “X é válido se condições A, B, C e também D”

Como nós antigos continuam podendo usar a rede, *Soft Forks* são preferíveis.

Para ser um *soft fork* (compatível com versões anteriores), o *SegWit* precisava que:

- Nós antigos aceitassem blocos com transações *SegWit*
- Nós novos aplicassem regras extras de validação
- Não causasse fork da blockchain

### Detalhando o SegWit

Enquanto novos nós olham no novo campo *witness*:

```text
witness: <assinatura> <pubKey>
```

Nós antigos continuam olhando nos campos antigos:

```text
scriptPubKey: OP_0 <hash qualquer de 20 ou 32 bytes>
scriptSig: [vazio]
```

Onde

- `scriptPubKey`: define CONDIÇÕES para gastar

- `scriptSig`: fornece DADOS para satisfazer as condições

Ao receberem esses valores ao invés de um script de verdade, qualquer um pode satisfazer as condições para gastar os fundos daquela transação.

Exemplo comum de valores válidos:

```text
scriptSig: <assinatura> <pubKey>
scriptPubKey: OP_DUP OP_HASH160 <hash160(pubKey)> OP_EQUALVERIFY OP_CHECKSIG
```

Em outras palavras, para resumir:

> *SegWit* não usa o campo designado para dizer quem tem controle sobre o output(UTXO) criado naquela transação, então nós que não entendem *SegWit* pensam que aquele output pode ser gasto por qualquer um.

> Nós que entendem *SegWit* fazem a verificação do campo `witness` e rejeitam transações que não atendam as condições específicas do *SegWit*(diferente do `scriptPubKey`).

### Vantagem real do SegWit

Pelo que eu disse até aqui parece que o *SegWit* meramente move as assinaturas das transações para outro lugar no bloco. Que vantagem real ele traz? E qual a relação disso com o título do texto?

Antes as assinaturas estavam unidas de forma inseparável às transações, e por isso entravam no limite máximo de 1 MB que os blocos têm. Com *SegWit*, a parte principal do bloco fica preenchida de forma contígua somente por dados das transações, enquanto os *witness* ficam segregados em uma parte separada.

```text
┌─────────────────────────────────────┐
│ Block Header (80 bytes)             │
├─────────────────────────────────────┤
│ Transaction Count                   │
├─────────────────────────────────────┤
│ TRANSAÇÕES (parte principal)        │ ← Contíguas, SEM witness
│   TX1: version, inputs, outputs...  │
│   TX2: version, inputs, outputs...  │
│   TX3: version, inputs, outputs...  │
│   ...                               │
├─────────────────────────────────────┤
│ WITNESS DATA (separado)             │ ← Todos os witness juntos
│   Witness para TX1                  │
│   Witness para TX2                  │
│   Witness para TX3                  │
│   ...                               │
└─────────────────────────────────────┘
```

Em essência, *witness* contém as assinaturas e condições de gasto — o mesmo conteúdo que antes ficava embutido na transação, mas agora em local separado.

Aqui está o pulo do gato: **o** ***SegWit*** **redefiniu o que conta como “tamanho do bloco”**.

Antes, a regra era simples: “bloco não pode ter mais de 1 MB de dados, ponto final”. Isso limitava quantas transações cabiam, já que cerca de 60% de cada transação era ocupado pela assinatura.

O *SegWit* mudou a regra para: “bloco não pode exceder um certo **peso**, onde dados da transação base pesam 4x mais que dados witness”. Isso significa que assinaturas agora “contam menos” para o limite — é como se você pudesse colocar mais coisas numa mala porque roupas agora “pesam menos” que antes, mesmo ocupando o mesmo espaço físico.

O resultado? Blocos podem ter ~1.8-2.2 MB de dados reais (transações + assinaturas), mas para fins da regra de consenso ainda “cabem” dentro do limite.

Para nós antigos, nada mudou — eles só veem a parte base (~1 MB) e pensam “tudo normal, dentro do limite”. Nós novos veem o bloco completo (1.8-2.2 MB) mas aplicam as novas regras de peso que tornam isso válido.

**Em resumo:** ***SegWit*** **não economizou espaço de armazenamento — ele trapaceou no sistema de medição para permitir blocos maiores sem fazer hard fork.**

### Por que isso não quebra nada?

Nós antigos continuam vendo apenas a parte base das transações (sem witness), que fica abaixo de 1 MB — respeitando o limite antigo. Eles literalmente não enxergam os dados witness que foram adicionados. Ou seja, o limite de tamanho do bloco continua sendo respeitado retroativamente.

Por outro lado, *witness* é um campo importante que nós novos se importam. O que garante que as regras *SegWit* estão sendo respeitadas se nós antigos não fazem ideia sobre essas regras e não as usam para fazer sua validação?

Quem faz essa verificação são os mineradores que são nós novos por uma maioria quase unânime.

### Adoção do SegWit (Mineradores)

Como já expliquei em um [texto anterior](https://danielloureno1.substack.com/p/bitcoin-nao-e-dinheiro) o Bitcoin é um protocolo de consenso onde mudanças podem ser feitas desde que seja o consenso da rede. O BIP 9 definia um critério claro para organizar essa mudança repentina gerando o menor caos possível.

O BIP 9 dizia que os mineradores poderiam adicionar uma informação extra nos seus blocos de forma padronizada para sinalizar apoio. Caso num período de 2016 blocos seguidos 1916 blocos sinalizassem apoio, em mais 2016 blocos todos deveriam começar a usar as novas regras. Ou seja, se no período de duas semanas pelo menos 95% dos mineradores apoiassem as novas regras, em mais duas semanas eles poderiam usá-las.

De Novembro de 2016 até Maio de 2017 a sinalização dos mineradores apoiando *SegWit* ficou girando em torno de 30% sem sinal de aumentar. Muita coisa aconteceu nesse período entre Maio e Agosto de 2017 que tornam o *SegWit* a maior mudança no Bitcoin e a mais turbulenta.

Em 24 Maio 2017, o BIP 148 (UASF - User Activated Soft Fork) definiu que os nós que o adotassem iriam rejeitar blocos de mineradores que não sinalizassem apoio ao *SegWit* a partir de 1 de Agosto de 2017. Isso causaria um **Hard Fork!!**

Em 14 de Junho, o BIP 91 teve seu código finalizado. Ele servia como um passo intermediário na busca do consenso, definia regras mais brandas para ativação do *SegWit*: Somente 80% de sinalização num período de 336 blocos (2-3 dias).

Em 19 de Julho os 80% de sinalização do BIP 91 são atingidos evitando o fork do UASF, que aconteceria em menos de duas semanas.

Entre 23 e 24 de Agosto a rede atinge 100% de sinalização para *SegWit*.

Toda essa luta era necessária por um motivo. Em um *Soft Fork* os nós antigos perdem a capacidade de validar plenamente as transações seguindo o padrão *SegWit* pelos motivos já discutidos. Mas com a grande maioria dos mineradores fazendo essa validação, esse problema é mitigado. Sem falar que os nós antigos que não adotaram *SegWit* na main-net são uma raça em extinção.

Vale mencionar que em 1 de Agosto de 2017, antes mesmo do *SegWit* ativar, uma facção contrária à mudança executou um **hard fork** criando o Bitcoin Cash (BCH) — uma blockchain separada que rejeitou o *SegWit* e aumentou o tamanho dos blocos para 8 MB.

### Conclusão

Então se você é um nó desatualizado e usa uma versão anterior ao *Bitcoin Core 0.13.1*, lançado em 15 de outubro de 2016, você começou a ver bitcoins grátis sendo distribuídos pela rede e transações tentando usar esses bitcoins sendo recusadas por não ter um certo campo *witness* que você não faz ideia de pra que serve. Isso se deve aos mineradores que em sua totalidade aderiram ao *SegWit* e fazem a correta validação de todas as transações segundo as novas regras.

Nós antigos ainda podem usar a rede, fazer transações e receber pagamentos normalmente, apesar de usar um modelo de transação antigo que deixou de ser competitivo com os novos modelos, que pagam menos taxas pela sua otimização.

Respondendo ao título: Eles têm dono, mas nós antigos não sabem disso. Eles são UTXOs que foram criados por transações usando *SegWit*.

Foi uma boa oportunidade para explorar como o *SegWit* mudou a forma como o Bitcoin funciona. E ainda deu pra falar sobre a história do Bitcoin e dar uma ideia de como funciona BIPs e alterações das [regras de consenso](https://danielloureno1.substack.com/p/bitcoin-nao-e-dinheiro).

As discussões sobre *SegWit* se iniciaram em 2015 e se concretizaram totalmente em 2017, mas a adoção pelas pessoas não foi tão imediata como pode ver pela tabela a seguir mostrando a quantidade de transações feitas com *SegWit* e o número de nós reconhecendo e propagando transações *SegWit*.

```text
Data          | % TXs SegWit | % Nodes
--------------|--------------|----------
Ago 2017      | ~10%         | ~60%
Set 2017      | ~12%         | ~65%
Dez 2017      | ~14%         | ~70%
Mar 2018      | ~30%         | ~75%
Dez 2018      | ~40%         | ~80%
2019          | ~50%         | ~85%
2020          | ~60%         | ~90%
2021          | ~70%         | ~92%
2024          | ~85%         | ~95%
```

Mudanças no protocolo são possíveis, mas muito difíceis de serem feitas. Elas exigem a aceitação de quase toda a rede. Bitcoin pode mudar, mas resiste a isso. Acho isso perfeito pois gera a previsibilidade que ele vai continuar com as características que desejamos e amamos enquanto pode se adaptar contra possíveis inimigos como computação quântica ou qualquer outra coisa quem ainda nem imaginamos.

Se gostou desse texto, leia outros na mesma pegada:

> [Matemática por trás do Ataque de 51%](https://substack.com/home/post/p-185122608)
>
> Estou terminando uma disciplina de estatística que me dá ferramentas para analisar probabilidades associadas à variáveis aleatórias com certos tipos de distribuições. Nesse texto quero aplicar esse conhecimento em um exemplo do mundo real para solidificar o meu aprendizado e trabalhar em um tema que acho interessante.

> [Criptografia de Curva Elíptica](https://substack.com/home/post/p-185879880)
>
> Chaves Públicas e Privadas são o coração do Bitcoin. Bitcoins são propriedades de Chaves Públicas, que exercem essa propriedade assinando transações para outras chaves. Essas assinaturas, por sua vez, dependem da Chave Privada.

> [Bitcoin não é dinheiro](https://substack.com/home/post/p-184364651)
>
> O Bitcoin não é uma dinheiro eletrônico ponto a ponto. É um protocolo que busca consenso pois quer fugir do autoritarismo de qualquer instituição. E isso tem um preço.
