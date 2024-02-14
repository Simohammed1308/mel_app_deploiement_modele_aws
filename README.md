Projet 8 : Déploiement dans le cloud : AWS
==========================================





# Installation



    $ cd $HOME  # or any other development directory you prefer
    $ git clone https://github.com/ageron/handson-ml.git
    $ cd handson-ml

## Python & Required Libraries
Of course, you obviously need Python. Python 2 is already preinstalled on most systems nowadays, and sometimes even Python 3. You can check which version(s) you have by typing the following commands:

    $ python --version   # for Python 2
    $ python3 --version  # for Python 3


    $ /Applications/Python\ 3.6/Install\ Certificates.command

On Linux, unless you know what you are doing, you should use your system's packaging system. For example, on Debian or Ubuntu, type:

    $ sudo apt-get update
    $ sudo apt-get install python3

Another option is to download and install [Anaconda](https://www.continuum.io/downloads). This is a package that includes both Python and many scientific libraries. You should prefer the Python 3 version.

If you choose to use Anaconda, read the next section, or else jump to the [Using pip](#using-pip) section.

## Using Anaconda
When using Anaconda, you can optionally create an isolated Python environment dedicated to this project. This is recommended as it makes it possible to have a different environment for each project (e.g. one for this project), with potentially different libraries and library versions:

    $ conda create -n mlbook python=3.5 anaconda
    $ conda activate mlbook

This creates a fresh Python 3.5 environment called `mlbook` (you can change the name if you want to), and it activates it. This environment contains all the scientific libraries that come with Anaconda. This includes all the libraries we will need (NumPy, Matplotlib, Pandas, Jupyter and a few others), except for TensorFlow, so let's install it:

    $ conda install -n mlbook -c conda-forge tensorflow

This installs the latest version of TensorFlow available for Anaconda (which is usually *not* the latest TensorFlow version) in the `mlbook` environment (fetching it from the `conda-forge` repository). If you chose not to create an `mlbook` environment, then just remove the `-n mlbook` option.

Next, you can optionally install Jupyter extensions. These are useful to have nice tables of contents in the notebooks, but they are not required.

    $ conda install -n mlbook -c conda-forge jupyter_contrib_nbextensions

You are all set! Next, jump to the [Starting Jupyter](#starting-jupyter) section.

## Using pip 
If you are not using Anaconda, you need to install several scientific Python libraries that are necessary for this project, in particular NumPy, Matplotlib, Pandas, Jupyter and TensorFlow (and a few others). For this, you can either use Python's integrated packaging system, pip, or you may prefer to use your system's own packaging system (if available, e.g. on Linux, or on MacOSX when using MacPorts or Homebrew). The advantage of using pip is that it is easy to create multiple isolated Python environments with different libraries and different library versions (e.g. one environment for each project). The advantage of using your system's packaging system is that there is less risk of having conflicts between your Python libraries and your system's other packages. Since I have many projects with different library requirements, I prefer to use pip with isolated environments. Moreover, the pip packages are usually the most recent ones available, while Anaconda and system packages often lag behind a bit.

These are the commands you need to type in a terminal if you want to use pip to install the required libraries. Note: in all the following commands, if you chose to use Python 2 rather than Python 3, you must replace `pip3` with `pip`, and `python3` with `python`.

First you need to make sure you have the latest version of pip installed:

    $ pip3 install --user --upgrade pip

The `--user` option will install the latest version of pip only for the current user. If you prefer to install it system wide (i.e. for all users), you must have administrator rights (e.g. use `sudo pip3` instead of `pip3` on Linux), and you should remove the `--user` option. The same is true of the command below that uses the `--user` option.

Next, you can optionally create an isolated environment. This is recommended as it makes it possible to have a different environment for each project (e.g. one for this project), with potentially very different libraries, and different versions:

    $ pip3 install --user --upgrade virtualenv
    $ virtualenv -p `which python3` env

This creates a new directory called `env` in the current directory, containing an isolated Python environment based on Python 3. If you installed multiple versions of Python 3 on your system, you can replace `` `which python3` `` with the path to the Python executable you prefer to use.

Now you must activate this environment. You will need to run this command every time you want to use this environment.

    $ source ./env/bin/activate

On Windows, the command is slightly different:

    $ .\env\Scripts\activate

Next, use pip to install the required python packages. If you are not using virtualenv, you should add the `--user` option (alternatively you could install the libraries system-wide, but this will probably require administrator rights, e.g. using `sudo pip3` instead of `pip3` on Linux).

    $ pip3 install --upgrade -r requirements.txt

Great! You're all set, you just need to start Jupyter now.

## Starting Jupyter
Okay! You can now start Jupyter, simply type:

    $ jupyter notebook

This should open up your browser, and you should see Jupyter's tree view, with the contents of the current directory. If your browser does not open automatically, visit [127.0.0.1:8888](http://127.0.0.1:8888/tree). Click on `index.ipynb` to get started!

Congrats! You are ready to learn Machine Learning, hands on!

# Contributors
I would like to thank everyone who contributed to this project, either by providing useful feedback, filing issues or submitting Pull Requests. Special thanks go to Steven Bunkley and Ziembla who created the `docker` directory.
