lawbeattie.com
--------------

Setup
=====

#. Install `complexity <https://complexity.readthedocs.io/en/latest/>`_::

     pip install -r requirements.txt

#. Build the site::

     complexity src

#. This installs the site into the `www` folder and runs a server at localhost:9090. Use the
   following command to just build the pages::

     complexity --noserver src


Dokku setup
===========

#. Make sure that your SSH config for dokku is set up::

     Host dokku
       Hostname git.drkurup.com
       User dokku
       RequestTTY yes

#. create the app::

     ssh dokku apps:create lawbeattie

#. add the dokku git remote::

     git remote add dokku dokku@git.drkurup.com:lawbeattie
