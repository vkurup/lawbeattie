lawbeattie.com
--------------

Local Setup
===========

#. Install `complexity <https://complexity.readthedocs.io/en/latest/>`_::

     pip install -r requirements/dev.txt


Github pages setup
==================

This is deployed to GH pages using the `docs folder on master branch` option. A CNAME file is
created at the top level for the custom domain. HTTPS is enabled in GitHub. Two CNAME records are
created at the registrar for `www` and `@`, both pointing to vkurup.github.io.

It takes a while for the pages to be built and for the cert to be issues, at least the
first time.


Site changes
============

#. Make the changes in the ``src`` directory. Build the site (which will generate the
   files in the ``docs`` directory) and view it at localhost:9090::

     complexity src

#. When you're satisfied, commit to the changes to master and Github Pages will deploy it.
