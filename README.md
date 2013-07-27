# MDM HTML Project Template

A starter template for creating beautiful themes for Linux Mint's login screen
[MDM](http://linuxmint.com/rel_olivia_whatsnew.php#mdm)

Features include Bootstrap LESS for greater customizability, plus a Makefile
to make project tasks like running the emulator and installing your theme
super simple.

## Getting Started

You probably want to download this template as a zipfile or tarball, since
you'll want to create a new Git repository for your theme. Extract the project
archive to the directory of your choice, and open a terminal in that directory.

In your terminal, run:

    ./configure


The configure script will ask you for a project name and a short description:

    $ ./configure
    What is the theme name? My Theme
    Enter a short theme description: The best MDM theme ever!


The configure script will generate a Makefile customized for your theme. It also
generates the ``theme.info`` file which contains metadata used by MDM:

    [Theme]
    Encoding=UTF-8
    Name=My Theme
    Description=The best MDM theme ever!
    Screenshot=screen.jpg


If you don't have them already, you'll need to install some dependencies for
working with LESS:

1. [Node.js](http://nodejs.org), for ``npm``
2. The LESS compiler: ``npm install -g less``
3. The watchr gem: ``gem install watchr``

## Start Hacking!

Your theme files are in the ``src`` directory. Edit these to your heart's content.

To see your changes, you need to run the MDM Theme Emulator. Simply:

    make emulator

and the MDM Theme Emulator will start with your theme already loaded.


## Working with LESS

This theme template is configured to use LESS, which is a powerful CSS
pre-processor which Bootstrap is built with.

Your custom styles should go in ``less/theme.less``. You can also edit ``less/variables.less``,
which is the Bootstrap LESS variables file. It's well documented, and offers
a great deal of styling flexibility without having to write your own style rules.

To compile LESS to CSS, you have two choices:

    make

Will run the less compiler as a one-shot operation, or

    make watch


will watch the ``less`` folder, and automatically run the compiler as you make
changes.


## Installing Your Theme

Installation is simple - just run:

    make install

And your theme will be installed to ``/usr/share/mdm/html-themes/``


## Distributing Your Theme

Your ``src`` file is your theme, distribute as you like. You might opt to also
distribute your Makefile, which would allow users to use ``make install`` to
install the theme on their system.
