Standalone version
=====

.. _installation:

Installation
------------

To use the standalone version of PepQuery2, first install it on your computer:

You must have Java 1.8 or newer installed. To check your java version please open your terminal 
application and run the following command:

.. code-block:: console

   java -version

Next go to download the standalone version of PepQuery here <http://www.pepquery.org/data/pepquery-2.0.2.tar.gz>. 
After you download it, please uncompress it using the following command line and you will find a jar file in the package folder. 
The whole installation process typically only takes one or two minutes.

.. code-block:: console

   tar xvzf pepquery-2.0.2.tar.gz

Identifying novel peptides
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

