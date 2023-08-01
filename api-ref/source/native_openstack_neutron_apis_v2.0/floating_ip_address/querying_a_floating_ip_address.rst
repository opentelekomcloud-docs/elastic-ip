:original_name: eip_openstackapi_0007.html

.. _eip_openstackapi_0007:

Querying a Floating IP Address
==============================

Function
--------

This API is used to query details about a specified floating IP address, including the floating IP address status, ID of the router to which the floating IP address belongs, and external network ID of the floating IP address.

.. note::

   Note the following when you use EIPs of the Dedicated Load Balancer (**5_gray**) type:

   -  In **eu-de**, EIPs of the Dedicated Load Balancer (**5_gray**) type cannot be assigned anymore. You can assign EIPs of the BGP (**5_bgp**) type.
   -  Existing EIPs of the Dedicated Load Balancer (**5_gray**) type can be bound to dedicated or shared load balancers.

      -  The EIP console cannot be used to bind EIPs to or unbind them from dedicated load balancers.
      -  You can use APIs to bind EIPs to or unbind them from dedicated load balancers. For details, see `Binding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/binding_an_eip.html>`__ and `Unbinding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/unbinding_an_eip.html>`__.
      -  EIPs of this type can be bound to or unbound from shared load balancers using the EIP console or APIs.
      -  You are advised to bind BGP EIPs to or unbind them from dedicated load balancers.

   -  Do not add EIPs of the dedicated load balancer type (**5_gray**) and other types to the same shared bandwidth. Otherwise, the bandwidth limit policy will not take effect.

URI
---

GET /v2.0/floatingips/{floatingip_id}

Request Message
---------------

None

Response Message
----------------

.. table:: **Table 1** Response parameter

   +------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type                                                                                     | Description                                                                                                                              |
   +============+==========================================================================================+==========================================================================================================================================+
   | floatingip | :ref:`floatingip <eip_openstackapi_0007__en-us_topic_0201534072_table8139247714>` object | Specifies the floating IP address list. For details, see :ref:`Table 2 <eip_openstackapi_0007__en-us_topic_0201534072_table8139247714>`. |
   +------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

.. _eip_openstackapi_0007__en-us_topic_0201534072_table8139247714:

.. table:: **Table 2** **floatingip** objects

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | Attribute             | Type                  | Description                                                                                    |
   +=======================+=======================+================================================================================================+
   | status                | String                | Specifies the floating IP address status. The value can be **ACTIVE**, **DOWN**, or **ERROR**. |
   |                       |                       |                                                                                                |
   |                       |                       | -  **DOWN** indicates that the floating IP address has not been bound.                         |
   |                       |                       | -  **ACTIVE** indicates that the floating IP address has been bound.                           |
   |                       |                       | -  **ERROR** indicates that the floating IP address is abnormal.                               |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | id                    | String                | Specifies the floating IP address ID.                                                          |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | project_id            | String                | Specifies the project ID.                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | floating_ip_address   | String                | Specifies the floating IP address.                                                             |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | floating_network_id   | String                | Specifies the external network ID.                                                             |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | router_id             | String                | Specifies the ID of the belonged router.                                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | port_id               | String                | Specifies the port ID.                                                                         |
   |                       |                       |                                                                                                |
   |                       |                       | .. note::                                                                                      |
   |                       |                       |                                                                                                |
   |                       |                       |    The value of **port_id** is null if the EIP is bound to a dedicated load balancer.          |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | fixed_ip_address      | String                | Specifies the private IP address of the associated port.                                       |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | dns_name              | String                | Specifies the DNS name.                                                                        |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | dns_domain            | String                | Specifies the DNS domain.                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies the time when the floating IP address was created.                                   |
   |                       |                       |                                                                                                |
   |                       |                       | UTC time is used.                                                                              |
   |                       |                       |                                                                                                |
   |                       |                       | Format: *yyyy-MM-ddTHH:mm:ss*                                                                  |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | updated_at            | String                | Specifies the time when the floating IP address was updated.                                   |
   |                       |                       |                                                                                                |
   |                       |                       | UTC time is used.                                                                              |
   |                       |                       |                                                                                                |
   |                       |                       | Format: *yyyy-MM-ddTHH:mm:ss*                                                                  |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+

Example:
--------

Example request

.. code-block:: text

   GET https://{Endpoint}/v2.0/floatingips/1a3a2818-d9b4-4a9c-8a19-5252c499d1cd

Example response

.. code-block::

   {
       "floatingip": {
           "id": "1a3a2818-d9b4-4a9c-8a19-5252c499d1cd",
           "status": "DOWN",
           "router_id": null,
           "tenant_id": "bbfe8c41dd034a07bebd592bf03b4b0c",
           "project_id": "bbfe8c41dd034a07bebd592bf03b4b0c",
           "floating_network_id": "0a2228f2-7f8a-45f1-8e09-9039e1d09975",
           "fixed_ip_address": null,
           "floating_ip_address": "99.99.99.84",
           "port_id": null,
           "dns_name": "ecs-80-158-78-239",
           "dns_domain": "reverse.domain-name.com",
           "created_at": "2017-10-19T12:21:28",
           "updated_at": "2018-07-30T12:52:13"
       }
   }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
