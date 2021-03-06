============
wetransferpy
============
.. image:: https://travis-ci.org/predat/wetransferpy.svg?branch=master
    :alt: Build Status
    :target: https://travis-ci.org/predat/wetransferpy
.. image:: https://badge.fury.io/py/wetransferpy.svg
    :target: https://badge.fury.io/py/wetransferpy

Python script for uploading and downloading wetransfer files from the command line.
Inspired by `upload-wetransfer <https://github.com/kraynel/upload-wetransfer>`__ by
`kraynel <https://github.com/kraynel>`__ and `wetransfer-upload <https://github.com/creemerica/wetransfer-upload>`__
by `Spencer Cree <https://github.com/creemerica>`.

Features
--------

-  Upload files or directories of files with or without authentication

-  Download file from url

-  Show progress of upload and download


Installation
------------

.. code:: bash

    pip install wetransferpy

or

.. code:: bash

    git clone https://github.com/predat/wetransferpy


Usage
-----

Authenticate upload:

.. code-block:: python

    from wetransferpy import WeTransfer

    wt = WeTransfer(username="name@example.com",
                    password="thepassword",
                    sender="sender@example.com",
                    receivers=["receiver1@example.com","receiver2@example.com"],
                    channel='',
                    message='Hello from python',
                    expire_in='3m',
                    progress=True,
    )
    wt.uploadFile('thefile.mov')


Anonymous upload:

.. code-block:: python

    from wetransferpy import WeTransfer
    wt = Wetransfer()
    url = wt.uploadFile('thefile.mov')
    print url


Upload Shell script usage:

.. code-block:: bash

    wetranfer-upload -h

    usage: wetransfer-upload [-h] [-b] [-u USERNAME] [-p PASSWORD] [-e EXPIRE]
                         [-c CHANNEL] [-r [RECEIVER [RECEIVER ...]]]
                         [-s SENDER] [-m MESSAGE] [-R]
                         files [files ...]

    Uploads files or folders to WeTransfer.

    positional arguments:
      files                 files or directory to send

    optional arguments:
      -h, --help            show this help message and exit
      -b, --no-progressbar  Hide progress bar
      -u USERNAME, --username USERNAME
                            WeTransfer user account name
      -p PASSWORD, --password PASSWORD
                            WeTransfer password
      -e EXPIRE, --expire EXPIRE
                            File expiration
      -c CHANNEL, --channel CHANNEL
                            WeTransfer channel
      -r [RECEIVER [RECEIVER ...]], --receiver [RECEIVER [RECEIVER ...]]
                            emails of the receivers
      -s SENDER, --sender SENDER
                            email of the sender
      -m MESSAGE, --message MESSAGE
                            message to send
      -R, --recursive       recursive send


Download shell script usage:

.. code-block:: bash

    wetranfer-download -u http://we.tl/XV4MmuqPRd


