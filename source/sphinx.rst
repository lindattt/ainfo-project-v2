.. _sphinx:

============================
The documentation compiler
============================

What is a documentation compiler
--------------------------------

A **documentation compiler** is a compiler that converts plain text files (written in Markdown, reStructured Text or other markup languages) into interactive documentation, for example in the form of HTML, LaTeX, ePub and other formats.


Sphinx
------

The documentation compiler that we are going to use in this tutorial is `Sphinx <https://www.sphinx-doc.org>`__.

If you followed the steps described in :ref:`this section <esercizio1>`, you don't need to install Sphinx again: the **virtual environment** is already equipped with a Sphinx installation.


Exercise: build your first page of documentation
-------------------------------------------------

In this section we will learn how to build documentation using Sphinx.

*	**Step 1**: Activate the virtual environment

The virtual environment included in the repository you've copied will provide you a Python installation and a recent version of Sphinx.

To activate the virtual environment, run the following command:

.. code-block:: bash

	conda activate coderefinery
	

*	**Step 2**: Use sphinx-quickstart

We can easily generate the basic documentation template with a built-in command in Sphinx. Run:

.. code-block:: bash

	sphinx-quickstart

The quickstart utility will ask you some questions. You can choose to go with the default answers or to specify names, preferences and details for your project. For example:

.. code-block:: bash

	> Separate source and build directories (y/n) [n]: <type y>
	> Project name: <your project name>
	> Author name(s): <your name>
	> Project release []: <hit enter>
	> Project language [en]: <hit enter>

After that, some files and some directories will be created.


Directories:

*	**source**: contains plain-text files of documentation.
*	**build**: contains output files	


Files:
	 
*	**index.rst**: main file for Sphinx. It contains the index of all pages of the documentation and represents the homepage of the documentation once the project is converted in an interactive output format (like HTML).
*	**conf.py**: configuration file for Sphinx. It contains metadata and information regarding extensions, themes, etc.


We will now take a closer look on those two files


The document ``index.rst``
--------------------------

The document ``index.rst`` contains the table of contents (*toctree*) of the documentation.

Using the quickstart utility, your index file will look like this:

.. code-block:: rest

	.. myproject documentation master file, created by
	   sphinx-quickstart on Sat Dec 23 17:35:26 2023.
	   You can adapt this file completely to your liking, but it should at least
	   contain the root `toctree` directive.

	Welcome to myproject's documentation!
	=====================================

	.. toctree::
	   :maxdepth: 2
	   :caption: Contents:


	Indices and tables
	==================

	* :ref:`genindex`
	* :ref:`modindex`
	* :ref:`search`


We can delete the ``Indices and tables`` section since we won't use it in this tutorial. To add content to our documentation, we must create plain-text files in the ``source`` directory and then add them to the ``toctree``. For example, we create two reStructured Text files, ``page1.rst`` and ``page2.rst``, and then list these files (without specifying extension, in case of .rst files) under the ``toctree``.

.. code-block:: rest

	.. myproject documentation master file, created by
	   sphinx-quickstart on Sat Dec 23 17:35:26 2023.
	   You can adapt this file completely to your liking, but it should at least
	   contain the root `toctree` directive.

	Welcome to myproject's documentation!
	=====================================

	.. toctree::
	   :maxdepth: 2
	   :caption: Contents:

	   page1
	   page2


.. attention::
	
	Pay attention to the indentation of the file names under the toctree. The file names must be indented correctly in order to be interpreted as the content of the toctree. 
	

You can now edit the documents you've created and format them with reStructured Text markup language and add more content to the toctree.


The document ``conf.py``
-------------------------

The document ``conf.py`` contains Python instructions for the Sphinx builder. 

The information contained in this document covers project information, metadata, sphinx extensions, themes and so on.

