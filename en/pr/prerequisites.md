# Prerequisites

## Install Python 3

In 2008, a change in the history of Python and programming took place : Python 3.0.0 was released.

Be aware that in this version, many things have changed, which means that a fairly substantial program for Python 2 requires modifications to make it work under Python 3 and that some libraries will not be available on either of the two.

Download the latest version (not the development version) adapted to your operating system from the official website : [https://www.python.org/downloads/](https://www.python.org/downloads/).&#x20;

Then, follow the instructions of the installer or the website. To verify that Python 3 is installed, open the terminal (see [#open-a-command-line](prerequisites.md#open-a-command-line "mention")) and type the command :

```bash
python3 --version
```

This should show your current version.

## Install a code editor

A code editor is a text editor that displays in a fixed-size font and provides syntax highlighting.

One of the most popular is Visual Studio Code. It has many features, a user-friendly interface, and many extensions to suit your needs. It is available on Windows, MacOS, and Linux.

You can download it from the official website : [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

You also have other options like :&#x20;

* Notepad++ (Windows only and simpler) : [https://notepad-plus-plus.org/downloads/](https://notepad-plus-plus.org/downloads/)
* Phoenix Code (multiplatform with a clean interface) : [https://phcode.io/#/home](https://phcode.io/#/home)

## Configure a `venv`

A `venv` is a lightweight virtual environment with its own directory. Each virtual environment has its own Python binary and can have its own list of installed Python packages.

This is useful when we want to isolate our programs so as not to interfere with the system and for better compatibility.

To create one, follow the instructions in the Python documentation : [Creating `venv`](https://docs.python.org/3/library/venv.html#creating-virtual-environments).

## Open a command line

The terminal (also called command line) is a software that allows you to interact directly with the operating system or applications via text commands.

{% tabs %}
{% tab title="Windows" %}
1. Click the Windows button to open the search bar.
2. Type `cmd.exe` and press Enter.
3. Click `cmd.exe` (probably the first result).
{% endtab %}

{% tab title="MacOS" %}
Open Launchpad or go to the Applications folder. Then, search for and open Terminal.
{% endtab %}

{% tab title="Linux" %}
You can try Ctrl + Alt + T which should work for you. Otherwise, use the usual way to open an application and then open the terminal (may be called differently depending on your distribution).
{% endtab %}
{% endtabs %}

## Run a Python program

To execute code in Python, there are many ways. I will present 4 of them with their advantages, disadvantages and of course how to apply them.

### Integrated Python's CLI

Open a terminal and enter the following command :

```bash
python3
```

Then you will be able to type Python code that will execute as you type lines.

This will allow you to quickly experiment with commands and understand some concepts but be aware that, this way, you will not be able to save your programs and some features will remain inaccessible to you.

### Python as file

First, you save your program in a file like `script.py`.

Then, you will open the terminal and enter the following command replacing with your file name :

```bash
python3 /path/to/directory/script.py
```

Your program will then run in the terminal unless it is designed to have a GUI (graphical user interface) and in this case, a window will open.

This is the most used method during the development of a program.

### Via the code editor

If you use a code editor like IDLE or VS Code, you may have a feature that allows you to run the script directly, probably accessible via a keyboard shortcut or right-click. It's up to you to check.

### Open an executable created with PyInstaller

Often, to distribute a Python program intended for an audience not very computer-literate, it is packaged as an executable. One of the most famous tools allowing this is [PyInstaller](https://pyinstaller.org/en/stable/).

I will not explain here how to create an executable from Python scripts (you can find information on this in their [documentation](https://pyinstaller.org/en/stable/)).

Once the executable is ready, you simply have to open it like any other application on the appropriate operating system.

## Use `pip`

`pip` is the Python package installer. These packages can contain libraries of functions and other data.

It should have been installed on your computer if you did a standard Python installation. To check this, type in the terminal :

```bash
pip --version
```

Cela devrait vous retourner un numéro de version. Si ce n'est pas le cas, effectuez un réinstallation de Python ([#install-python-3](prerequisites.md#install-python-3 "mention")).

Maintenant, vous devriez être en mesure d'installer des modules depuis `pip`. Essayez en entrant la commande suivante :clap:

This should return a version number. If not, do a reinstall of Python ([#install-python-3](prerequisites.md#install-python-3 "mention")).

Now you should be able to install modules from `pip`. Try this by entering the following command :

```bash
pip install markdown
```

To update `pip`, run the command :

```bash
pip install --upgrade pip
```

To learn additional useful commands, enter :

```bash
pip -h
```

You should get an organized list.
