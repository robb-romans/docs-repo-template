.. _export-env-var:

Exporting environment variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To run the cURL requests shown in this guide, export your tenant ID and the token that you 
got during authentication to environment variables. Then copy the examples from this guide 
to the command line, script, or tool of your choice, changing URI parameters or body 
parameters as needed.

To export environment variables:

1. Export your tenant ID to the ``account`` environment variable:

   .. code::  

       $ export account="tenantID"

   Where ``tenantID`` is your account ID.

2. Export your authentication token to the ``token`` environment
   variable:

   .. code::  

       $ export token="token_id"

   Where ``token_id`` is the authentication token value in the ``id`` field of the 
   ``token`` element in the authentication response.
