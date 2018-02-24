.. _Build-Documents:

==============
Build Document
==============

Basic Document Build with controlled environment::

    $ git clone https://github.com/ctrees/ms-nfc-4.git
    $ cd ms-nfs-4/ansible
    $ ../scripts/abt-role-deps.sh
    $ cd ..
    $ pwd (should be in ms-nfs-4
    $ vagrant up

Build Documents::

    $ vagrant ssh docbuild
    docbuid $ cd /vagrant/docs 
    docs $ make html
