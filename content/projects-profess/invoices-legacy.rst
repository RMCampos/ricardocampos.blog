Legacy Invoices (Java SE - Swing)
=================================

.. date: 2018-07-02 14:00:00

O projeto
---------

- Atualização para NFe 4.0

Este projeto merece relato devido à complexidade e importância como uma das partes principais e mais usadas do ERP. O projeto consiste não só na atualização para as mudanças previstas na nova versão mas também num programa inteiramente novo. Isso significa mudança principalmente para o cliente, e como toda mudança grande, vem acompanhada de insegurança e medo.

E o motivo de precisar de um programa inteiramente novo é a idade e a obsolescência da versão do programa atual, da nota 3.10. Por ser um programa antigo, legado, está cheio de gambiarras e código espalhado de maneira confusa.

Desafio
-------

Em resumo parece simples: adicionar algumas *tags* novas ao XML e manter as funções do programa antigo. Porém foi ao estudar as mudanças e mapear tudo que era feito, foi quando compreendemos o tamanho do problema. E no meio do caminho decidimos **melhorar** algumas coisas e deixar o programa mais **inteligente**. Risos. 

Informações técnicas
-----------------------

A versão antiga era escrita em C++ Builder e COBOL. A tela em C++ Builder e o processamento em COBOL. Então boa parte da dificuldade foi *traduzir* para Java e manter o mesmo resultado.

Por usar essas linguagens de baixo nível o processamento era veloz, mesmo em estruturas que pareciam lentas, como efetuar múltiplas consultas ao banco dentro de loops e coisas assim.

Quanto ao banco de dados não houve mudança. A versão antiga acessava via BDE e a versão nova via JDBC. Já tinhamos bibliotecas prontas para ambos.

Como aconteceu
--------------

Pois bem. Eu fui o principal desenvolvedor referente a conversão para Java. Além de mais 2 desenvolvedores que estavam junto, um para cuidar da comunicação e consumo dos webservices e outro para cuidar que a versão nova seria tão boa ou melhor quanto a antiga.

Eu comecei com a tela. Disposição dos botões e layouts. A ideia foi ter algo próximo da versão antiga mas que ainda sim ficasse evidente que existiam novidades. Dei atenção especial aos eventos, cuidando para regras de UX e não permitindo que o programa executasse tarefas em meio a preenchimento de campos e cliques que não fossem em botões.

Terminando a tela comecei a parte da lógica, regra de negócio e funcionamento em sí. 

E assim mais um programa foi finalizado! 