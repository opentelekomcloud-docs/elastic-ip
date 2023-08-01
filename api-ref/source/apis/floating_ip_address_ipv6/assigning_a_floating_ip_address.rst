:original_name: eip_apifloatip_0003.html

.. _eip_apifloatip_0003:

Assigning a Floating IP Address
===============================

Function
--------

This API is used to assign a floating IP address and associates it with an internal port.

Restrictions

You can use **GET /v2.0/networks?router:external=True** or run the **neutron net-external-list** command to obtain the UUID of the external network required for assigning a floating IP address.

The **port_id** parameter value must be the ECS port ID, which can be obtained from the **NIC ID** parameter in the ECS NIC details.

URI
---

POST /v2.0/eip/floatingips_v6

Request Message
---------------

-  Request parameter

.. table:: **Table 1** Request parameter

   +------------+-------------------------------------------------------------------------------------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type                                                                                      | Mandatory | Description                                                                                                                               |
   +============+===========================================================================================+===========+===========================================================================================================================================+
   | floatingip | :ref:`floatingip <eip_apifloatip_0003__en-us_topic_0201534148_table1831319135111>` object | Yes       | Specifies the floating IP address list. For details, see :ref:`Table 2 <eip_apifloatip_0003__en-us_topic_0201534148_table1831319135111>`. |
   +------------+-------------------------------------------------------------------------------------------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+

.. _eip_apifloatip_0003__en-us_topic_0201534148_table1831319135111:

.. table:: **Table 2** **floatingip** objects

   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory       | Type            | Description                                                                                                                                       |
   +=====================+=================+=================+===================================================================================================================================================+
   | id                  | Yes             | String          | Specifies the floating IP address ID.                                                                                                             |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address | No              | String          | Specifies the floating IPv6 address.                                                                                                              |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_network_id | No              | String          | Specifies the external network ID.                                                                                                                |
   |                     |                 |                 |                                                                                                                                                   |
   |                     |                 |                 | You can only use fixed external network.                                                                                                          |
   |                     |                 |                 |                                                                                                                                                   |
   |                     |                 |                 | You can use **GET /v2.0/networks?router:external=True** or                                                                                        |
   |                     |                 |                 |                                                                                                                                                   |
   |                     |                 |                 | **GET /v2.0/networks?name={floating_network}** or run the **neutron net-external-list** command to obtain information about the external network. |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id           | No              | String          | Specifies the ID of the belonged router.                                                                                                          |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | port_id             | No              | String          | Specifies the port ID.                                                                                                                            |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | fixed_ip_address    | No              | String          | Specifies the private IP address of the associated port.                                                                                          |
   |                     |                 |                 |                                                                                                                                                   |
   |                     |                 |                 | This value can only be dynamically assigned by the system.                                                                                        |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id           | No              | String          | Specifies the project ID.                                                                                                                         |
   +---------------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

.. code-block:: text

   POST https://{Endpoint}/v2.0/eip/floatingips_v6

   {
       "floatingip": {
           "floating_network_id": "5ce655fa-c911-4d2c-99f7-445bc1162ef8",
           "port_id": "552389f5-8f4c-4bb7-9991-07233c315d60"
       }
   }

Response Message
----------------

-  Response parameter

   .. table:: **Table 3** Response parameter

      +------------+-----------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter  | Type                                                                                    | Description                                                                                                                             |
      +============+=========================================================================================+=========================================================================================================================================+
      | floatingip | :ref:`floatingip <eip_apifloatip_0003__en-us_topic_0201534148_table71601678316>` object | Specifies the floating IP address list. For details, see :ref:`Table 4 <eip_apifloatip_0003__en-us_topic_0201534148_table71601678316>`. |
      +------------+-----------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apifloatip_0003__en-us_topic_0201534148_table71601678316:

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

-  Example response

   .. code-block::

      {
          "floatingip": {
              "router_id": "76c052d6-6a92-444c-b67d-147ee166a480",
              "status": "DOWN",
              "tenant_id": "6fd9b5fdb997425f97bc5ba1f0846084",
              "floating_network_id": "5ce655fa-c911-4d2c-99f7-445bc1162ef8",
              "fixed_ip_address": "12.xx.xx.5",
              "floating_ip_address": "cdcd:910a:2222:5498:8475:1111:c013:8096",
              "port_id": "552389f5-8f4c-4bb7-9991-07233c315d60",
              "id": "2567f393-5c76-42db-a397-477723ce41f7"
          }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
