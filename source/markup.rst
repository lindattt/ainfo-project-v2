.. _markup:

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
   

Crossreferences 
~~~~~~~~~~~~~~~~

To put a tag on a header or a page:

.. code-block:: rest

   .. _my-header-tag: 
   
   Header
   ======
   
Then to call it in another page:

.. code-block:: rest

   Click :ref:`here <my-header-tag>` to be redirected to a specific section.



Code blocks
~~~~~~~~~~~

.. code-block:: rest

   .. code-block::
   
      echo "Hello world"


Inline
~~~~~~

To emphasize a certain word like ``this``:

.. code-block:: rest

   ``this``



Notes, admonitions
~~~~~~~~~~~~~~~~~~~~

Output:

.. note::
   A box with a note
   
Source code:

.. code-block:: rest

   .. note::
      A box with a note


Toctree (Sphinx)
~~~~~~~~~~~~~~~~

To hide the toctree:

.. code-block:: rest

    .. toctree::
       :hidden:


HANDS ON: use reST syntax to customize your pages
----------------------------------------------------------------------
