:original_name: eip_api_0001.html

.. _eip_api_0001:

Assigning an EIP
================

Function
--------

This API is used to assign an EIP.

The EIP service provides independent public IP addresses and bandwidth for Internet access. EIPs can be bound to or unbound from ECSs, BMSs, virtual IP addresses, load balancers, and NAT gateways.

URI
---

POST /v1/{project_id}/publicips

:ref:`Table 1 <eip_api_0001__en-us_topic_0201534274_table57311924>` describes the parameters.

.. _eip_api_0001__en-us_topic_0201534274_table57311924:

.. table:: **Table 1** Parameter description

   ========== ========= =========================
   Name       Mandatory Description
   ========== ========= =========================
   project_id Yes       Specifies the project ID.
   ========== ========= =========================

Request Message
---------------

-  Request parameter

   .. table:: **Table 2** Request parameter

      +-----------------------+-----------------+------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Mandatory       | Type                                                                         | Description                                                                                                                                      |
      +=======================+=================+==============================================================================+==================================================================================================================================================+
      | publicip              | Yes             | :ref:`publicip <eip_api_0001__en-us_topic_0201534274_table4491214>` object   | Specifies the EIP object. For details, see :ref:`Table 3 <eip_api_0001__en-us_topic_0201534274_table4491214>`.                                   |
      +-----------------------+-----------------+------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth             | Yes             | :ref:`bandwidth <eip_api_0001__en-us_topic_0201534274_table11041789>` object | Specifies the bandwidth object. For details, see :ref:`Table 4 <eip_api_0001__en-us_topic_0201534274_table11041789>`.                            |
      +-----------------------+-----------------+------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | No              | String                                                                       | -  Specifies the enterprise project ID. The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-). |
      |                       |                 |                                                                              | -  When you assign an EIP, associate an enterprise project ID with the EIP.                                                                      |
      |                       |                 |                                                                              | -  If this parameter is not specified, the default value is **0**, which indicates that the default enterprise project is used.                  |
      |                       |                 |                                                                              |                                                                                                                                                  |
      |                       |                 |                                                                              | .. note::                                                                                                                                        |
      |                       |                 |                                                                              |                                                                                                                                                  |
      |                       |                 |                                                                              |    This parameter is unsupported. Do not use it.                                                                                                 |
      +-----------------------+-----------------+------------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0001__en-us_topic_0201534274_table4491214:

   .. table:: **Table 3** Description of the **publicip** field

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | Name            | Mandatory       | Type            | Description                                                                                                                           |
      +=================+=================+=================+=======================================================================================================================================+
      | type            | Yes             | String          | -  Specifies the EIP type.                                                                                                            |
      |                 |                 |                 | -  The value can be **5_bgp** (Dynamic BGP), **5_mailbgp** (Mail BGP), or **5_gray** (Dedicated load balancer, shared load balancer). |
      |                 |                 |                 | -  Constraints:                                                                                                                       |
      |                 |                 |                 |                                                                                                                                       |
      |                 |                 |                 |    -  The configured value must be supported by the system.                                                                           |
      |                 |                 |                 |    -  **publicip_id** is an IPv4 port. If **publicip_type** is not specified, the default value is **5_bgp**.                         |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | ip_address      | No              | String          | -  Specifies the EIP to be assigned. The system automatically assigns an EIP if you do not specify it.                                |
      |                 |                 |                 | -  The value must be a valid IPv4 address in the available IP address range.                                                          |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0001__en-us_topic_0201534274_table11041789:

   .. table:: **Table 4** Description of the **bandwidth** field

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name            | Mandatory       | Type            | Description                                                                                                                                                                                                         |
      +=================+=================+=================+=====================================================================================================================================================================================================================+
      | name            | Yes             | String          | -  Specifies the bandwidth name.                                                                                                                                                                                    |
      |                 |                 |                 | -  The value can contain 1 to 64 characters, including letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                              |
      |                 |                 |                 | -  This parameter is mandatory when **share_type** is set to **PER**. This parameter will be ignored when **share_type** is set to **WHOLE** with an ID specified.                                                  |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | size            | Yes             | Integer         | -  Specifies the bandwidth size.                                                                                                                                                                                    |
      |                 |                 |                 | -  The value ranges from 1 Mbit/s to 1000 Mbit/s by default. (The specific range may vary depending on the configuration in each region. You can see the bandwidth range of each region on the management console.) |
      |                 |                 |                 | -  This parameter is mandatory when **share_type** is set to **PER**. This parameter will be ignored when **share_type** is set to **WHOLE** with an ID specified.                                                  |
      |                 |                 |                 | -  The minimum increment for bandwidth adjustment varies depending on the bandwidth range. The details are as follows:                                                                                              |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 |    -  The minimum increment is 1 Mbit/s if the allowed bandwidth ranges from 0 Mbit/s to 300 Mbit/s (with 300 Mbit/s included).                                                                                     |
      |                 |                 |                 |    -  The minimum increment is 50 Mbit/s if the allowed bandwidth ranges from 300 Mbit/s to 1000 Mbit/s (with 1000 Mbit/s included).                                                                                |
      |                 |                 |                 |    -  The minimum increment is 500 Mbit/s if the allowed bandwidth is greater than 1000 Mbit/s.                                                                                                                     |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | id              | No              | String          | -  Specifies the bandwidth ID. You can specify an existing shared bandwidth when assigning an EIP.                                                                                                                  |
      |                 |                 |                 | -  The value can be the ID of the shared bandwidth whose type is set to **WHOLE**.                                                                                                                                  |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | share_type      | Yes             | String          | -  Specifies the bandwidth type.                                                                                                                                                                                    |
      |                 |                 |                 | -  Possible values are as follows:                                                                                                                                                                                  |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 |    -  **PER**: Dedicated bandwidth                                                                                                                                                                                  |
      |                 |                 |                 |    -  **WHOLE**: Shared bandwidth                                                                                                                                                                                   |
      |                 |                 |                 |                                                                                                                                                                                                                     |
      |                 |                 |                 | -  If this parameter is set to **WHOLE**, the bandwidth ID must be specified.                                                                                                                                       |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | charge_mode     | No              | String          | -  The value is **traffic**, indicating that the billing is based on traffic.                                                                                                                                       |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request (IPv4 EIP with dedicated bandwidth)

   .. code-block:: text

      POST https://{Endpoint}/v1/{project_id}/publicips

      {
          "publicip": {
              "type": "5_bgp",
              "ip_version": 4
          },
          "bandwidth": {
              "name": "bandwidth123",
              "size": 10,
              "share_type": "PER"
          },
          "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439"
      }

