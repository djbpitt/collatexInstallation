Using CollateX
==============

David J. Birnbaum (djbpitt@gmail.com), http://www.obdurodon.org

Last revised: 2014-10-04

Installation
------------

To install CollateX, you first need to install Python 3 and then CollateX.
Here’s how to do that in Mac OS X, Ubuntu Linux, and Microsoft Windows. The
process described below will probably take between twenty minutes and an
hour, depending on how familiar you are with installing programs on your
system. The good news is that you only have to do the installation once,
and launching CollateX after that will take almost no time.

### Installing Python

#### Installing Python on Mac OS X

Installation is run from the *command line*, also called the *terminal*.
Launch this by opening the Finder, selecting Applications, then Utilities,
and then Terminal. A window will open that displays a command line, a place
where you can type instructions to be executed on the computer.

At the time of writing, Mac OS X normally comes with Python 2.7 (core
language and utilities) installed. You can check this by typing

    python --version

at the command line. If what you see begins “Python 2.7” (there may be a
dot and another number after it), then you will need to install Python 3 as
well. This will not affect your existing Python or anything that uses it.

To install Python 3 on MacOS, select the 'Latest Python 3 Release' link at
<https://www.python.org/download/mac>.

#### Installing Python on Ubuntu Linux

Debian and Ubuntu last releases have both Python 2.7 and Python 3
pre-installed, but typing

    python --version

at the command line will probably report version “2.7”. Type

    python3 --version

instead (and use the path `/usr/bin/python3` to point to the latest
supported Python 3 version). If you need to install Python 3, you can do so
by typing:

    sudo apt-get install python3

Alternatively, you can install Python 3 by using the [Synaptic Package
Manager](https://apps.ubuntu.com/cat/applications/synaptic). Search for
“python3” and *do not remove “python 2.7”*! In addition to python 3, select
“python3-setuptools” for installation, which makes the command
`easy_install3 pip` available.

Alternatively, the [PPA](https://launchpad.net/ubuntu/+ppas)
[deadsnakes](https://launchpad.net/~fkrull/+archive/ubuntu/deadsnakes),
maintained by Felix Krull, contains old and new Python versions. You can
access it with:

    sudo apt-get install python-software-properties
    sudo add-apt-repository ppa:fkrull/deadsnakes
    sudo apt-get update
    sudo apt-get install python3.3

#### Installing Python on Microsoft Windows

Install Anaconda Python from <http://continuum.io/downloads.html>. Be sure
to click on the link that says "I want Python 3.4" before you download. Do
not use Python distributions other than Anaconda.

### Installing CollateX

Once you have installed Python, you need to install CollateX, along with a
few supporting files (*libraries*). Here is how to do that.

#### Installing CollateX on MacOS

Open a command line (terminal) as described above. The easiest way to
install CollateX is with pip, a Python *package manager*. First verify that
you have pip installed by typing:

    pip --version

If you see something that looks vaguely like “pip 6.0.8 from
/Library/Frameworks/Python.framework/Versions/3.4/lib/python3.4/site-
packages (python 3.4)”, you have pip installed and can proceed to
installing CollateX. If you get an error message that indicates that pip is
not installed, install it by typing:

    TODO fill this in

The system may prompt you to enter your password, which you should do if
asked. Then check that the installation has worked by typing the command
above to check the version.

Once you have pip installed, you can install CollateX and the programs on
which it depends by typing:

    sudo pip3 install --pre collatex 
    sudo pip3 install python-levenshtein

As above, if the system prompts you for your password, provide it.

#### Installing CollateX on Ubuntu Linux

Type:

    sudo easy_install3 pip

If you get an error message, try:

    sudo apt-get install python3-setuptools
    sudo easy_install3 pip

#### Installing CollateX on Microsoft Windows

You need to know whether you are running 32-bit Windows (win32) or 64-bit
Windows (win-amd64). If you don’t know, you can find out by clicking on the
start button, then Control panel, and then System. In the section of the
display labeled “System”, it will specify whether the system is 32-bit
(win32) or 64-bit (win-amd64).

Installing CollateX on Windows requires the following steps:

* install CollateX 
* install the Python Levenshtein library. 

Here’s how to do that:

##### Installing CollateX on Windows

Open a command shell. You can do that by clicking on the Start button in
the lower left of your screen and then typing “powershell” in the search
box labeled “Search programs and files” (Windows 7) or the general search
box (Windows 8). Windows will find the the command-line interface program
(displayed as “Windows PowerShell”) and invite you to click to launch it,
which you should do. A window will open that displays a command line, a
place where you can type instructions to be executed on the computer.

At the command line type:

    pip install --pre collatex

##### Installing the Python Levenshtein library on Windows

Navigate to <http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-levenshtein>
and download and run the installer that corresponds to your version of
Windows and Python. Your version of Python will probably be 3.4; you can
check whether you are running win-amd64 or win32 as described above.

Environments
------------

Add information about the file system needed to know where project files
are located.

### iPython

Add instructions for installing and launching iPython and sample from
https://pypi.python.org/pypi/collatex.

### Command line

Add instructions for running sample from
https://pypi.python.org/pypi/collatex.

Special issues
--------------

### Unicode

Prepend the following to your file:

    # This Python file uses the following encoding: utf-8

Decide what to do (for now) about Unicode problems with the current
release.
