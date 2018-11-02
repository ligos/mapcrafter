============
Blockcrafter
============

`Blockcrafter <https://github.com/mapcrafter/blockcrafter>`_ is the tool 
used to create the block sprite image files Mapcrafter uses to create your 
maps based on Minecraft assets. 

Mapcrafter already contains block sprites for ``texture_size`` 12 and 16, all
``render_views`` (isometric, topdown, side), and all ``rotations`` (top-left, 
top-right, bottom-right, bottom-left).

You only need Blockcrafter:

* To use a ``texture_size`` other than 12 or 16.
* To render a map which uses a custom Minecraft resource pack.


Installing and Using Blockcrafter
=================================

Blockcrafter is a `Python 3 <https://www.python.org/>`_ app, which uses 
`VisPy <http://vispy.org>`_ to render images. You'll need to use `Docker 
<https://www.docker.com/>`_ images, or build from source, to use Blockcrafter.

Remember to use **Python 3** not **Python 2**, and to install a `VisPy Backend 
<http://vispy.org/installation.html>`_ package (Qt5 is recommended in the 
instructions below).

Docker
------

TODO - Murray has no experience with docker.


Debian / Ubuntu
---------------

.. code-block:: shell

    $ sudo apt install git python3 python3-pip3
    $ git clone https://github.com/mapcrafter/blockcrafter.git /home/user/blockcrafter
    $ cd /home/user/blockcrafter
    $ pip3 install .
    $ sudo pip3 install PyQt5
    $ mapcrafter-export 
        -a /home/user/.minecraft/versions/1.13.2.jar 
        -o /home/user/blocks 
        -v isometric 
        -t 8

CentOS / Fedora / RedHat
------------------------

TODO

Windows
-------

Download and install the latest version of `Python3 for Windows 
<https://www.python.org/downloads/windows/>`_. Version 3.7.1 has been tested OK.
Python 3.4+ is highly recommended (as it contains `pip <https://pip.pypa.io/en/stable/>`_).

Download or clone the latest version of `Blockcrafter from Github <https://github.com/ligos/blockcrafter>`_
to a folder of your choice (eg: ``C:\Users\username\source\Blockcrafter``).

Open a powershell console in the folder you just created.

.. code-block:: shell

    PS> py -m pip install .
    PS> py -m pip install PyQt5 --user
    PS> blockcrafter-export 
        -a C:\Users\username\AppData\Roaming\.minecraft\versions\1.13.2\1.13.2.jar 
        -o blocks 
        -v isometric 
        -t 8


Installing Block Sprite files
=============================

Once BlockCrafter has created your new block sprite files, you simply copy
them into the Mapcrafter *block directory*, or specify a custom ``block_dir``
for your map.

See ``--find-resources`` in :ref:`command_line_options`, and ``block_dir`` 
and ``texture_size`` in :doc:`configuration` for further details.