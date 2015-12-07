**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Apply Getting Started Guide template to migrated content](#apply-getting-started-guide-template-to-migrated-content)
	- [Content architecture and description](#content-architecture-and-description)
	- [Update Authentication section in General API Info section](#update-authentication-section-in-general-api-info-section)
	- [Update your conf.py file](#update-your-confpy-file)
	- [Integrate use cases](#integrate-use-cases)
	- [Use environment variables in use case examples](#use-the-environment-variables-in-use-case-examples)

#Apply Getting Started Guide template to migrated content

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

Integrate use cases into the Getting Started Guide by adding a use case intro topic(s) at the same level (H1) as the **Prerequisites*, *Send API requests*, and *Authenticate* sections. Then, nest the use case examples under the intro topic(s). 

Like most things with Sphinx, you can create this architecture in different ways. 

For example, if your guide shows examples for basic operations, add an H1 intro topic for the use cases, and then use the include directive to nest the use case examples under the H1 header.  See [Cloud Queues](https://developer.rackspace.com/docs/cloud-queues/v1/developer-guide/#document-getting-started)  for an example.

To follow the Cloud Queues use case example, complete these tasks: 

* In the getting-started folder, create a use case overview topic, for example   [using-cloud-queues.rst(https://github.com/rackerlabs/docs-cloud-queues/blob/master/api-docs/getting-started/using-cloud-queues.rst)

* In the getting-started folder, add an ``examples`` folder and move all of the use case example files into that folder. 

* In the use case intro topic, use the ``include`` directive to add all of the examples.

  ```
     .. include:: examples/gs-create-queue.rst
     .. include:: examples/gs-post-message.rst
     .. include:: examples/gs-claim-messages.rst
     .. include:: examples/gs-delete-message.rst
     .. include:: examples/gs-release-claim.rst
     .. include:: examples/gs-delete-queue.rst
  ```

* To prevent Sphinx duplicate label build errors, add the ``examples`` folder to the conf.py ``excludes`` specification.  

   ```
      exclude_patterns = ['_build', 'samples', 'api-operations/methods*', 'common-gs', 'getting-started/examples']
  
   ```

After making these changes, the Sphinx project Getting Started directory has the following structure: 

```
	├── getting-started
	│   ├── authenticate.rst
	│   ├── examples                    New folder that contains the use case example files.
	│   │   ├── gs-claim-messages.rst   Use case examples converted from DocBook source.
	│   │   ├── gs-create-queue.rst
	│   │   ├── gs-delete-message.rst
	│   │   ├── gs-delete-queue.rst
	│   │   ├── gs-post-message.rst
	│   │   └── gs-release-claim.rst
	│   ├── index.rst
	│   ├── prerequisites-for-using-api.rst
	│   ├── send-request-ovw.rst
	│   └── using-cloud-queues.rst      New introductory topic for the use cases.
	
```

##Use the environment variables in use case examples

The common authentication topics have a section to create environment variables. Use these variables in the use case examples, and 
add the following note to the Use Case intro topic. 
````
.. note:: 
     These examples use the ``$API_ENDPOINT``, ``$AUTH_TOKEN``, and ``$TENANT_ID`` environment 
     variables to specify the API endpoint, authentication token, and project ID values 
     for accessing the service. Make sure you 
     :ref:`configure these variables<configure-environment-variables>` before running the 
     code samples. 
     
````
In the use case examples, replace the endpoint, auth-token, and tenant-id values or variables with the common environment variables. 
