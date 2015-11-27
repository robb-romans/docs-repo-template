.. _request-using-lava-client:

Using the Lava client
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The Lava client is a command-line tool that provides access to all public Cloud 
Big Data API methods. To send requests using the client, you have to install it. 

**Prerequisites**

- Linux or Mac OS X
- Python 2.7.2 or later
- Rackspace Cloud account and access to Rackspace Cloud Big Data
- Perform the following steps to install the CLI.

Install the python-lavaclient from PyPI using pip.

.. code::

	$ sudo pip install lavaclient
	
Run the help command to ensure that the client has been installed correctly and to review 
information about using the client.

.. code:: 

    $ lava --help

To get started using the client, see :ref:`authenticate by using the lava 
client <auth-using-client>`