---
title: 'Treinando Minha Propria Inteligencia'
date: '2026-11-25T07:11:50-03:00'
draft: true
---

Recentemente o Substack começou a usar o serviço do Pangram para detectar escrita feita ou auxiliada por Inteligência Artificial. Enquanto muitas pessoas reclamaram ou discutiram sobre a utilidade ou necessidade de tal ferramenta, fiquei maravilhado com a acurácia. A própria empresa escreveu um artigo explicando um pouco sobre a tecnologia.

> [How does Pangram work?](https://pangram.substack.com/p/how-does-pangram-work)

Basicamente a ferramenta consegue não apenas detectar se houve interferência de LLMs, mas diferenciar a autoria do texto. Portanto, mesmo que o nome do autor seja incerto, o modelo é capaz de diferenciar textos de diferentes autorias, mesmo entre diferentes LLMs.

Enquanto chegar no estado da arte como o Pangram fez para ter uma taxa de falsos positivos irrisória, não é impossível atingir um resultado parecido com um modelo rudimentarmente treinado com menos dados. Pelo menos foi o que pensei. Esse texto mostra meu processo de implementar uma pipeline de treinamento de um modelo classificador que consiga diferenciar textos meus de outras pessoas, ou quem sabe até identificar o autor dentro de um grupo pré-selecionado.
