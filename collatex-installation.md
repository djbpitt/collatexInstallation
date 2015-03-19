Using CollateX
==============

David J. Birnbaum (djbpitt@gmail.com), http://www.obdurodon.org

Last revised: 2014-10-04

Installation
------------

To install CollateX, you first need to install Python 2.7 and then
CollateX. Here’s how to do that in MacOS and Microsoft Windows. The
process described below will probably take between twenty minutes and an
hour, depending on how familiar you are with installing programs on your
system. The good news is that you only have to do the installation once,
and launching CollateX after that will take almost no time.

### Installing Python

#### Installing Python on MacOS

Installation is run from the *command line*, also called the *terminal*.
Launch this by opening the Finder, selecting Applications, then
Utilities, and then Terminal. A window will open that displays a command
line, a place where you can type instructions to be executed on the
computer.

MacOS should come with Python 2.7 (core language and utilities)
installed. You can check this by typing

    python --version

at the command line. If what you see begins “Python 2.7” (there may be a
dot and another number after it), all is well. If the Python version
number begins with a 3, it won’t work properly with CollateX, and you’ll
need to install version 2 of Python, which you can do alongside (that
is, without overwriting) version 3. To install Python on MacOS, follow
the instructions at <https://www.python.org/download/mac>.

#### Installing Python on Ubuntu Linux

Debian and Ubuntu last releases have both Python 2.7 and Python 3
pre-installed, but typing

    python --version

at the command line will probably report version “2.7”. Type

    python3 --version

instead (and use the path `/usr/bin/python3` to point to the latest
supported Python 3 version). If you need to install Python 3, you can do
so by typing:

    sudo apt-get install python3

Alternatively, you can install Python 3 by using the [Synaptic Package
Manager](https://apps.ubuntu.com/cat/applications/synaptic). Search for
“python3” and *do not desinstall “python 2.7”*! In addition to Python 3,
select “python3-setuptools” for installation, which makes the command
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

Install Anaconda Python from <http://docs.continuum.io/anaconda/>. Be
sure to install version 2.7 (which is the default); CollateX does not
work with version 3 of Python. Do not use Python distributions other
than Anaconda.

### Installing CollateX

Once you have installed Python, you need to install CollateX, along with
a few supporting files (*libraries*). Here is how to do that.

#### Installing CollateX on MacOS

Open a command line (terminaL) as described above. The easiest way to
install CollateX is with pip, a Python *package manager*. First verify
that you have pip installed by typing:

    pip --version

If you see something that looks vaguely like “pip 1.5.2 from
/Library/Python/2.7/site-packages/pip-1.5.2-py2.7.egg (python 2.7)”, you
have pip installed and can proceed to installing CollateX. If you get an
error message that indicates that pip is not installed, install it by
typing:

The system may prompt you to enter your password, which you should do if
asked. Then verify that the installation has worked by typing the
command above to check the version.

Once you have pip installed, you can install CollateX and the programs
on which it depends by typing:

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

You need to know whether you are running 32-bit Windows (win32) or
64-bit Windows (win-amd64). If you don’t know, you can find out by
clicking on the start button, then Control panel, and then System. In
the section of the display labeled “System”, it will specify whether the
system is 32-bit (win32) or 64-bit (win-amd64).

Open a command line or terminal. You can do that by clicking on the
Start button in the lower left of your screen and then typing “cmd” in
the search box labeled “Search programs and files” (Windows 7) or the
general search box (Windows 8). Windows will find the the command-line
interface program (displayed as “cmd” or “cmd.exe”) and invite you to
click to launch it, which you should do. A window will open that
displays a command line, a place where you can type instructions to be
executed on the computer.

Installing CollateX on Windows requires the following step *in order*:
install PyGraphviz, install CollateX, and then install the Python
Levenshtein library. Here’s how to do that:

##### Installing PyGraphviz on Windows

To install PyGraphviz on Windows, first install Graphviz from
<http://www.graphviz.org/Download_windows.php> (choose the current
stable release in the msi file format; there is no difference between
win32 and win-amd64 for Graphviz). You now need to add the path to the
Graphviz dot.exe program to your Windows path, which means first finding
where dot.exe has been installed. Your dot.exe program is probably
located in C:\\Program Files\\Graphviz2.38\\bin (if you have 32-bit
Windows) or C:\\Program Files (x86)\\Graphviz2.38\\bin (for 64-bit
Windows), and you check by **ADD PROCEDURE**. Once you know the
location, add it to the end of the path variable by following the
instructions at <http://www.computerhope.com/issues/ch000549.htm>. You
want to add the path to the Graphviz bin directory at the end of your
path; for the 64-bit example above, that means adding the following text
at the end of the current path variable value: “;C:\\Program
Files\\Graphviz2.38\\bin” (do not include “dot.exe” in the path; the
path should end with “bin”).

Once you’ve installed Graphviz and added dot.exe to your path, you
should download PyGraphviz from
<http://www.lfd.uci.edu/~gohlke/pythonlibs/#pygraphviz>, selecting the
one that fits your version of Python (probably 2.7) and Windows (win32
or win-amd64). Run the program to install it.

##### Installing CollateX on Windows

At the command line type:

    pip install --pre collatex

##### Installing the Python Levenshtein library on Windows

Navigate to
<http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-levenshtein> and
download and run the installer that corresponds to your version of
Windows and Python. Your version of Python will probably be 2.7; you can
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