Response Message
----------------

-  Response parameter

   .. table:: **Table 5** Response parameter

      +----------+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+
      | Name     | Type                                                                        | Description                                                                                                     |
      +==========+=============================================================================+=================================================================================================================+
      | publicip | :ref:`publicip <eip_api_0001__en-us_topic_0201534274_table44471219>` object | Specifies the EIP object. For details, see :ref:`Table 6 <eip_api_0001__en-us_topic_0201534274_table44471219>`. |
      +----------+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0001__en-us_topic_0201534274_table44471219:

   .. table:: **Table 6** Description of the **publicip** field

      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================+
      | id                    | String                | Specifies the unique identifier of an EIP.                                                                                                       |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                | -  Specifies the EIP status.                                                                                                                     |
      |                       |                       | -  Possible values are as follows:                                                                                                               |
      |                       |                       |                                                                                                                                                  |
      |                       |                       |    -  **FREEZED** (Frozen)                                                                                                                       |
      |                       |                       |    -  **BIND_ERROR** (Binding failed)                                                                                                            |
      |                       |                       |    -  **BINDING** (Binding)                                                                                                                      |
      |                       |                       |    -  **PENDING_DELETE** (Releasing)                                                                                                             |
      |                       |                       |    -  **PENDING_CREATE** (Assigning)                                                                                                             |
      |                       |                       |    -  **PENDING_UPDATE** (Updating)                                                                                                              |
      |                       |                       |    -  **DOWN** (Unbound)                                                                                                                         |
      |                       |                       |    -  **ACTIVE** (Bound)                                                                                                                         |
      |                       |                       |    -  **ELB** (Bound to a load balancer)                                                                                                         |
      |                       |                       |    -  **ERROR** (Exceptions)                                                                                                                     |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                | -  Specifies the EIP type.                                                                                                                       |
      |                       |                       | -  The value can be **5_bgp** (Dynamic BGP), **5_mailbgp** (Mail BGP), or **5_gray** (Dedicated load balancer, shared load balancer).            |
      |                       |                       | -  Constraints:                                                                                                                                  |
      |                       |                       |                                                                                                                                                  |
      |                       |                       |    -  The configured value must be supported by the system.                                                                                      |
      |                       |                       |    -  **publicip_id** is an IPv4 port. If **publicip_type** is not specified, the default value is **5_bgp**.                                    |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | public_ip_address     | String                | Specifies the obtained EIP if only IPv4 EIPs are available.                                                                                      |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | ip_version            | Integer               | Specifies the IP address version. The value can be **4** or **6**.                                                                               |
      |                       |                       |                                                                                                                                                  |
      |                       |                       | -  **4**: IPv4                                                                                                                                   |
      |                       |                       | -  **6**: IPv6 (IPv6 is not supported currently.)                                                                                                |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | tenant_id             | String                | Specifies the project ID.                                                                                                                        |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | create_time           | String                | Specifies the time (UTC) when the EIP is assigned.                                                                                               |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_size        | Integer               | Specifies the bandwidth (Mbit/s).                                                                                                                |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                | -  Specifies the enterprise project ID. The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-). |
      |                       |                       | -  When you assign an EIP, associate an enterprise project ID with the EIP.                                                                      |
      |                       |                       | -  If this parameter is not specified, the default value is **0**, which indicates that the default enterprise project is used.                  |
      |                       |                       |                                                                                                                                                  |
      |                       |                       | .. note::                                                                                                                                        |
      |                       |                       |                                                                                                                                                  |
      |                       |                       |    This parameter is unsupported. Do not use it.                                                                                                 |
      +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example response (IPv4 EIP with dedicated bandwidth)

   .. code-block::

      {
          "publicip": {
              "id": "f588ccfa-8750-4d7c-bf5d-2ede24414706",
              "status": "PENDING_CREATE",
              "type": "5_bgp",
              "public_ip_address": "161.xx.xx.7",
              "tenant_id": "8b7e35ad379141fc9df3e178bd64f55c",
              "ip_version": 4,
              "create_time": "2015-07-16 04:10:52",
              "bandwidth_size": 0,
              "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439"
          }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <eip_api05_0002>`.
