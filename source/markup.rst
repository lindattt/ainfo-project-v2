=====================
The markup language
=====================


.. _what is a markup language:

What is a markup language
--------------------------

A markup language is...

Sono linguaggi leggeri (rispetto ad HTML)

Possono venire tradotti in html

Sphinx li traduce automaticamente, nella compilazione... sì, perché mica mi obblica a scrivere in rest...



reStructured Text
------------------

reStructured Text is a simple and straightforward markup language.

The following is a short list of formattating commands for your text in reStructured Text.

Elementi di formattazione (gli stessi che ho usato io)

Headings
~~~~~~~~

.. code-block:: rest

	=====
	Title
	=====
	
	Heading 1
	=========
	
	Heading 1.1
	-----------
	
	Heading 1.1.1
	~~~~~~~~~~~~~
	
	Heading 1.1.1.1
	"""""""""""""""
	
	

Bolds, italics, ...
~~~~~~~~~~~~~~~~~~~

.. code-block:: rest

	**bold text**, *italics text*, ...


Links
~~~~~

.. code-block:: rest

   `anchor text <URL>`__
   
   For example, this `link <https://github.com/>`__ redirects to GitHub.


Code blocks
~~~~~~~~~~~

.. code-block:: rest

   .. code-block::
   
      echo "Hello world"

Inline

Trying this :ref:`cross reference thing <what is a markup language>`