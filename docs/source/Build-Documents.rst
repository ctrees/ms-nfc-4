.. _Build-Documents:

==============
Build Document
==============

Basic Document Build with controlled environment::

    $ git clone https://github.com/ctrees/ms-nfc-4.git
    $ cd ms-nfs-4
    $ mkdir ansible/roles
    $ ./scripts/atb-role-deps.sh ansible/site.yml
    $ vagrant up

Build Documents::

    $ vagrant ssh docbuild
    [vagrant@docbuild ~]$ cd /vagrant/docs 
    [vagrant@docbuild ~]$ make html

Use msops to share docs::

    $ ssh msops@172.28.128.3
    NOTE: given the user is msops AND has the ssh pubkey in ~/.ssh/id_rsa.pub
    NOTE: Ansible runs via the vagrant user in local mode
    $ [msops@docbuild ~]$ cd public_html/
    $ [msops@docbuild ~]$ cp -R /vagrant/docs/build .
    NOTE: I copied the build to preserve, you could ln but I did have issues with ln permissions over share mount

Browse ms-nfc-4_Documentation_ ::

    $ open http://172.28.128.3/~msops/build/html/index.html

.. _ms-nfc-4_Documentation: http://172.28.128.3/~msops/build/html/index.html