:original_name: eip_api_0005.html

.. _eip_api_0005:

Releasing an EIP
================

Function
--------

This API is used to release an EIP.

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

DELETE /v1/{project_id}/publicips/{publicip_id}

:ref:`Table 1 <eip_api_0005__en-us_topic_0201534180_table45251091>` describes the parameters.

.. _eip_api_0005__en-us_topic_0201534180_table45251091:

.. table:: **Table 1** Parameter description

   =========== ========= ==========================================
   Name        Mandatory Description
   =========== ========= ==========================================
   project_id  Yes       Specifies the project ID.
   publicip_id Yes       Specifies the unique identifier of an EIP.
   =========== ========= ==========================================

Request Message
---------------

-  Request parameter

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v1/{project_id}/publicips/{publicip_id}

Response Message
----------------

-  Response parameter

   None

-  Example response

   None

   Or

   .. code-block::

      {
             "code":"xxx",
             "message":"xxxxx"
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
