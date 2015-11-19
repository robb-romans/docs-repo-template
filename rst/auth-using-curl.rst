.. _authenticate-using-curl:

Generate an authentication token using cURL
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Complete these steps to generate an authentication token.

#. If you don't have it, get the API key for your Rackspace Cloud account.

   #. Log in to the `Cloud Control Panel`_ by using the username and password 
      for your Rackspace Cloud account. 
      
   #. In the top-right corner of the Control Panel menu, click **yourUserName**. 
      Then, click **Account Settings**.
   
   #. On the Account Settings page, find your API key in the **Login Details** section. 
       
   #. To save the value, click **Show**. Then, copy the value and export it to an 
      environment variable.
      
       .. code:: bash

           $ export apiKey="API key"

      Replace the *API key* variable with the value you copied from the control panel.  


#. From a command prompt, submit a **POST tokens** request that includes your username and 
   API key to the Identity service API endpoint as shown in the following cURL example:

      .. code:: bash

          $ curl https://identity.api.rackspacecloud.com/v2.0/tokens  \
           -X POST \
           -d '{"auth":{"RAX-KSKEY:apiKeyCredentials":{"username":"yourUserName","apiKey":"$apiKey"}}}' \
           -H "Content-type: application/json" | python -m json.tool
           

#. Check the :ref:`authentication response <samp-auth-resp>`.

   -  If the request is successful, the Identity service returns a response that includes 
      an authentication token, user information and role assignments, and a service catalog with 
      information about the services that you can access with the authentication token. 
      Use this information to submit :ref:`submit an API
      request <submit-an-api-request>`.
      
      .. note:: 
            For detailed reference information, see 
            :rax-devdocs:`Annotated authentication request and response <cloud-identity/v2/developer-guide/#annotated-authentication-request-and-response>`
            in the Cloud Identity API documentation.

      
   -  If the request is not successful, review the response message and
      the following error message descriptions to determine next steps.

      ``400 Invalid request body: unable to parse Auth data. Please review XML or JSON formatting``
      
        Review the authentication request for syntax or coding errors.
        If you are using cURL, see :ref:`How cURL commands work <how-curl-commands-work>`.
          

      ``401 Unable to authenticate user with credentials provided.``
        
        Verify the authentication credentials submitted in the
        authentication request. If necessary, contact your Rackspace
        Cloud Administrator or Rackspace Support to get valid
        credentials.

      ..  note:: 
      
          For additional information about authentication errors, see the 
          :rax-devdocs:`Identity API Reference documentation <cloud-identity/v2/developer-guide/#document-api-operations/token-operations>`.

          To use authentication tokens securely and efficiently, review the information 
          about :rax-devdocs:`managing authentication tokens <cloud-identity/v2/developer-guide/#manage-authentication-tokens>`. 
          in the Rackspace Cloud Identity service documentation.
          
Save key values
~~~~~~~~~~~~~~~~~

When you authenticate successfully, the authentication response returns the following key 
values required to use the |apiservice|.

- The token ID value is required to confirm your identity each time you access the service.
- The tenant ID provides your account number. This value is appended to the API endpoint in the 
  service catalog.  
- The API endpoint provides the URL that you use to access the API service.

Save these values so that you can include them in API service requests.

.. note:: 
       The authentication response also includes other user, role, and authentication 
       information. For details, see the  
       :rax-devdocs:`annotated authentication request and response <cloud-identity/v2/developer-guide/##annotated-authentication-request-and-response>`
       in the Rackspace Cloud Identity service documentation.
      

#. In the ``token`` section of the response, copy the token ``id`` value from the token object.

      .. include:: ../samples/auth-token-object.rst
   
#. :ref:`Export the token ID to an environment variable<export-env-var>`
   that can be supplied in the `X-Auth-Token` header required in each
   API request.  
   
   .. code::

       $ export auth-token="token-id"

   Replace the *token_id* variable with the authentication token ``id`` value returned 
   in the authentication response.
        
        
#. In the ``service catalog``, copy the ``publicURL`` value for the 
   |apiservice|, version, and region that you want to access. 
   
   This example shows the endpoints available for the |apiservice|. 
   
   .. include:: ../samples/service-catalog-endpoint.rst
   
   
   .. note:: 
          For guidance on choosing an endpoint, see :ref:`Service access`<service-access-endpoints>`.
          
   
#. Copy the URL, and then export it to an environment variable.

   .. code::
      
        $ export api-endpoint="publicURL"
      
      
   Replace the *publicURL* with the publicURL value listed in the service catalog.
    