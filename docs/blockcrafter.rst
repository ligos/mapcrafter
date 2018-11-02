=======
Blockcrafter
=======

`Blockcrafter <https://github.com/mapcrafter/blockcrafter>`_ is the tool 
used to create the spritemaps Mapcrafter uses to create your maps based 
on Minecraft assets. You only need Blockcrafter:

* To use a ``texture_size`` other than 12 or 16.
* To render a map which uses a custom Minecraft resource pack.


If you use the 
``--find-resources`` command line option, you can find the Mapcrafter
spritemaps, which are large PNG files and text files. ``Block directories``
is the one you're interested in. ::

.. code-block::
    $ mapcrafter --find-resources
    Your home directory: /home/msn
Mapcrafter binary: /mnt/c/Users/msn/source/mapcrafter/src/mapcrafter
Resource directories:
  1. /mnt/c/Users/msn/source/mapcrafter/src/data
Template directories:
  1. /mnt/c/Users/msn/source/mapcrafter/src/data/template
Block directories:
  1. /mnt/c/Users/msn/source/mapcrafter/src/data/blocks
Logging configuration file:
  1. /mnt/c/Users/msn/source/mapcrafter/src/logging.conf

See also ``block_dir`` and ``texture_size`` in :ref:Configuration.


Installing and Using Blockcrafter
=================================

Docker
------

TODO - Murray has no experience with docker.


Debian / Ubuntu
---------------

$ sudo apt install git python3 python3-pip3

$ git clone https://github.com/mapcrafter/blockcrafter.git /home/user/blockcrafter

$ cd /home/user/blockcrafter

$ pip3 install .

$ sudo pip3 install PyQt5

$ mapcrafter-export -a /home/user/.minecraft/versions/1.13.2.jar -o /home/user/blocks -v isometric -t 8

Windows
-------

Download and install the latest version of `Python3 for Windows 
<https://www.python.org/downloads/windows/>`_. Version 3.7.1 has been tested OK.
Python 3.4+ is highly recommended (as it contains `pip <https://pip.pypa.io/en/stable/>`_).

Download or clone the latest version of `Blockcrafter from Github <https://github.com/ligos/blockcrafter>`_
(eg: ``C:\Users\username\source\Blockcrafter``).

Open a powershell console in the folder you just created.

PS> py -m pip install .

PS> py -m pip install PyQt5 --user

PS> blockcrafter-export 
        -a C:\Users\username\AppData\Roaming\.minecraft\versions\1.13.2\1.13.2.jar 
        -o blocks 
        -v isometric 
        -t 8

