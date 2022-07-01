Pesquisar Tabelas (Java SE)
===========================

Como surgiu
-----------
Este programa surgiu de uma demanda e um problema (ou oportunidade). A Kugel_ é uma empresa com mais de 3 décadas de idade, logo, existe código legado. Entre o legado, está o banco de dados. O banco usado é o Pervasive, atual Actian_ Zen (PSQL), e sua principal característica é ser um banco de dados acessível para cobol e também para o Java (via JDBC).

E por causa desse banco de dados, os scripts ficam armazenados numa pasta, a qual precisávamos manter aberta para consultas. A pasta era o nosso dicionário de dados.

Então tive a ideia de criar um programa que consulta esses arquivos, baseado no nome da tabela. E acabei implementando busca por campos, por nomes, e etc. Resolveu tão bem o problema que todos os desenvolvedores da empresa adotaram.

Informações técnicas
-----------------------

Na verdade a ideia é simples. Com a API de arquivos do java `(java.file)` foi possível implementar a busca, navegação e leitura dos arquivos das tabelas. Bastou organizar o processo e montar uma tela para mostrar o resultado.

A tela a propósito foi feita com a API Swing do java `(javax.swing)`, que funciona muito bem e pode ficar bem bonita, se o programador for atencioso.

.. _Kugel: https://kugel.com.br
.. _Actian: https://esd.actian.com/product/Zen_PSQL

.. Modelo
.. O Projeto/Como Surgiu
.. Desafio
.. Informações técnicas
.. Como aconteceu (storytelling)
.. Código fonte
.. Endereço
.. Print
