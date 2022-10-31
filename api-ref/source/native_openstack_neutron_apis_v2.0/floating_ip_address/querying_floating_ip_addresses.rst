:original_name: eip_openstackapi_0006.html

.. _eip_openstackapi_0006:

Querying Floating IP Addresses
==============================

Function
--------

This API is used to query all floating IP addresses accessible to the tenant submitting the request.

You can query the detailed information about a specified floating IP address using the API for :ref:`Querying a Floating IP Address <eip_openstackapi_0007>`.

URI
---

GET /v2.0/floatingips

:ref:`Table 1 <eip_openstackapi_0006__en-us_topic_0201534068_table107561756154818>` describes the parameters.

.. _eip_openstackapi_0006__en-us_topic_0201534068_table107561756154818:

.. table:: **Table 1** Parameter description

   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory       | Type            | Description                                                                                                                                                                                                            |
   +=====================+=================+=================+========================================================================================================================================================================================================================+
   | id                  | No              | String          | Specifies the floating IP address ID.                                                                                                                                                                                  |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_ip_address | No              | String          | Specifies the floating IPv4 address.                                                                                                                                                                                   |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | floating_network_id | No              | String          | Specifies the external network ID.                                                                                                                                                                                     |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | You can only use fixed external network.                                                                                                                                                                               |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | You can use **GET /v2.0/networks?router:external=True** or                                                                                                                                                             |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | **GET /v2.0/networks?name={floating_network}** or run the **neutron net-external-list** command to obtain information about the external network.                                                                      |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id           | No              | String          | Specifies the ID of the belonged router.                                                                                                                                                                               |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | port_id             | No              | String          | Specifies the port ID.                                                                                                                                                                                                 |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | fixed_ip_address    | No              | String          | Specifies the private IP address of the associated port.                                                                                                                                                               |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id           | No              | String          | Specifies the project ID.                                                                                                                                                                                              |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit               | Integer         | No              | Specifies the number of records that will be returned on each page. The value is from 0 to intmax.                                                                                                                     |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | **limit** can be used together with **marker**. For details, see the parameter description of **marker**.                                                                                                              |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | marker              | String          | No              | Specifies a resource ID for pagination query, indicating that the query starts from the next record of the specified resource ID.                                                                                      |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | This parameter can work together with the parameter **limit**.                                                                                                                                                         |
   |                     |                 |                 |                                                                                                                                                                                                                        |
   |                     |                 |                 | -  If parameters **marker** and **limit** are not passed, all resource records will be returned.                                                                                                                       |
   |                     |                 |                 | -  If the parameter **marker** is not passed and the value of parameter **limit** is set to **10**, the first 10 resource records will be returned.                                                                    |
   |                     |                 |                 | -  If the value of the parameter **marker** is set to the resource ID of the 10th record and the value of parameter **limit** is set to **10**, the 11th to 20th resource records will be returned.                    |
   |                     |                 |                 | -  If the value of the parameter **marker** is set to the resource ID of the 10th record and the parameter **limit** is not passed, resource records starting from the 11th records (including 11th) will be returned. |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | page_reverse        | Boolean         | No              | Specifies the page direction. The value can be **True** or **False**.                                                                                                                                                  |
   +---------------------+-----------------+-----------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example:

.. code-block:: text

   GET https://{Endpoint}/v2.0/floatingips?id={fip_id}&router_id={router_id}&floating_network_id={net_id}&floating_ip_address={floating_ip}&port_id={port_id}&fixed_ip_address={fixed_ip}&tenant_id={tenant_id}

Request Message
---------------

None

Response Message
----------------

.. table:: **Table 2** Response parameter

   +-------------+----------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Type                                                                                               | Description                                                                                                                              |
   +=============+====================================================================================================+==========================================================================================================================================+
   | floatingips | Array of :ref:`floatingip <eip_openstackapi_0006__en-us_topic_0201534068_table8139247714>` objects | Specifies the floating IP address list. For details, see :ref:`Table 3 <eip_openstackapi_0006__en-us_topic_0201534068_table8139247714>`. |
   +-------------+----------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------+

.. _eip_openstackapi_0006__en-us_topic_0201534068_table8139247714:

.. table:: **Table 3** **floatingip** objects

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                    |
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

   GET https://{Endpoint}/v2.0/floatingips?limit=1

Example response

.. code-block::

   {
       "floatingips": [
           {
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
       ]
   }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <eip_api05_0002>`.
