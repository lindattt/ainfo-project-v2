.. _markup:

=====================
The markup language
=====================


.. _what is a markup language:

What is a markup language
--------------------------

A **markup language** is a language whose syntax allows to format text and organize the layout of a digital document.

A file written in a markup language is then **processed** by a compiler (like :ref:`Sphinx <sphinx>`) and **rendered** in the desired output (HTML, LaTeX, and so on).

There are many markup languages; some of these are characterixed by a "light" syntax, i.e. a syntax that can be easily interpreted by a human user. Among these lightweight languages, two famous choices are **Markdown** and **reStructured Text**, which by the way share a lot of common syntax.

For simplicity, in this tutorial we will work with reStructured Text only.

reStructured Text
------------------

**reStructured Text (reST)** is a simple and straightforward markup language.

The following is a short list of formattating commands for your text in reStructured Text.


Headings
~~~~~~~~

Title and headings are formatted as follows:

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
	
	

Bold, italics
~~~~~~~~~~~~~

**How it looks:**

	**bold text**, *italics text*

**Source:**

.. code-block:: rest

	**bold text**, *italics text*


Links
~~~~~

**How it looks:**

   For example, this `link <https://github.com/>`__ redirects to GitHub.

**Source:**

.. code-block:: rest
   
   For example, this `link <https://github.com/>`__ redirects to GitHub.
   

Crossreferences 
~~~~~~~~~~~~~~~~

To put a tag on a header or title of a page:

.. code-block:: rest

   .. _my-header-tag: 
   
   Header
   ======
   
Then to call it in another page:

.. code-block:: rest

   Click :ref:`here <my-header-tag>` to be redirected to a specific section.



Code blocks
~~~~~~~~~~~

**How it looks:**

   .. code-block:: bash
   
      echo "Hello world"

**Source:**

.. code-block:: rest

   .. code-block::
   
      echo "Hello world"


Inline code
~~~~~~~~~~~
**How it looks:**

	Run ``git init`` to initialize a repository.

**Source:**

.. code-block:: rest

   Run ``git init`` to initialize a repository.



Notes, admonitions
~~~~~~~~~~~~~~~~~~

**How it looks:**

.. note::
   A box with a note
   
**Source:**

.. code-block:: rest

   .. note::
      A box with a note


.. Toctree (Sphinx)
	~~~~~~~~~~~~~~~~
	To hide the toctree:
	.. code-block:: rest
	 .. toctree::
       :hidden:


Tables
~~~~~~

**How it looks:**

.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - Heading row 1, column 1
     - Heading row 1, column 2
     - Heading row 1, column 3
   * - Row 1, column 1
     -
     - Row 1, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3


**Source:**

.. code-block:: rest

	.. list-table:: Title
   		:widths: 25 25 50
   	 	:header-rows: 1

   	 	* - Heading row 1, column 1
   	  	  - Heading row 1, column 2
     	  - Heading row 1, column 3
   	    * - Row 1, column 1
 		  -
		  - Row 1, column 3
 		* - Row 2, column 1
  	      - Row 2, column 2
  		  - Row 2, column 3



Exercise: use reST syntax to format your pages
----------------------------------------------

Try to use the syntax rules shown above to format your documentation.
