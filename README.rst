lawbeattie.com
--------------

Local Setup
===========

#. Install `complexity <https://complexity.readthedocs.io/en/latest/>`_::

     pip install -r requirements/dev.txt

Dokku setup
===========

#. Make sure that your SSH config for dokku is set up::

     Host dokku
       Hostname git.drkurup.com
       User dokku
       RequestTTY yes

#. create the app::

     ssh dokku apps:create lawbeattie
     ssh dokku apps:create lawbeattie-staging
     ssh dokku git:set lawbeattie-staging deploy-branch develop

#. add the dokku git remote for production::

     git remote add prod dokku@git.drkurup.com:lawbeattie
     git push prod master

#. add the dokku git remote for staging::

     git remote add staging dokku@git.drkurup.com:lawbeattie-staging
     git push staging develop

#. add domains::

     ssh dokku domains:add lawbeattie lawbeattie.com
     ssh dokku domains:add lawbeattie www.lawbeattie.com


Site changes
============

#. Make the changes in the `src` directory. Build the site and view it at localhost:9090::

     complexity src

#. When you're satisfied, commit to develop and push develop to staging::

     git push staging develop

#. When you're satisfied with staging, merge develop to master and push master to prod::

     git push prod master
