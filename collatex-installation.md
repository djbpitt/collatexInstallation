Using CollateX
==============

David J. Birnbaum (<djbpitt@gmail.com>), <http://www.obdurodon.org>  
Tara Andrews (<tla@mit.edu>), <http://www.dh.unibe.ch/en/andrews/>

Last revised: 2015-05-17

## Overview

This tutorial explains how to install Python, CollateX, and IPython notebook for use in our CollateX workshop at DH2015 (Sydney). Workshop participants should install the software prior to the workshop.

## Installation

To install CollateX, you need first to install Python 3 and then CollateX, along with some other programs, packages, and modules used by CollateX. Here’s how to do that in Mac OS X, Ubuntu Linux, and Microsoft Windows. The process described below will probably take between thirty minutes and an hour, depending on how familiar you are with installing programs on your system. The good news is that you only have to do the installation once, and launching CollateX after that will take almost no time. This tutorial assumes that you are running the latest version of Mac OS (10.10 Yosemite), Windows **[add versions]**, or Ubuntu Linux **[add versions]**. 

In all of the steps below, if you are prompted to enter your password (which will happen the first time you use a `sudo` command), you should do so.

### Installing Python

Your system may already have some version of Python installed, but for the workshop we recommend that you install and use the Anaconda Python distribution. CollateX will work with other distributions of Python 3, but the installation and configuration is more complicated, so for the workshop we are strongly recommending Anaconda. Installing Anaconda according to the instructions on their site should not interfere with other existing Python versions on your system.

For MacOS, Linux, and Windows, the Python installation instructions are the same: install Anaconda Python from <http://continuum.io/downloads.html>. Be sure to click on the link that says <q>I want Python 3.4</q> before you download. Do not use Python distributions other than Anaconda. If you are curious, there’s a useful Anaconda quick-start tutorial at <https://store.continuum.io/static/img/Anaconda-Quickstart.pdf>.

<!--

#### Installing Python on MacOS

Install Anaconda Python from <http://continuum.io/downloads.html>. Be sure to click on the link that says <q>I want Python 3.4</q> before you download. Do not use Python distributions other than Anaconda. If you are curious, there’s a useful Anaconda quick-start tutorial at <https://store.continuum.io/static/img/Anaconda-Quickstart.pdf>.

#### Installing Python on Ubuntu Linux

**[Replace all of the following with Anaconda instructions, and consolidate the MacOS, Linux, and Windows instructions into one?]**

The most recent Debian and Ubuntu releases have both Python 2.7 and Python 3 pre-installed, but typing

    python --version

at the command line will probably report version <q>2.7</q>. Type

    python3 --version

instead to check whether you also have Python 3 installed (and use the path `/usr/bin/python3` to point to the latest supported Python 3 version). If you need to install Python 3, you can do so by typing:

    sudo apt-get install python3

