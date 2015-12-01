This content architecture is a template for the beginning sections of a Getting Started Guide:

- Getting Started Guide overview
- Prerequisities
- Send API requests
- Authenticate

This is a template with some common content that can be used for all guides, but some topics and content need to be customized to fit your use case. Review the following information for guidance on how to apply and customize this architecture and common content for a specific instance of the API service documentation.

##Content architecture and description

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
└── getting-started.rst                   Intro topic for main header in contents. Use the description in the Customize
                                          template as an example. Customize the text to match the details for each product.

```

##Update Authentication section in General API Info section

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

##Update your conf.py file

Add the `common-gs` folder to the `exlude_patterns`. For example:

````

exclude_patterns = ['_build', 'samples', 'api-operations/methods*', 'common-gs']

````

Add the `apiservice` shortcut the `rst_epilog`. For example:

````

rst_epilog = """
.. |apiservice| replace:: Rackspace Cloud Servers API
.. |no changes| replace:: None for this release
.. |contract version| replace:: 2.0
.. |product name| replace:: Rackspace Cloud Servers
"""

````

Don't forget to replace **Rackspace Cloud Servers** with your product name.

Also, after updating the `authentication.rst` file in the General API info
section, be sure to fix the reference in `service-access-endpoints.rst`, also
in the General API info section.

The reference is in the paragraph following the endpoint table, and it should
be changed to:

````
In your authentication response (see :ref:`authentication-ovw`),
it is listed as InternalURL.

````

##Integrate use cases

Integrate your use cases into this architecture by adding an H1 topic to introduce them. This structure keeps the major
headings at the same levels as *Prerequsities*, *Send API requests*, and so on. For example, if your 
guide shows examples for basic operations, add an H1 intro topic for the use cases, and then include the example topics 
in the intro topic. See [Cloud Queues](https://developer.rackspace.com/docs/cloud-queues/v1/developer-guide/#document-getting-started)  for an example.

Also, note that we want to use the environment variables created in the common authentication topic in the examples. For the Cloud Queues product, I added the following note to the Use case intro topic:

````
.. note:: 
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and ``$TENANT_ID`` environment 
     variables to specify the API endpoint, authentication token, and project ID values 
     for accessing the service. Make sure you 
     :ref:`configure these variables<configure-environment-variables>` before running the 
     code samples. 
     
````
Then, I replaced the values in the examples to use the environment variables. 
