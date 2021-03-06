.. _mai:

===
Mai
===

**Mai** is a command line utility to retrieve temporary AWS credentials.

Installation
============

Install or upgrade to the latest version of Mai (|mai-pypi-version|) with PIP:

.. |mai-pypi-version| image:: https://img.shields.io/pypi/v/stups-mai.svg
   :target: https://pypi.python.org/pypi/stups-mai/
   :alt: Latest PyPI version

.. code-block:: bash

    $ sudo pip3 install --upgrade stups-mai

How to use
==========

Creating a new profile:

.. code-block:: bash

    $ mai create myteam
    $ Identity provider URL: https://aws.example.org # Enter your Identity Provider URL
    $ SAML username: john.doe@example.org # Enter your SAML username
    # answer the questions

Deleting a profile:

.. code-block:: bash

    $ mai delete myteam

List profile(s):

.. code-block:: bash

    $ mai list

Login profile(s):

.. code-block:: bash

    $ mai login myteam

If you only have one profile, you can simply execute ``mai`` to login:

.. code-block:: bash

    $ mai
    $ # credentials are now stored in ~/.aws/credentials
    $ aws ec2 describe-instances # example usage

You can set the default profile to use when running ``mai`` without arguments:

.. code-block:: bash

    $ mai set-default myprofile

.. Tip::

    Mai commands can be abbreviated, i.e. the following commands are equivalent:

    .. code-block:: bash

        $ mai set myprof
        $ mai set-def myprof
        $ mai set-default myprof


.. Note:: Mai will save its configuration in a YAML file in your home directory (``~/.config/mai/mai.yaml`` on Linux, ``~/Library/Application\ Support/mai/mai.yaml`` on OSX)
