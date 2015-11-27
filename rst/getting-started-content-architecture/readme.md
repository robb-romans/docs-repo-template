This content architecture is a template for the beginning sections of a Getting Started Guide --

In the generated output, the content structure is like the one shown in the following example:

Getting Started Guide intro architecture: 
![alttext](https://raw.githubusercontent.com/meker12/docs-common/master/templates/getting-started-intro-content.png "GS TOC")

The following tree structure describes the RST source, code samples, and image files 
in the template for the Getting Started content architecture.

````

├── common-gs                             Common files for Getting Started module
│   │
│   ├── auth-using-client.rst             Auth-using-client template; topic to be customized per guide
│   │                                     Included in authentication.rst topic
│   │
│   ├── auth-using-curl.rst               Common Auth using cURL example for all guides.
│   │                                     Included in authentication.rst topic
│   │
│   ├── get-credentials.rst               Common file to get account info from Control Panel
│   │                                     Included in prerequisites-for-using-api.rst
│   │
│   ├── how-to-use-curl.rst               Common topic for all guides. 
│   │
│   │                                     Requires using common auth-using-client.rst template
│   │                                     because of link to "Create environment variables".
│   ├── images
│   │   └── show-api-key-control-panel.png  Control panel screen cap for Get credentials topic.
│   │
│   ├── samples
│   │   ├── auth-req-curl.rst             Common cURL example for how-to-use-curl and auth-using-curl
│   │   │                                 
│   │   ├── auth-resp-json.rst            Common response example used in auth-using-curl.rst
│   │   │
│   │   ├── auth-token-object.rst         Common token obj used in auth-using-curl.rst
│   │   │   
│   │   └── service-catalog-endpoint.rst  Endpoint example in auth-using-curl.rst - 
│   │                                     Replace code sample with product-specific info.
│   │
│   ├── using-client.rst                  Template topic for using client.  Customize per 
│   │                                     guide. See Servers and Cloud Big Data GS for examples.
│   │            
│   └── using-env-variables.rst           Note about env variables session restriction and link to more info about using 
│   │                                     Used in auth-using-curl and auth-using-client. 
│   │
├── getting-started
│   │
│   ├── authenticate.rst                  Common Authentication overview topic.
│   │                                     
│   ├── index.rst                         Getting Started content index
│   │                                     Update per guide as required
│   │
│   │
│   │
│   ├── prerequisites-for-using-api.rst   Common intro to capture what's needed 
│   │                                     to use API. Might require additional info per product.
│   │
│   └── send-request-ovw.rst              Common intro topic for Send requests: customize  
│                                         depending on whether service has cURL and CLI. 
│
└── getting-started.rst                   Intro topic for main header in contents. Customize 
                                          description per guide. 
                                          
```
                                          
Integrate your use cases into this architecture by adding them as H1 topics so the major 
headings are at the same levels as *Prerequsities*, *Send API requests*, and so on.


**Update Authentication section in General API Info section**

The Authentication topics replace most of the information in the Authentication section of 
the General API info section.

In the General API info section, replace the content in the Authentication.rst source file 
with the following content:

````
.. _authentication-ovw: 

==============
Authentication
==============

Each REST request against the Cloud Big Data service requires the inclusion of a specific 
authorization token, supplied in the ``X-Auth-Token`` HTTP header of each API request. 
You get a token by submitting an authentication request with valid account credentials to 
the following Rackspace Cloud Identity API service endpoint:

.. code::
     
       https://identity.api.rackspacecloud.com/v2.0

For details see the following information:

- :ref:`Authenticate to the Rackspace Cloud<authenticate-to-cloud>`
- :rax-devdocs:`Rackspace Cloud Identity API developer documentation 
  <cloud-identity/v2/developer-guide/>`


````

