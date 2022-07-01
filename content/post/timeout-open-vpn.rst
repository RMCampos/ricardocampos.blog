Timeout OpenVPN
===============

.. lang: pt-br

.. tags: linux-br

Aqui vai uma dica rápida para quem está tendo problemas para conectar num servidor utlizando OpenVPN e ficou preso no *timeout*.

Na realidade o *timeout* é uma consequência do erro. O que houve de fato precisa ser visto a partir do log do sistema. No meu caso foi um problema com a versão mínima suportada do TLS. Por padrão se tem as instalações com a versão mais recente (v1.2 no dia que escrevi esta dica) através das atualizações do sistema.

E se a versão do servidor estiver com uma versão anterior vai dar esse problema. A solução é alterar o arquivo **/etc/ssl/openssl.cnf** (no Debian) e habilitar o suporte à uma versão anterior, alterando o valor do item **MinProtocol** para TLSv1.1 ou TLSv1.

.. code:: shell

    # vim /etc/ssl/openssl.cnf

    [system_default_sect]
    MinProtocol = TLSv1.1

Isso deve resolver o problema. Um abraço e até!

[`See this page in English`_]

.. _`See this page in English`: /post/openvpn-timeout
