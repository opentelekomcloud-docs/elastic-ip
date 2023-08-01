:original_name: eip_apifloatip_0004.html

.. _eip_apifloatip_0004:

Updating a Floating IP Address
==============================

Function
--------

This API is used to update a specific floating IP address and the port associated with the IP address. If **port_id** is left blank, the floating IP address has been unbound from the port.

Restrictions

When you bind a floating IP address, if the floating IP address is in the **error** state, try unbinding the address first.

You are not allowed to bind a floating IP address that has been bound to a port to another port. You must first unbind the IP address from its original port and bind it to the required port.

URI
---

PUT /v2.0/eip/floatingips_v6/{floatingip_id}

Request Message
---------------

-  Request parameter

   .. table:: **Table 1** Request parameter

      +------------+------------------------------------------------------------------------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Type                                                                                     | Mandatory | Description                                                                                                                              |
      +============+==========================================================================================+===========+==========================================================================================================================================+
      | floatingip | :ref:`floatingip <eip_apifloatip_0004__en-us_topic_0201534155_table547993685510>` object | Yes       | Specifies the floating IP address list. For details, see :ref:`Table 2 <eip_apifloatip_0004__en-us_topic_0201534155_table547993685510>`. |
      +------------+------------------------------------------------------------------------------------------+-----------+------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apifloatip_0004__en-us_topic_0201534155_table547993685510:

   .. table:: **Table 2** **floatingip** objects

      ========= ========= ====== ======================
      Parameter Mandatory Type   Description
      ========= ========= ====== ======================
      port_id   No        String Specifies the port ID.
      ========= ========= ====== ======================

-  Example request 1 (Binding to a port)

   .. code-block:: text

      PUT https://{Endpoint}/v2.0/eip/floatingips_v6/b639c937-4737-4107-8978-fecc7327a5ae

      {
          "floatingip": {
              "port_id": "21b5c483-84e9-40a1-86b3-3041606106f5",
              "fixed_ip_address": "10.0.2.2"
          }
      }

-  Example request 2 (Unbinding from a port)

   .. code-block:: text

      PUT https://{Endpoint}/v2.0/eip/floatingips_v6/3870858f-91dc-489f-92a1-c04dbdc6d781

      {
          "floatingip": {
              "port_id": null
          }
      }

Response Message
----------------

-  Response parameter

   .. table:: **Table 3** Response parameter

      +------------+-------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Type                                                                                      | Description                                                                                                                               |
      +============+===========================================================================================+===========================================================================================================================================+
      | floatingip | :ref:`floatingip <eip_apifloatip_0004__en-us_topic_0201534155_table1935317341267>` object | Specifies the floating IP address list. For details, see :ref:`Table 4 <eip_apifloatip_0004__en-us_topic_0201534155_table1935317341267>`. |
      +------------+-------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apifloatip_0004__en-us_topic_0201534155_table1935317341267:

   .. table:: **Table 4** **floatingip** objects

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

-  Example response 1 (Binding a specified floating IP address to a port)

   .. code-block::

      {
          "floatingip": {
              "router_id": "76c052d6-6a92-444c-b67d-147ee166a480",
              "status": "ACTIVE",
              "tenant_id": "6fbe9263116a4b68818cf1edce16bc4f",
              "floating_network_id": "0a2228f2-7f8a-45f1-8e09-9039e1d09975",
              "fixed_ip_address": "10.0.2.2",
              "floating_ip_address": "cdcd:910a:2222:5498:8475:1111:c013:8096",
              "port_id": "21b5c483-84e9-40a1-86b3-3041606106f5",
              "id": "b639c937-4737-4107-8978-fecc7327a5ae"
          }
      }

-  Example response 2 (Unbinding a specified floating IP address from a port)

   .. code-block::

      {
          "floatingip": {
              "floating_network_id": "809fdbbc-2e3e-426e-897c-cb632b081a72",
              "router_id": null,
              "fixed_ip_address": null,
              "floating_ip_address": "cdcd:910a:2222:5498:8475:1111:c013:8096",
              "tenant_id": "3c8c36e1520147ccbc83d2ccfbb9ab24",
              "status": "ACTIVE",
              "port_id": null,
              "id": "3870858f-91dc-489f-92a1-c04dbdc6d781"
          }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
