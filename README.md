# Python 0.9.1 (patched, QoL improvements)
*by Arslaan Pathan*  
https://arslaancodes.com/

> Notice: This is not endorsed by the Python Software Foundation nor is it endorsed by Stichting Mathematisch Centrum/CWI or any of their subsidiaries.

This repository is a patched version of Python 0.9.1 (from 1991!) which fixes the multiplication integer overflow bug on 64-bit systems, sets -std=c89 in CFLAGS by default to be compatible with GCC 15, and a couple of other QoL improvements.

## QoL improvements
- Fixed int_mul integer overflow bug in src/intobject.c on 64-bit systems
- Added -std=c89 to CFLAGS in Makefile for compatibility with GCC 15+
- Added a `make install` target that installs to /opt/python091 by default (python is at /opt/python091/bin/py091), this can be changed with the INSTALL_DIR env variable.
- Fixed PYTHONPATH to be relative to the INSTALL_DIR used in `make install` target

## Compilation & Installation

To get started with Python 0.9.1, you'll need to compile it yourself.  
Do not fear, as it should only take a couple seconds.  
Simply install the dependencies `glibc-static` and `gcc`, then run `make` inside the `src` directory.  
Once it's done, simply run the `./python` binary!

### Installing

Installing is also quite easy.  
Make sure the dependencies from earlier are installed, then run `make install` inside the `src` directory.  
If you are installing to the default INSTALL_DIR (/opt/python091) or any system directory, you may need root privileges.

## Some tips to get you started with the language

1. The syntax of Python 0.9.1 is quite similar to the syntax of Python 2, but with fewer features. The language is more lightweight overall.
2. Start by attempting to write FizzBuzz and some basic scripts. If you know Python 3, this language is easy to learn. The language is best learnt by experimenting.
2. The `os` module does not exist here; use `posix` instead.
3. The singular `=` sign is used for both assignment AND comparison (a nightmare, I know.)
4. Double-quoted strings do not exist, we only have single-quoted strings.
5. Some things may be unstable, it is not fully tested. I'll have to read through the whole codebase later.
6. If you cannot import modules from the standard library, try setting the PYTHONPATH environment variable to the location of the `lib` directory. For example, to use a standard library from ~/py091/lib, run the command like this: `PYTHONPATH=~/py091/lib /path/to/python **args`

> Original README is at README.original
