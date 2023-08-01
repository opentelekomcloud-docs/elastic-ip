:original_name: eip_apifloatip_0002.html

.. _eip_apifloatip_0002:

Querying a Floating IP Address
==============================

Function
--------

This API is used to query details about a specific floating IP address accessible to the tenant submitting the request.

URI
---

GET /v2.0/eip/floatingips_v6/{floatingip_id}

Request Message
---------------

-  Request parameter

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}//v2.0/eip/floatingips_v6/2dedb5e7-cb70-4e78-b50f-d88c8321d161

Response Message
----------------

-  Response parameter

   .. table:: **Table 1** Response parameter

      +------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Type                                                                                     | Description                                                                                                                              |
      +============+==========================================================================================+==========================================================================================================================================+
      | floatingip | :ref:`floatingip <eip_apifloatip_0002__en-us_topic_0201534088_table870410995611>` object | Specifies the floating IP address list. For details, see :ref:`Table 2 <eip_apifloatip_0002__en-us_topic_0201534088_table870410995611>`. |
      +------------+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apifloatip_0002__en-us_topic_0201534088_table870410995611:

   .. table:: **Table 2** **floatingip** objects

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                    |
      +=======================+=======================+================================================================================================+
      | status                | String                | Specifies the floating IP address status. The value can be **ACTIVE**, **DOWN**, or **ERROR**. |
      |                       |                       |                                                                                                |
      |                       |                       | -  **ACTIVE** indicates that the floating IP address has been bound.                           |
      |                       |                       | -  **ERROR** indicates that the floating IP address is abnormal.                               |
      |                       |                       | -  **DOWN** indicates that the floating IP address has not been bound.                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | id                    | String                | Specifies the floating IP address ID.                                                          |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | floating_ip_address   | String                | Specifies the floating IPv6 address.                                                           |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | floating_network_id   | String                | Specifies the external network ID.                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | router_id             | String                | Specifies the ID of the belonged router.                                                       |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | port_id               | String                | Specifies the port ID.                                                                         |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | fixed_ip_address      | String                | Specifies the private IP address of the associated port.                                       |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
      | tenant_id             | String                | Specifies the project ID.                                                                      |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "floatingip": {
          "id": "861a4c5b-b17b-4a1d-b653-f3e95dcb3345",
          "status": "DOWN",
          "router_id": null,
          "tenant_id": "26ae5181a416420998eb2093aaed84d9",
          "project_id": "26ae5181a416420998eb2093aaed84d9",
          "floating_network_id": "0a2228f2-7f8a-45f1-8e09-9039e1d09975",
          "fixed_ip_address": null,
          "floating_ip_address": "cdcd:910a:2222:5498:8475:1111:c613:16e3",
          "port_id": null,
          "created_at": "2019-03-26T09:52:41",
          "updated_at": "2019-03-26T09:52:45"
        }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