Alternatively, you can install Python 3 by using the [Synaptic Package Manager](https://apps.ubuntu.com/cat/applications/synaptic). Search for <q>python3</q> and *do not remove <q>python 2.7</q>*! In addition to python 3, select “python3-setuptools” for installation, which makes the command `easy_install3 pip` available.

Alternatively, the [PPA](https://launchpad.net/ubuntu/+ppas) [deadsnakes](https://launchpad.net/~fkrull/+archive/ubuntu/deadsnakes), maintained by Felix Krull, contains old and new Python versions. You can access it with:

    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:fkrull/deadsnakes
    sudo apt-get update
    sudo apt-get install python3.3

#### Installing Python on Microsoft Windows

Install Anaconda Python from <http://continuum.io/downloads.html>. Be sure to click on the link that says <q>I want Python 3.4</q> before you download. Do not use Python distributions other than Anaconda. If you are curious, there’s a useful Anaconda quick-start tutorial at <https://store.continuum.io/static/img/Anaconda-Quickstart.pdf>.

-->

### Installing CollateX

Once you have installed Python, you need to install CollateX, along with a few supporting files (*libraries*). Here is how to do that.

#### Installing CollateX on MacOS

Open a command line (terminal) as described above. The easiest way to install CollateX is with pip, a Python *package manager*. pip comes bundled with Anaconda, so you don’t have to install it separately, and you can install CollateX and the programs on which it depends by typing:

    sudo pip install --pre collatex 
    sudo pip install python-levenshtein

#### Installing CollateX on Ubuntu Linux

The easiest way to install CollateX is with pip, a Python *package manager*. To test whether pip is available, type:

    pip --version
    
If you get an error message, or if the version reported is 2, rather than 3, you need to install pip, which you can do by typing:

    sudo easy_install3 pip

If the system prompts you for your password after this (or any other) `sudo` command, provide it. If you still get an error message, you need to install easy_install3 in order to install pip in order to install other programs (sigh). Try:

    sudo apt-get install python3-setuptools
    sudo easy_install3 pip

Once you have pip installed, type:

    sudo pip install --pre collatex 
    sudo pip install python-levenshtein

#### Installing CollateX on Microsoft Windows

The installation of CollateX itself is the same for all versions of Microsoft Windows, but you need to know whether you are running 32-bit Windows (win32) or 64-bit Windows (win-amd64) in order to install the Python Levenshtein library, which is required by CollateX. If you don’t know which version of Windows you are running, you can find out by clicking on the start button, then Control panel, and then System. In the section of the display labeled <q>System</q>, it will specify whether the system is 32-bit (win32) or 64-bit (win-amd64).

Installing CollateX on Windows requires the following steps:

* install CollateX 
* install the Python Levenshtein library

Here’s how to do that:

##### Installing CollateX on Microsoft Windows

Open a command shell. You can do that by clicking on the Start button in the lower left of your screen and then typing <q>powershell</q> in the search box labeled <q>Search programs and files</q> (Windows 7) or the general search box (Windows 8). Windows will find the the command-line interface program (displayed as <q>Windows PowerShell</q>) and invite you to click to launch it, which you should do. A window will open that displays a command line, a place where you can type instructions to be executed on the computer.

At the command line type:

    pip install --pre collatex

##### Installing the Python Levenshtein library on Microsoft Windows

Navigate to <http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-levenshtein> and download and run the installer that corresponds to your version of Windows and Python. Your version of Python will probably be 3.4; you can check whether you are running win-amd64 or win32 as described above.

### Installing graphviz

graphviz is a program for creating graphic representations, including the *variant graphs* sometimes used in CollateX (see the examples at <http://stemmaweb.net/stemmaweb/relation/help/Latin>). graphviz is required by CollateX only for viewing variant graphs. We recommend installing it for the workshop, but you can perform collations without it.

#### Installing graphviz on MacOS

The easiest way to install graphviz on MacOS is by downloading a dmg file from <http://www.ryandesign.com/graphviz/>. Choose the most recent stable version for your Mac hardware. You probably have an Intel machine, but you can verify by clicking on the little apple in the upper left corner of your screen and selecting <q>About this Mac</q>.

As an alternative to the dmg, you can install graphviz using *ports*. If you already have ports installed, you can type just:

    port install graphviz

If you don’t have ports installed, you’ll need to install it, and it requires the installation of Apple’s Xcode and the Xcode Command Line Tools first. Instructions and download links for these resources are at <https://www.macports.org/install.php>. 

In addition to graphviz itself, you also need to install Python support for graphviz, which you can do with:

    sudo pip install graphviz

#### Installing graphviz on Ubuntu Linux

**[Add instructions for installing graphviz on Ubuntu Linux]**

In addition to graphviz itself, you also need to install Python support for graphviz, which you can do with:

    sudo pip install graphviz

#### Installing graphvix on Microsoft Windows

**[Add instructions for installing graphviz on Microsoft Windows]**

## Environments

**[Add information about the file system needed to know where project files
are located.]**

### IPython notebook

We will use the IPython notebook development environment in our workshop to write and test CollateX collations. You should install IPython notebook in advance, and at the workshop we’ll describe how to use it to work with CollateX.

<!-- If IPython notebook works okay out of Ubuntu with the Anaconda launcher, we can cut the line above about installing IPython and unify the instructions for launching it to include Linux with the other two operating systems. -->

#### Starting IPython notebook on MacOS and Microsoft Windows

IPython notebook is bundled with Anaconda Python, so no separate installation is required. To launch IPython notebook in MacOS, open the Finder and navigate to the *anaconda* folder under your main user folder and double-click on Launcher.app. (If your main user folder isn’t visible in the Finder, you can get there by typing Shift-Command-H in an open Finder window.) In Microsoft Windows you can start the Launcher from your regular Start menu. You can then start IPython notebook from the Launcher. 

#### Installing and starting IPython notebook on Ubuntu Linux

**[Add instructions for installing and launching IPython notebook on Linux.]**

#### Using IPython notebook

We’ll describe how to use IPython notebook in the workshop, but if you already know a bit of Python, you can type Python commands into an empty cell and click the Run button (right-pointing triangle in the menu bar) or type Shift-Enter. The results of running your program will appear immediately below your code. For example, type the following into a cell in IPython notebook:

    from collatex import *
    collation = Collation()
    collation.add_plain_witness("A", "The quick brown fox jumps over the dog.")
    collation.add_plain_witness("B", "The brown fox jumps over the lazy dog.")
    alignment_table = collate(collation)
    print(alignment_table)

and click the Run button to show the results.

### Command line

We typically use IPython notebook for development and the command line in production, and we’ll explain how to use CollateX from the command line in the workshop. If you are already familiar with working on the command line (sometimes called a *terminal* window), you can save your Python code in a file (give it the traditional Python filename extension <q>.py</q>) and run it from the directory in which you’ve saved it with:

    python3 nameofscript.py


