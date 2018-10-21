Notes on Infrastructure
=======================

The practical exercises of this workshop will be running on a separate virtual machine (VM) for each participant. Access to this virtual machine can be obtained using various channels, including a custom terminal client software (such as Terminal on Mac OS X) and Jupyter_, a browser based system for interactive computing. For the following, I will assume access via Jupyter.

How to Connect to Jupyter
-------------------------

To connect to the Jupyter interface for your virtual machine, open your favourite Browser, go to the `VM Server entry page`_, and click on the Jupyter link indicated for your particular machine. You will be asked to enter the password you have been given for your personal VM.

.. _Jupyter: http://jupyter.org
.. _VM Server entry page: http://195.148.31.27:3000/connect


Basic Usage
-----------
When you first access Jupyter, you will get a file browser view of the ``~/work`` folder on your VM. In the beginning that list will be empty, and will be populated with notebooks and files throughout this workshop. 

To create a new text file, click on *New* and then *Text File*, which opens a text editor within your browser. You can now add content into the file, or edit existing content and save. The filename can be changed by clicking into the Filename on top. You can now go back to your file browser window and update using the button with the two arrows in the upper right corner, and you should see your text file saved under ``~/work`` on your VM.

You can also use Jupyter to open a Terminal within the browser: Click on *New* and then *Terminal*, which will open a terminal window in a separate browser tab. You can enter Unix Bash commands to change directories, view files or execute programs. 

.. note:: To use the terminal, some basic knowledge of Unix is required. For this workshop, you will frequently use tools such as ``pwd`` to view the current directory, ``ls`` to view the contents of the current directory, ``cd`` to change the directory, ``cat`` to output the contents of a file, ``grep`` to search in a text file and other commands.

Finally, you can create new Folders by clicking on *New* and then *Folder*. To rename the new folder, click on the checkbox beside the new folder, and click the *Rename* button on top, which appeared. To change into the new folder, click on it. To move back, click on the parent folder appearing on top of the file browser.

.. admonition:: Exercise

  Create a new folder called ``fun``, and a text file within that folder using Jupyter. Fill the text file with arbitrary content, such as "Hello, World!". Then open a terminal and output the new text file using the ``cat`` command.

Notebooks
---------

Bash Notebook
*************

Markdown
********
Headings, Subheadings, Text, italics and bold

Executing Code
**************

Python Notebooks
****************

Plotting in Python Notebooks
****************************

Reproducible Science
********************

(workflows depending on raw data and then with execution top->down)





  
