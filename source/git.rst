.. _git:

=================================
The version control platform
=================================

What is a version control platform?
-----------------------------------

Version control platforms are platforms that allow you to keep track of the changes done to your code over time, and to resume an older version of it if needed.

In order to manage properly a new project, it is useful to create a repository in a version control platform. 

GitHub and GitLab
-----------------

The most popular platforms of this kind are `GitHub <https://github.com>`__ and `GitLab <https://gitlab.com>`__. Those platforms are different but they share similar features, so no matter which one you choose to work with, the content of the GitHub repository and of the GitLab repository will basically be the same, as well as the shell commands you need to know to work from locally from your computer.


Exercise: create a repository for your technical documentation project
----------------------------------------------------------------------

.. note:: 
   You need to have `Git <https://git-scm.com/downloads>`__, `Python <https://www.python.org/downloads/>`__ and `pyenv <https://github.com/pyenv/pyenv>`__ installed in your operating system.
   
For the sake of brevity, in the following examples we will work with GitHub, but the same commands and instructions apply to GitLab.

*   Create an account on `GitHub <https://github.com>`__. 

If you choose for example ``myuser`` as a username, your personal account will be created at this link: ``https://github.com/myuser``.

.. *la configurazione la salto, perché viene dal prerequisito di avere installato Git sull'OS

*   Open the shell in the directory you want to work on. Let it be, for example, your home directory ``~/``.
   
*   Create a new repository on GitHub. Let's use the command line interface (CLI):

.. code-block:: bash

	gh repo create

The terminal will ask you a series of questions, which you can answer by selecting an option or typing. Let's create a new repository from scratch:

.. code-block:: bash

	? What would you like to do?  [Use arrows to move, type to filter]
	> Create a new repository on GitHub from scratch
	  Create a new repository on GitHub from a template repository
	  Push an existing local repository to GitHub
	  
Then you will be asked to name the new repository. Let's call it ``myrep``:

.. code-block:: bash

	? Repository name myrep
	
After that you will be asked a number of questions regarding the privacy settings of your repository and the files you may want to add immediately. 
You can choose the default options by pressing the enter key and the output will be this:

.. code-block:: bash

	? Description 
	? Visibility Public
	? Would you like to add a README file? No
	? Would you like to add a .gitignore? No
	? Would you like to add a license? No
	? This will create "myrep" as a public repository on GitHub. Continue? Yes
	✓ Created repository myuser/myrep on GitHub
	? Clone the new repository locally? Yes
	
If you answer yes to the last question, the repository will be copied locally, and its path will be ``~/myrep``. 

*	Clone `this repository <https://framagit.org/coslo/template-docs>`__.

.. code-block:: bash
	
	git clone https://framagit.org/coslo/template-docs

This repository contains the basics to put up a virtual environment with python and sphinx installed.
	
*	Push the cloned content in your repository.

.. code-block:: bash
	
	git add .
	git commit -m "first commit"
	git push origin main
	
Now you have everything set up to start working on your project.






 

