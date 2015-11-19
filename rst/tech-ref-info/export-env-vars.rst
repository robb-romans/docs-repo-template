.. _export-env-var:

Exporting environment variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To run the cURL requests shown in this guide, export the authentication token and tenant ID 
values returned in the authentication response to environment variables. Then, copy the 
examples from this guide to the command line, script, or tool of your choice, 
changing URI parameters or body parameters as needed.

To export environment variables:

1. Export your authentication token to the ``token`` environment
   variable:

   .. code::  

       $ export token="token_id"

   Replace the *token_id* variable with the authentication token ``id`` value returned 
   in the authentication response. 
   
2. Export your tenant ID to the ``account`` environment variable:

   .. code::  

       $ export account="tenantID"

   Replace the *tenantID* variable with the tenant ``id`` value returned in the authentication 
   response.  
   
   .. note:: 
         The tenant ID is the same as your account ID that is displayed in the Cloud Control 
         panel when you are logged into your Rackspace Cloud account.

