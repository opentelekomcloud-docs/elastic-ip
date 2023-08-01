:original_name: eip_api_0003.html

.. _eip_api_0003:

Querying EIPs
=============

Function
--------

This API is used to query EIPs.

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

GET /v1/{project_id}/publicips

:ref:`Table 1 <eip_api_0003__en-us_topic_0201534309_table51200735>` describes the parameters.

.. _eip_api_0003__en-us_topic_0201534309_table51200735:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Name                  | Mandatory       | Type            | Description                                                                                                                                                                                                                                                 |
   +=======================+=================+=================+=============================================================================================================================================================================================================================================================+
   | project_id            | Yes             | String          | Specifies the project ID.                                                                                                                                                                                                                                   |
   +-----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | marker                | No              | String          | Specifies a resource ID for pagination query, indicating that the query starts from the next record of the specified resource ID.                                                                                                                           |
   |                       |                 |                 |                                                                                                                                                                                                                                                             |
   |                       |                 |                 | This parameter can work together with the parameter **limit**.                                                                                                                                                                                              |
   |                       |                 |                 |                                                                                                                                                                                                                                                             |
   |                       |                 |                 | -  If parameters **marker** and **limit** are not passed, resource records on the first page will be returned.                                                                                                                                              |
   |                       |                 |                 | -  If the parameter **marker** is not passed and the value of parameter **limit** is set to **10**, the first 10 resource records will be returned.                                                                                                         |
   |                       |                 |                 | -  If the value of the parameter **marker** is set to the resource ID of the 10th record and the value of parameter **limit** is set to **10**, the 11th to 20th resource records will be returned.                                                         |
   |                       |                 |                 | -  If the value of the parameter **marker** is set to the resource ID of the 10th record and the parameter **limit** is not passed, resource records starting from the 11th records (including 11th) will be returned.                                      |
   +-----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | limit                 | No              | Integer         | Specifies the number of records that will be returned on each page. The value is from 0 to intmax (2^31-1). The default value is 2000.                                                                                                                      |
   |                       |                 |                 |                                                                                                                                                                                                                                                             |
   |                       |                 |                 | **limit** can be used together with **marker**. For details, see the parameter description of **marker**.                                                                                                                                                   |
   +-----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | enterprise_project_id | No              | String          | -  Specifies the enterprise project ID. This field can be used to filter the EIPs of an enterprise project.                                                                                                                                                 |
   |                       |                 |                 | -  The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-). Value **0** indicates the default enterprise project. To obtain the EIPs bound to all enterprise projects of the user, set **all_granted_eps**. |
   |                       |                 |                 |                                                                                                                                                                                                                                                             |
   |                       |                 |                 | .. note::                                                                                                                                                                                                                                                   |
   |                       |                 |                 |                                                                                                                                                                                                                                                             |
   |                       |                 |                 |    This parameter is unsupported. Do not use it.                                                                                                                                                                                                            |
   +-----------------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Request Message
---------------

-  Request parameter

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v1/{project_id}/publicips?limit={limit}&marker={marker}

Response Message
----------------

