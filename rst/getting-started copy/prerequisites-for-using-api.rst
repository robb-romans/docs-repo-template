.. _prereqs-for-using-api:

Prerequisites
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You need the following resources and information to send and receive API requests and 
responses.

- Rackspace Cloud account  
- Username and password to access the account
- API key to access Rackspace Cloud services
- Account number
- :ref:`Command line tool or browser client<send-api-requests>` to communicate with the API service

If you don't have an account, `sign up`_ for one.
You can find your account number and API key on the Account Settings page in the Cloud Control Panel.
    
.. _Cloud Control Panel: https://mycloud.rackspace.com    
.. _sign up: https://cart.rackspace.com/cloud/


.. _get-credentials:

Get your credentials
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Log in to the Rackspace Cloud Control panel`_ to get your Rackspace Cloud account username, 
API key, and account number. You'll need this information to communicate with Rackspace Cloud 
services by using the REST API. 

If you don't have an account, `sign up`_ for one. 

.. note:: 
     In the API service documentation, the account number is referred to as your tenant ID 
     or tenant name.

After you log in, click your username on the upper-right side of the top navigation pane.
Then, select **Account Settings** to open the page.
     
.. image:: ../_images/show-api-key-control-panel.png


**Save your API key**

- On the Account Settings page, find the API Key in the **Login Details** section.
- Click  **Show** to see the value and copy it to a text editor of your choice.
- Click **Hide** to secure the API key value in the browser.

**Save your account number**

- On the Account Settings page, scroll down to the **Account Details** section.
- Copy and save the account number.

.. important::
      Protect your API key. Do not expose the value in code samples, screen captures, or 
      insecure client-server communications. Also, make sure that the value is not 
      included in source code that is stored in public repositories. 
      
.. _Log in to the Rackspace Cloud Control panel: https://mycloud.rackspace.com   

                    
