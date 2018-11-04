============
Blockcrafter
============

`Blockcrafter <https://github.com/mapcrafter/blockcrafter>`_ is the tool 
to create the block sprite image files Mapcrafter uses to create your 
maps. It reads from Minecraft assets (via the Minecraft client ``jar`` file, 
or custom texture packs) and uses OpenGL to render sprites for each Minecraft 
block. 

.. note::
    Mapcrafter already contains block sprites for ``texture_size`` 12 and 16, 
    all ``render_views`` (isometric, topdown, side), and all ``rotations`` 
    (top-left, top-right, bottom-right, bottom-left).

    You only need Blockcrafter:
        * To use a ``texture_size`` other than 12 or 16.
        * To render a map which uses a custom Minecraft resource pack.


Installing and Using Blockcrafter
=================================

Blockcrafter is a `Python 3 <https://www.python.org/>`_ app, which uses 
`VisPy <http://vispy.org>`_ to render images. To use it, you'll need:

* Either the `Docker <https://www.docker.com/>`_ images, OR build from source.
* Minecraft client ``jar`` file, which can usually be found in:
    * ``~/.minecraft/versions/<version>`` in Linux / MacOS.
    * ``%APPDATA%\.minecraft\versions\<version>`` in Windows.


Docker
------

TODO - Murray has no experience with docker.


Debian / Ubuntu
---------------

Note that Python 2 is installed by default on Ubuntu, but Blockcrafter requires Python 3:

.. code-block:: shell
    
    $ sudo apt install python3 python3-pip3

Then download / clone the Blockcrafter repository:

.. code-block:: shell
    
    $ sudo apt install git
    $ git clone https://github.com/mapcrafter/blockcrafter.git /home/user/blockcrafter

Compile and install Blockcrafter (downloading the modules it needs) via pip:

.. code-block:: shell
  
    $ cd /home/user/blockcrafter
    $ pip3 install .

Then install `Pyglet <https://pypi.org/project/pyglet/>`_ as a VisPy backend:

.. code-block:: shell
   
    $ sudo pip3 install Pyglet

And then you can run Blockcrafter! For example:

.. code-block:: shell
  
    $ mapcrafter-export 
        -a /home/user/.minecraft/versions/1.13.2.jar 
        -o /home/user/blocks 
        -v isometric 
        -t 8

You should see a blank window labelled "*VisPy canvas*" while Blockcrafter is rendering.

See the `Blockcrafter Github <https://github.com/mapcrafter/blockcrafter>`_ site for
further command line options.

CentOS / Fedora / RedHat
------------------------

.. note::
    NOTE: these instructions are based on the Debian ones, and running Fedora Workstation 28
    from a live CD image. There may be some inaccuracies.

Python 3 and git are installed on recent versions of Fedora Workstation. Remember that 
Blockcrafter is not compatible with Python 2. You can test by running ``python3 --version`` 
from a command prompt, or install like so:

.. code-block:: shell
    
    $ sudo yum install python3

Then download / clone the Blockcrafter repository:

.. code-block:: shell
    
    $ git clone https://github.com/mapcrafter/blockcrafter.git /home/user/blockcrafter

Compile and install Blockcrafter (downloading the modules it needs) via pip:

.. code-block:: shell
   
    $ cd /home/user/blockcrafter
    $ pip3 install .

Then install `Pyglet <https://pypi.org/project/pyglet/>`_ as a VisPy backend:

.. code-block:: shell

    $ sudo pip3 install Pyglet

And then you can run Blockcrafter! For example:

.. code-block:: shell

    $ mapcrafter-export 
        -a /home/user/.minecraft/versions/1.13.2.jar 
        -o /home/user/blocks 
        -v isometric 
        -t 8

You should see a blank window labelled "*VisPy canvas*" while Blockcrafter is rendering.

See the `Blockcrafter Github <https://github.com/mapcrafter/blockcrafter>`_ site for
further command line options.


Windows
-------

Download and install the latest version of `Python3 for Windows 
<https://www.python.org/downloads/windows/>`_. Version 3.7.1 has been tested OK.
Python 3.4+ is highly recommended (as it contains `pip <https://pip.pypa.io/en/stable/>`_).

Download or clone the latest version of `Blockcrafter from Github <https://github.com/ligos/blockcrafter>`_
to a folder of your choice (eg: ``C:\Users\username\source\Blockcrafter``).

Open a powershell console in the folder you just created to install Python modules:

.. code-block:: shell

    PS> py -m pip install .
    PS> py -m pip install Pyglet --user

And then you can run Blockcrafter! For example:

.. code-block:: shell

    PS> blockcrafter-export 
        -a C:\Users\username\AppData\Roaming\.minecraft\versions\1.13.2\1.13.2.jar 
        -o blocks 
        -v isometric 
        -t 8

You should see a blank window labelled "*VisPy canvas*" while Blockcrafter is rendering.
This will be marked as "*not responding*", but don't close it!

See the `Blockcrafter Github <https://github.com/mapcrafter/blockcrafter>`_ site for
further command line options.


Installing Block Sprite files
=============================

Once BlockCrafter has created your new block sprite files, you simply copy
them into the Mapcrafter *block directory*, or specify a custom ``block_dir``
for your map.

See ``--find-resources`` in :ref:`command_line_options`, and ``block_dir`` 
and ``texture_size`` in :doc:`configuration` for further details.