-  Response parameter

   .. table:: **Table 2** Response parameter

      +-----------+-------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------+
      | Name      | Type                                                                                      | Description                                                                                                        |
      +===========+===========================================================================================+====================================================================================================================+
      | publicips | Array of :ref:`publicips <eip_api_0003__en-us_topic_0201534309_table83964341880>` objects | Specifies the EIP object. For details, see :ref:`Table 3 <eip_api_0003__en-us_topic_0201534309_table83964341880>`. |
      +-----------+-------------------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0003__en-us_topic_0201534309_table83964341880:

   .. table:: **Table 3** Description of the **publicips** field

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                                             |
      +=======================+=======================+=========================================================================================================================================================================+
      | id                    | String                | Specifies the unique identifier of an EIP.                                                                                                                              |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | -  Specifies the EIP status.                                                                                                                                            |
      |                       |                       | -  Possible values are as follows:                                                                                                                                      |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    -  **FREEZED** (Frozen)                                                                                                                                              |
      |                       |                       |    -  **BIND_ERROR** (Binding failed)                                                                                                                                   |
      |                       |                       |    -  **BINDING** (Binding)                                                                                                                                             |
      |                       |                       |    -  **PENDING_DELETE** (Releasing)                                                                                                                                    |
      |                       |                       |    -  **PENDING_CREATE** (Assigning)                                                                                                                                    |
      |                       |                       |    -  **PENDING_UPDATE** (Updating)                                                                                                                                     |
      |                       |                       |    -  **DOWN** (Unbound)                                                                                                                                                |
      |                       |                       |    -  **ACTIVE** (Bound)                                                                                                                                                |
      |                       |                       |    -  **ELB** (Bound to a load balancer)                                                                                                                                |
      |                       |                       |    -  **ERROR** (Exceptions)                                                                                                                                            |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | profile               | Object                | Specifies the additional parameters, including the order ID and product ID. For details, see :ref:`Table 4 <eip_api_0003__en-us_topic_0201534309_table66651219193417>`. |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       | This parameter is not supported currently.                                                                                                                              |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                | -  Specifies the EIP type.                                                                                                                                              |
      |                       |                       | -  The value can be **5_bgp** (Dynamic BGP) or **5_mailbgp** (Mail BGP).                                                                                                |
      |                       |                       | -  Constraints:                                                                                                                                                         |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    -  The configured value must be supported by the system.                                                                                                             |
      |                       |                       |    -  **publicip_id** is an IPv4 port. If **publicip_type** is not specified, the default value is **5_bgp**.                                                           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | public_ip_address     | String                | Specifies the obtained EIP if only IPv4 EIPs are available.                                                                                                             |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ip_version            | Integer               | Specifies the IP address version. The value can be **4** or **6**.                                                                                                      |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       | -  **4**: IPv4                                                                                                                                                          |
      |                       |                       | -  **6**: IPv6 (IPv6 is not supported currently.)                                                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | private_ip_address    | String                | -  Specifies the private IP address bound to the EIP.                                                                                                                   |
      |                       |                       | -  This parameter is returned only if the private IP address is bound to the EIP.                                                                                       |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       | .. note::                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    The value of **private_ip_address** is **null** if the EIP is bound to a dedicated load balancer.                                                                    |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | port_id               | String                | -  Specifies the port ID.                                                                                                                                               |
      |                       |                       | -  This parameter is returned only when a port is associated with the EIP.                                                                                              |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       | .. note::                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    The value of **port_id** is null if the EIP is bound to a dedicated load balancer.                                                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tenant_id             | String                | Specifies the project ID.                                                                                                                                               |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | create_time           | String                | Specifies the time (UTC) when the EIP is assigned.                                                                                                                      |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_id          | String                | Specifies the ID of the EIP bandwidth.                                                                                                                                  |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_size        | Integer               | Specifies the bandwidth (Mbit/s).                                                                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_share_type  | String                | -  Specifies the EIP bandwidth type.                                                                                                                                    |
      |                       |                       | -  The value can be **PER** or **WHOLE**.                                                                                                                               |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    -  **PER**: Dedicated bandwidth                                                                                                                                      |
      |                       |                       |    -  **WHOLE**: Shared bandwidth                                                                                                                                       |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_name        | String                | Specifies the bandwidth name.                                                                                                                                           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                | -  Specifies the enterprise project ID. The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-).                        |
      |                       |                       | -  When assigning an EIP, you need to associate an enterprise project ID with the EIP.                                                                                  |
      |                       |                       | -  If this parameter is not specified, the default value is **0**, which indicates that the default enterprise project is used.                                         |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       | .. note::                                                                                                                                                               |
      |                       |                       |                                                                                                                                                                         |
      |                       |                       |    This parameter is unsupported. Do not use it.                                                                                                                        |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0003__en-us_topic_0201534309_table66651219193417:

   .. table:: **Table 4** Description of the **profile** field

      ========== ====== =========================
      Name       Type   Description
      ========== ====== =========================
      order_id   String Specifies the order ID.
      product_id String Specifies the product ID.
      region_id  String Specifies the region ID.
      user_id    String Specifies the user ID.
      ========== ====== =========================

-  Example response

   .. code-block::

      {
          "publicips": [
              {
                  "id": "6285e7be-fd9f-497c-bc2d-dd0bdea6efe0",
                  "status": "DOWN",
                  "profile": {},
                  "type": "5_bgp",
                  "public_ip_address": "161.xx.xx.9",
                  "private_ip_address": "192.168.10.5",
                  "tenant_id": "8b7e35ad379141fc9df3e178bd64f55c",
                  "create_time": "2015-07-16 04:22:32",
                  "bandwidth_id": "3fa5b383-5a73-4dcb-a314-c6128546d855",
                  "bandwidth_share_type": "PER",
                  "bandwidth_size": 5,
                  "bandwidth_name": "bandwidth-test",
                  "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439",
                  "ip_version": 4
              },
              {
                  "id": "80d5b82e-43b9-4f82-809a-37bec5793bd4",
                  "status": "DOWN",
                  "profile": {},
                  "type": "5_bgp",
                  "public_ip_address": "161.xx.xx.10",
                  "private_ip_address": "192.168.10.6",
                  "tenant_id": "8b7e35ad379141fc9df3e178bd64f55c",
                  "create_time": "2015-07-16 04:23:03",
                  "bandwidth_id": "a79fd11a-047b-4f5b-8f12-99c178cc780a",
                  "bandwidth_share_type": "PER",
                  "bandwidth_size": 5,
                  "bandwidth_name": "bandwidth-test1",
                  "enterprise_project_id":"0",
                  "ip_version": 4
              }
          ]
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
