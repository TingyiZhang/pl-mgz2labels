pl-mgz2labels
================================

.. image:: https://travis-ci.org/FNNDSC/mgz2labels.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/mgz2labels

.. image:: https://img.shields.io/badge/python-3.8%2B-blue.svg
    :target: https://github.com/FNNDSC/pl-mgz2labels/blob/master/setup.py

.. contents:: Table of Contents


Abstract
--------

MGZ label-wise converter


Description
-----------

``mgz2labels`` is a ChRIS-based application whose backbone is pl-mgz_converter:: https://github.com/FNNDSC/pl-mgz_converter. The input file structure is the same as pl-mgz_converter. The output will be 193 labels for each subject in separated folder, and 193 .npy files for each label. The output of this plugin is set to be used for pl-mricnn:: https://github.com/FNNDSC/pl-mricnn training.


Usage
-----

.. code::

    python mgz2labels.py
        [-h|--help]
        [--json] [--man] [--meta]
        [--savejson <DIR>]
        [-v|--verbosity <level>]
        [--version]
        <inputDir> <outputDir>


Arguments
~~~~~~~~~

.. code::

    [-h] [--help]
    If specified, show help message and exit.
    
    [--json]
    If specified, show json representation of app and exit.
    
    [--man]
    If specified, print (this) man page and exit.

    [--meta]
    If specified, print plugin meta data and exit.
    
    [--savejson <DIR>] 
    If specified, save json representation file to DIR and exit. 
    
    [-v <level>] [--verbosity <level>]
    Verbosity level for app. Not used currently.
    
    [--version]
    If specified, print version number and exit. 


Development
-----------

Build the Docker container:

.. code:: bash

    docker build -t mgz2labels .


Python dependencies can be added to ``setup.py``.
After a successful build, track which dependencies you have installed by
generating the `requirements.txt` file.

.. code:: bash

    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing                              \
        mgz2labels mgz2labels.py                                    \
        /incoming /outgoing

Examples
--------

.. code:: bash

    docker build -t mgz2labels .

.. code:: bash

    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing                              \
        mgz2labels mgz2labels.py                                    \
        /incoming /outgoing

