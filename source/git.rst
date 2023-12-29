.. _git:

=================================
The version control platform
=================================

What is a version control platform?
-----------------------------------

Version control platforms are platforms that...

In order to manage properly a new project, it is useful to create a repository in a version control platform. 

GitHub and GitLab
-----------------

The most popular platforms of this kind are **GitHub** and **GitLab**. Those platforms have different features, but they share the same Git environment, so no matter which one you choose to work with, the content of the GitHub repository and of the GitLab repository will be the same.


Hands on: create a repository for your technical documentation project
----------------------------------------------------------------------

Create an account on GitHub or GitLab.

Clone `this repository <https://framagit.org/coslo/template-docs>`__, which contains the basic files to build a Sphinx project. Use this commands in the shell:

.. code-block:: bash
	
	clone https://framagit.org/coslo/template-docs


(Python prerequisites)
~~~~~~~~~~~~~~~~~~~~~~

To make it work, you need to have Python (and pyenv) installed in your operating system. In this example, I installed ``pyenv`` with Homebrew:

.. code-block:: 
	
	brew install pyenv
	pyenv install 3.12.0

Then you need to change your PATH in order to...
	
.. code-block:: bash	
	
	pyenv global 3.12.0

 

