Timeout OpenVPN
===============

.. lang: en

.. tags: linux

.. date: 2019-12-12 22:43:35

Here's a quick tip for those who are having trouble connecting to a server using OpenVPN and get stuck in *timeout*.

Actually, *timeout* it's a consequence. What really happened needs to be seen on the system log. In my case, it was an issue about the minimum TLS supported version. By default, we have the more recent version (v1.2 on the day that I'm writing this post) updated through the system update.

So, if the destiny server has a different version than your system, you'll face this problem. The solution is to change the file **/etc/ssl/openssl.cnf** (on Debian) and enable support for old versions, changing the item **MinProtocol** to TLSv1.1 or TLSv1.

.. code:: shell

    # vim /etc/ssl/openssl.cnf

    [system_default_sect]
    MinProtocol = TLSv1.1

That should fix the problem. See ya!

[`Ver esta página em Português (br)`_]

.. _`Ver esta página em Português (br)`: /post/timeout-open-vpn
