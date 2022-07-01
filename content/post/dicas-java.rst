Dicas Java
==========

.. lang: pt-br

.. tags: java-br

Olá! Home vou escrever sobre Java. Provavelmente você sabe que sou programador Java, entretanto, ainda não escrevi sobre isso ainda. Até agora. E quero começar com o pé direito, o que significa, começar com algo simples de acompanhar, e melhor, de colocar em prática.

Como o título diz, quero te dar algumas dicas sobre programar. Note que algumas dicas talvez se apliquem a outras linguagens. Então, vamos começar!

.. read_more

Evitando NullPointerException
-----------------------------

Eu sei, esta exceção é uma das mais conhecidas, mas também é uma fácil de evitar. Em alguns casos, tudo que você precisa fazer é mudar o seu caso de teste, colocando a variável possível de ser nula depois. Considere esta situação:

.. sourcecode:: java

 String status = myService.findStatus();

Aqui está um possível NullPointerException, em caso de não testar a variável de status recebida, claro:

.. sourcecode:: java

 if (status.equals("MyStatus")) {
     myService.doSomething();
 } else {
     myService.doSomethingElse();
 }

Mas tudo que precisamos fazer é:

.. sourcecode:: java

 if ("MyStatus".equals(status)) {
     myService.doSomething();
 } else {
     myService.doSomethingElse();
 }

Desta forma temos exatamente a mesma condição e estamos evitando a exceção! Muito simples.

Abstraindo testes de valores
----------------------------

Esta é uma bela dica, em resumo, a ideia é abstrair os casos de testes de forma que facilite a leitura. Por exemplo, é muito comum testar se uma variável é nula e se tem valor. Talvez isso soe muito simples para você, mas confie em mim, no fim do dia, menos é muito muito mais.

Considere esta situação:

.. sourcecode:: java

 String status = myService.findStatus();

 if (status != null && !status.isEmpty()) {
     /* ... código aqui ... */
 }

Como eu disse, num primeiro olhar, não parece nada demais, mas podemos melhorar. Como:

.. sourcecode:: java
 
 if (ValueUtils.hasValue(status)) {
     /* ... código aqui ... */
 }

Agora veja esses dois exemplos acima, os quais são bem simples, mas imagine casos maiores, and quão feio as coisas podem ficar. O código é bem mais legível, não acha? Por sinal, uma classe ValueUtils se pareceria com isso:

.. sourcecode:: java

 public class ValueUtils {
     public static boolean hasValue(Object value) {
         if (value == null) {
             return false;
         }

         if (value instanceof String) {
             return !String.valueOf(value).trim().isEmpty();
         }

         /* outros tipos e classes aqui ... */
     }
 }

Bom pessoal, é isso por hoje. Assim que eu tiver mais dicas, eu voltarei! Se você tem alguma dúvida ou dica, por favor, compartilhe comigo nos comentários! o/

[`See in English`_]

.. _`See in English`: /post/java-tips
