lawbeattie.com
--------------

Setup
=====

#. Install `complexity <https://complexity.readthedocs.io/en/latest/>`_::

     pip install -r requirements.txt

#. Build the site::

     complexity src

#. This installs the site into the `www` folder and runs a server at localhost:9000. Use the
   following command to just build the pages::

     complexity --noserver src
