.. httpcode documentation master file, created by
   sphinx-quickstart on Wed Dec 21 15:35:58 2011.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to httpcode
===================

::

     _   _ _____ _____ ____   ____ ___  ____  _____
    | | | |_   _|_   _|  _ \ / ___/ _ \|  _ \| ____|
    | |_| | | |   | | | |_) | |  | | | | | | |  _|
    |  _  | | |   | | |  __/| |__| |_| | |_| | |___
    |_| |_| |_|   |_| |_|    \____\___/|____/|_____|


`httpcode` is a little utility that explains the meaning of an HTTP
status code on the command line.

Installation
------------

.. code-block:: bash

    $ [sudo] pip install httpcode


Usage
-----

Explain 405 status code

.. code-block:: bash

    $ hc 405
    Status code 405
    Message: Method Not Allowed
    Code explanation: Specified method is invalid for this resource.

Or 418 status code :)

.. code-block:: bash

    $ hc 418
    Status code 418
    Message: I'm a teapot
    Code explanation: The HTCPCP server is a teapot

List all codes

.. code-block:: bash

    $ hc
    Status code 100
    Message: Continue
    Code explanation: Request received, please continue

    Status code 101
    Message: Switching Protocols
    Code explanation: Switching to new protocol; obey Upgrade header

    Status code 200
    Message: OK
    Code explanation: Request fulfilled, document follows

    ...

Search code(s) by description (case-insensitive)

.. code-block:: bash

    $ hc -s too
    Status code 413
    Message: Request Entity Too Large
    Code explanation: Entity is too large.

    Status code 414
    Message: Request-URI Too Long
    Code explanation: URI is too long.

Filter codes with a regex

.. code-block:: bash

    $ hc 30[12]
    Status code 301
    Message: Moved Permanently
    Code explanation: Object moved permanently -- see URI list

    Status code 302
    Message: Found
    Code explanation: Object moved temporarily -- see URI list

Use an 'x' for any digit

.. code-block:: bash

    $ hc 1xx
    Status code 100
    Message: Continue
    Code explanation: Request received, please continue

    Status code 101
    Message: Switching Protocols
    Code explanation: Switching to new protocol; obey Upgrade header

Show help

.. code-block:: bash

    $ hc -h
    Usage: hc [code] [options]

    code may contain regular expression or use 'x' to denote any digit
    code examples: 418, 30[12], 3.*, 1xx

    Without parameters lists all available
    HTTP status codes and their description


    Options:
      -h, --help            show this help message and exit
      -s SEARCH, --search=SEARCH
                            Search for a code by name or description. Search text
                            may contain regular expressions.

Roadmap
-------

Add more codes

