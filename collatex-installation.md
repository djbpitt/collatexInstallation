Using CollateX
==============

David J. Birnbaum (<djbpitt@gmail.com>), <http://www.obdurodon.org>  
Tara Andrews (<tla@mit.edu>), <http://byzantini.st/>

Last revised: 2015-05-17

## Overview

This tutorial explains how to install Python, CollateX, and IPython notebook for use in our CollateX workshop at DH2015 (Sydney). Workshop participants should install the software prior to the workshop.

## The short form

If you regularly use Python and other software, here are the instructions in a nutshell:

* Ensure Python 3, preferably the [Anaconda](http://continuum.io/downloads.html) distribution
* Install Graphviz (either through a package manager such as apt-get or MacPorts, 
  or go to <http://www.graphviz.org/Download.php> and accept the license)
* `pip install --pre collatex`
* `pip install python-levenshtein`
* `pip install graphviz`


If you are not sure what all that means, read on!

## Installation

To install CollateX, you need first to install Python 3 and then CollateX, along with some other programs, packages, and modules used by CollateX. Here’s how to do that in Mac OS X, Ubuntu Linux, and Microsoft Windows. The process described below will probably take between thirty minutes and an hour, depending on how familiar you are with installing programs on your system. The good news is that you only have to do the installation once, and launching CollateX after that will take almost no time. This tutorial assumes that you are running Mac OS X 10.8 or later, Windows 7 or 8, or Ubuntu Linux 14.04 LTS or later. 

In all of the steps below, if you are prompted to enter your password (which will happen the first time you use a `sudo` command), you should do so.

### Installing Python

Your system may already have some version of Python installed, but we recommend that you install and use the Anaconda Python distribution. CollateX will work with other distributions of Python 3, but the installation and configuration is more complicated, so for the workshop we are using Anaconda. Installing Anaconda according to the instructions on their site should not interfere with other existing Python versions on your system.

For MacOS, Linux, and Windows, the Python installation instructions are the same: install Anaconda Python from <http://continuum.io/downloads.html>. **Be sure to click on the link that says <q>I want Python 3.4</q> before you download**. If you are curious, there’s a useful Anaconda quick-start tutorial at <https://store.continuum.io/static/img/Anaconda-Quickstart.pdf>.

#### Extra instructions for Linux users

The Anaconda package installer on Linux is not a clickable installation program as on Mac and Windows. You will need to choose to save the file, and then make a note of where the installer was saved (most likely your Downloads folder). You will then open a command line window (ctrl-alt-T on Ubuntu - also see below) to type the command

	bash Downloads/Anaconda3-2.2.0-Linux-x86_64.sh
	
(where `Downloads` is replaced with the name of the folder in which you saved Anaconda, if it is different.)

When asked, say 'yes' to everything. When the installation is finished, type

	exit
	
to close the command line window. (You need to do this, even though you will open a new one below!)

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

### Opening a command line window

Once you have installed Python, you need to install CollateX, along with a few supporting files (*libraries*). To do this, you will need to work with a command line window. The ones we recommend are:

* For Mac OS X: the Terminal.app that you will find in the Applications -> Utilities folder.
* For Windows: Windows Powershell, which you can find from the search box.
* For Ubuntu Desktop (Unity): you can type Ctrl-Alt-T or you can type 'Terminal' into the Search box.

A window will open that displays a command line, a place where you can type instructions to be executed on the computer, with a prompt that might look something like this:

	Taras-Mac:~ tara$ 
	
or this:

	PS C:\Users\Tara L Andrews> 
	
or this:

	tla@ubuntu:~$ 

Now you are ready to type the commands that come next.

***N.B. for Windows users**:  Some of you may have used `cmd.exe` in the past, to work at the command line. We recommend Powershell because it uses many of the same commands that have always been in use on Unix-like systems, and so makes it easier for you to follow generic command-line instructions such as those we will be giving in the workshop. If you stick to cmd.exe you do so at your own risk.*

### Installing CollateX

Once you have found your command line, as described above, you are ready to install CollateX. The easiest way to do this is with `pip`, a Python *package manager*. pip comes bundled with Anaconda, so you don’t have to install it separately, and you can install CollateX and the libraries on which it depends by typing:

    pip install --pre collatex 
    

### Installing the Python Levenshtein library

CollateX relies on this library to do inexact matching of words. The installation procedure is the same for all platforms: type the following at the command line.

    pip install python-levenshtein
    
***N.B. for Mac users:** You may get a popup window telling you that you require the command-line developer tools. If you get this window, choose 'Install'. When the installation is finished, run the command again.*
    
<!--

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

-->

### Installing Graphviz

Graphviz is a program for creating graphic representations, including the *variant graphs* sometimes used in CollateX (see the examples at <http://stemmaweb.net/stemmaweb/relation/help/Latin>). Graphviz is required by CollateX only for viewing variant graphs. We recommend installing it for the workshop, but you can perform collations without it.

#### Installing Graphviz on Windows

The easiest way to install Graphviz is to download the appropriate installer from [the Graphviz download page](http://www.graphviz.org/Download.php) (you will need to accept the license.) On Windows, use the .msi file.

Next, you will need to add Graphviz to the execution path.

#### Installing Graphviz on Mac OS X

The easiest way to install Graphviz is to download the appropriate installer from [the Graphviz download page](http://www.graphviz.org/Download.php) (you will need to accept the license.) On Mac, this will be the 'mountainlion' installer.

If the installer refuses to run when you double-click it, then you can do the following.

* Navigate to the installer in your Downloads folder.
* Right-click (or ctrl-click) to bring up the context menu.
* Choose *Open*. 
* When the warning dialog appears, choose *Open* again.

This is a useful trick to remember for installing any software that you know you want, but that your Mac doesn't trust.


<!-- Commenting out the MacPorts instructions, as then you have to set compiler options to tell Anaconda pip where to find the header files.!

As an alternative to the dmg installer on the Mac, you can install Graphviz using *ports*. If you already have ports installed, you can run the command:

    sudo port install graphviz

If you don’t have ports installed, you’ll need to install it, and it requires the installation of Apple’s Xcode and the Xcode Command Line Tools first. Instructions and download links for these resources are at <https://www.macports.org/install.php>. -->

#### Installing Graphviz on Ubuntu Linux

Graphviz can be installed from the Terminal on Ubuntu with the command:

	sudo apt-get install graphviz graphviz-dev

### Installing the Graphviz library for Python

In addition to graphviz itself, you also need to install Python support for graphviz, which you can do with the following command typed at the command line.

    pip install graphviz



## Environments

**[Add information about the file system needed to know where project files
are located.]**

### IPython notebook

We will use the IPython notebook development environment in our workshop to write and test CollateX collations. You should install IPython notebook in advance, and at the workshop we’ll describe how to use it to work with CollateX.

<!-- If IPython notebook works okay out of Ubuntu with the Anaconda launcher, we can cut the line above about installing IPython and unify the instructions for launching it to include Linux with the other two operating systems. -->

#### Starting IPython notebook

IPython notebook is bundled with Anaconda Python, so no separate installation is required. To launch it, at your command line type

	ipython notebook
	
and wait for a window to open in your Web browser.

<!-- [The following has the problem that most of them won't have a way to the their main user folder in the Finder. Thanks Apple. We can just have them start it from the command line, as long as they are there anyway.]

To launch IPython notebook in MacOS, open the Finder and navigate to the *anaconda* folder under your main user folder and double-click on Launcher.app. (If your main user folder isn’t visible in the Finder, you can get there by typing Shift-Command-H in an open Finder window.) In Microsoft Windows you can start the Launcher from your regular Start menu. You can then start IPython notebook from the Launcher. -->

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

We typically use IPython notebook for experimentation and the command line for finished Python programs, and we’ll explain how to use CollateX from the command line in the workshop. If you are already familiar with working on the command line, you can save your Python code in a file (give it the traditional Python filename extension <q>.py</q>) and run it from the directory in which you’ve saved it with:

    python nameofscript.py