.. code-block:: python

	# Configuration file for the Sphinx documentation builder.
	#
	# This file only contains a selection of the most common options. For a full
	# list see the documentation:
	# https://www.sphinx-doc.org/en/master/usage/configuration.html

	# -- Path setup --------------------------------------------------------------

	# If extensions (or modules to document with autodoc) are in another directory,
	# add these directories to sys.path here. If the directory is relative to the
	# documentation root, use os.path.abspath to make it absolute, like shown here.
	#
	# import os
	# import sys
	# sys.path.insert(0, os.path.abspath('../'))


	# -- Project information -----------------------------------------------------

	project = 'Project'
	html_title = 'Project'
	copyright = '2023, John Doe'
	author = 'John Doe'


	# -- General configuration ---------------------------------------------------

	# Add any Sphinx extension module names here, as strings. They can be
	# extensions coming with Sphinx (named 'sphinx.ext.*') or your custom
	# ones.
	# extensions = ['sphinx.ext.autodoc', 'sphinx.ext.coverage', 'sphinx.ext.napoleon']
	extensions = []

	# Add any paths that contain templates here, relative to this directory.
	templates_path = ['_templates']

	# The root document.
	root_doc = 'index'

	# Highlights: do not highlight literal blocks
	highlight_language = 'none'

	# List of patterns, relative to source directory, that match files and
	# directories to ignore when looking for source files.
	# This pattern also affects html_static_path and html_extra_path.
	exclude_patterns = ['_build', 'Thumbs.db', '.DS_Store']

	# Add any paths that contain custom static files (such as style sheets) here,
	# relative to this directory. They are copied after the builtin static files,
	# so a file named "default.css" will overwrite the builtin "default.css".
	html_static_path = []

	# The theme to use for HTML and HTML Help pages.  See the documentation for
	# a list of builtin themes.
	html_theme = 'furo'

	if html_theme == 'alabaster':
	    pygments_style = 'friendly'
	    html_static_path = ['_static/custom.css']
	    html_theme_options = {
	        'description': 'Code description',
	        'fixed_sidebar': True,
	        'sidebar_collapse': True,
	        'extra_nav_links': {},
	        'gray_2': '#F4F4F4ED',
	        'sidebar_width': '250px',
	        'body_max_width': 'auto',
	        'page_width': '1000px',
	    }

	    html_sidebars = {
	        '**': [
	            'about.html',
	            'navigation.html',
	            'searchbox.html',
	            'relations.html',
	            'donate.html',
	        ]
	    }

	if html_theme == 'sphinx_rtd_theme':
	    import sphinx_rtd_theme
	    extensions += [
	        'sphinx_rtd_theme',
	    ]
	    html_theme_options = {
	        'display_version': True,
	        'vcs_pageview_mode': '',
	        # Toc options
	        'collapse_navigation': False,
	        'sticky_navigation': True,
	        'navigation_depth': 4,
	        'includehidden': True,
	        'titles_only': False
	    }

	if html_theme == 'furo':
	    pygments_style = 'tango'
	    # html_static_path = ['_static/furo/']
	    # html_css_files = ['custom.css']
	    html_theme_options = {
	        "light_css_variables": {
	            "admonition-title-font-size": "1rem",
	            "admonition-font-size": "1rem",
	        },
	    }
	
	
	
	
Information about the variables contained in this document can be found in `this page <https://www.sphinx-doc.org/en/master/usage/configuration.html>`__.

Let's take a closer look on some specific part of conf.py. 




Project information
~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

	project = 'Project'
	html_title = 'Project'
	copyright = '2023, John Doe'
	author = 'John Doe'
	
In this section we can edit: the name of the project; the title that will appear in each HTML page of the output; the copyright statement; the author name.



``extensions``
~~~~~~~~~~~~~~~~~

.. code-block:: python

	extensions = []
	
Extensions can be added to the build process, in order to customize almost any aspect of document processing. Extensions must be added as strings. Examples of built-in extensions provided by Sphinx are ``sphinx.ext.doctest``, which tests snippets in the documentation, or ``sphinx.ext.doctest``, which enables the creation of to-do lists.



``templates_path``
~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

	templates_path = ['_templates']

Themes and templates are two different things.

You can overwrite only specific blocks within a template, customizing it while also keeping the changes at a minimum.

Sphinx will look for templates in the folders of templates_path first, and if it can’t find the template it’s looking for there, it falls back to the selected theme’s templates.


``root_doc``
~~~~~~~~~~~~~~~~~
	
.. code-block:: python
	
	root_doc = 'index'
	
The document name of the “root” document, that is, the document that contains the root toctree directive. Default is 'index'.


``highlight_language``
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python

	highlight_language = 'none'
	
This variable refers to the default programming language to highlight source code in. Almost any documentation project contains code blocks to explain chunks of the code; this page itself contains several blocks. It is possible to customize each block so that the text is not single-coloured but highlighted, as it would be in the editor. If no specification is indicated in the block, the highlight will be the one contained in the ``highlight_language`` variable. 
For example, if we are writing documentation exclusively related to fortran

.. code-block:: fortran

	1+1
	
.. code-block:: html

	1+1
	
	

``exclude_patterns``
~~~~~~~~~~~~~~~~~~~~~~~~

This string contains pattern that are excluded when looking for source files during the building. 


.. code-block:: python
	
	exclude_patterns = ['_build', 'Thumbs.db', '.DS_Store']


``html_static_path``
~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: python
	
	html_static_path = []

This variable consists of paths that contain custom static files, i.e. CSS files that enable to customize the style of the HTML output. For example, we can create a file :file:`custom.css` in the :file:`_static` folder and change the main body font family, from sans-serif (which is default for furo's theme) to serif:

.. code-block:: python
	
	#conf.py
	
	html_static_path = ['_static']

	html_css_files = ['custom.css']
	
	
.. code-block:: css
	
	/* custom.css */
	
	body {
	  font-family: serif;
	}
	
``html_theme``
~~~~~~~~~~~~~~~~~~~
This variable allows to change the theme of the HTML output. 

Alabaster is default.

Example


.. code-block:: python
	
	html_theme = 'furo'

To change it, just download the package, put it in ????, then change the name in ``conf.py``
 
.. code-block:: python
	
	html_theme = 'alabaster'
	
	