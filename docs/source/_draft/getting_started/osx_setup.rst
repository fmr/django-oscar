================================================
Setting up a development environment on Mac OS X
================================================

This article contains instructions on how to set up the pre-requisites to develop on oscar.

Install MacPorts and Python Packages
------------------------------------

* Install MacPorts  

  To install MacPorts, follow the instructions specified `here`_.

.. _`here`: http://www.macports.org/install.php

* Install Python 2.7::

    # port install python27 && sudo python_select python27
    
* Install the Python Imaging Library (``PIL``)::

    # port install py27-pil

* Use Python 2.7 by default::

    # python_select python27
    # easy_install pip
    # ln -s pip-2.7 /opt/local/bin/pip

* Install ``virtualenvwrapper``::

    # pip install virtualenv virtualenvwrapper
    # ln -s /opt/local/Library/Frameworks/Python.framework/Versions/2.7/bin/virtualenvwrapper.sh /opt/local/bin/virtualenvwrapper.sh
    

Bash configuration
------------------

Add these lines to `~/.bash_profile` or `~/.bashrc`, making sure to replace the value of `PROJECT_HOME` to your project directory::

    export PIP_RESPECT_VIRTUALENV=true
    export PROJECT_HOME=$HOME/Documents/Code/python
    export VIRTUALENVWRAPPER_PYTHON=/opt/local/bin/python
    source /opt/local/bin/virtualenvwrapper.sh

Reload Bash settings::

    $ source ~/.bash_profile

OR::

    $ source ~/.bashrc
