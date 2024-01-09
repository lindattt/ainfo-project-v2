.. _temi:

=======
Themes
=======

Sphinx supports changing the appearance of its HTML output via **themes**. A theme is a collection of HTML templates, stylesheets and other static files.

The default theme for a Sphinx project is *Alabaster*, but there are plenty of free themes that you can choose. Here you can find some: https://sphinx-themes.org.


Exercise: Change the theme of your Sphinx project
-------------------------------------------------

Suppose that you've browsed `Sphinx themes <https://sphinx-themes.org>`__ and you've chosen `Read the docs <https://sphinx-themes.org/sample-sites/sphinx-rtd-theme/>`__ theme for your project. These few steps will show you how to install and use it.

*   **Step 1**: install the theme.

In your shell, run:

.. code-block:: shell

	pip install sphinx-rtd-theme

*   **Step 2**: edit ``conf.py`` file.

Open ``conf.py``, look for the ``html_theme`` variable end edit as follows:

.. code-block:: python

	html_theme = 'sphinx_rtd_theme'

*   **Step 3**: build.

Build your documentation and enjoy your new theme.