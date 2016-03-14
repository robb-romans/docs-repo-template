.. _common-dg-service-access-endpoints:

.. Some Rackspace cloud services are regionalized, some are not, for example services like 
.. Identity and DNS only have a single, global endpoint. Some services also have special 
.. considerations associated with endpoint access and operations. This topic is a 
.. general template for documenting regionalized endpoint. 

============================
Service access endpoints
============================

The |apiservice| is a regionalized service. The user of the service is therefore 
responsible for selecting the appropriate regional endpoint to ensure access to servers, 
networks, or other Cloud services.

.. tip::

   To help you decide which regionalized endpoint to use, read 
   about :how-to:`special considerations for choosing a region<about-regions>`.
   
   
When your Rackspace cloud service resources are in one Rackspace data center, using the 
``ServiceNet`` endpoint has no network costs and provides a faster connection. 
``ServiceNet`` is the data center internet network. In your authentication response 
service catalog, it is listed as ``InternalURL``.

If you are working with cloud service resources that are not in one of the Rackspace data 
centers, you must use a public endpoint to connect. In your authentication response, 
public endpoints are listed as ``publicURL``.  If you are working with servers in multiple 
data centers or have a mixed environment where you have servers in your data centers and 
in Rackspace data centers, use a public endpoint because it is accessible from all the 
servers in the different environments.


.. note::

   If you do not know your account ID or which data center you are working in, you can 
   find that information in your  your :mycloud:`Cloud Control Panel<>`.


.. include:: service-access-endpoints-table.txt


.. note:
   
   The service catalog returned in the auth response specifies the correct service access 
   endpoint for your account to use for accessing DNS. Use the service type (rax:dns) to 
   locate the correct endpoint in the service catalog. For an example of the service catalog, 
   see :ref:`authentication response examples <review-auth-resp>`.


