:original_name: eip_apisharedbandwidth_0001.html

.. _eip_apisharedbandwidth_0001:

Assigning a Shared Bandwidth
============================

Function
--------

This API is used to assign a shared bandwidth.

URI
---

POST /v2.0/{project_id}/bandwidths

:ref:`Table 1 <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table40002310>` describes the parameters.

.. _eip_apisharedbandwidth_0001__en-us_topic_0201534115_table40002310:

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

      +-----------+-----------+---------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | Name      | Mandatory | Type                                                                                        | Description                                                                                                                           |
      +===========+===========+=============================================================================================+=======================================================================================================================================+
      | bandwidth | Yes       | :ref:`bandwidth <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table11041789>` object | Specifies the bandwidth objects. For details, see :ref:`Table 3 <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table11041789>`. |
      +-----------+-----------+---------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apisharedbandwidth_0001__en-us_topic_0201534115_table11041789:

   .. table:: **Table 3** Description of the **bandwidth** field

      +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Mandatory       | Type            | Description                                                                                                                                                                                                    |
      +=======================+=================+=================+================================================================================================================================================================================================================+
      | name                  | Yes             | String          | -  Specifies the bandwidth name.                                                                                                                                                                               |
      |                       |                 |                 | -  The value can contain 1 to 64 characters, including letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                         |
      +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | size                  | Yes             | Integer         | -  Specifies the bandwidth size. The shared bandwidth has a minimum limit, which may vary depending on sites. The default minimum value is 5 Mbit/s.                                                           |
      |                       |                 |                 | -  The value ranges from 1 Mbit/s to 1000 Mbit/s by default. (The specific range may vary depending on the configuration in each region. You can see the available bandwidth range on the management console.) |
      |                       |                 |                 | -  If a decimal fraction (for example **10.2**) or a character string (for example **"10"**) is specified, the specified value will be automatically converted to an integer.                                  |
      |                       |                 |                 | -  The minimum increment for bandwidth adjustment varies depending on the bandwidth range. The details are as follows:                                                                                         |
      |                       |                 |                 |                                                                                                                                                                                                                |
      |                       |                 |                 |    -  The minimum increment is 1 Mbit/s if the allowed bandwidth ranges from 0 Mbit/s to 300 Mbit/s (with 300 Mbit/s included).                                                                                |
      |                       |                 |                 |    -  The minimum increment is 50 Mbit/s if the allowed bandwidth ranges from 300 Mbit/s to 1000 Mbit/s (with 1000 Mbit/s included).                                                                           |
      |                       |                 |                 |    -  The minimum increment is 500 Mbit/s if the allowed bandwidth is greater than 1000 Mbit/s.                                                                                                                |
      +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | No              | String          | -  Specifies the enterprise project ID. The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-). Value **0** indicates the default enterprise project.         |
      |                       |                 |                 | -  When creating a shared bandwidth, associate the enterprise project ID with the shared bandwidth.                                                                                                            |
      |                       |                 |                 |                                                                                                                                                                                                                |
      |                       |                 |                 | .. note::                                                                                                                                                                                                      |
      |                       |                 |                 |                                                                                                                                                                                                                |
      |                       |                 |                 |    This parameter is unsupported. Do not use it.                                                                                                                                                               |
      +-----------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v2.0/{project_id}/bandwidths

      {
          "bandwidth": {
              "name": "bandwidth123",
              "size": 10,
              "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439"
          }
      }

Response Message
----------------

-  Response parameter

   .. table:: **Table 4** Response parameter

      +-----------+---------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
      | Name      | Type                                                                                        | Description                                                                                                                           |
      +===========+=============================================================================================+=======================================================================================================================================+
      | bandwidth | :ref:`bandwidth <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table60972066>` object | Specifies the bandwidth objects. For details, see :ref:`Table 5 <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table60972066>`. |
      +-----------+---------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apisharedbandwidth_0001__en-us_topic_0201534115_table60972066:

   .. table:: **Table 5** Description of the **bandwidth** field

      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                                                                                                      | Description                                                                                                                                                                                                    |
      +=======================+===========================================================================================================+================================================================================================================================================================================================================+
      | name                  | String                                                                                                    | -  Specifies the bandwidth name.                                                                                                                                                                               |
      |                       |                                                                                                           | -  The value can contain 1 to 64 characters, including letters, digits, underscores (_), hyphens (-), and periods (.).                                                                                         |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | size                  | Integer                                                                                                   | -  Specifies the bandwidth size.                                                                                                                                                                               |
      |                       |                                                                                                           | -  The value ranges from 1 Mbit/s to 1000 Mbit/s by default. (The specific range may vary depending on the configuration in each region. You can see the available bandwidth range on the management console.) |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | id                    | String                                                                                                    | Specifies the bandwidth ID, which uniquely identifies the bandwidth.                                                                                                                                           |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | share_type            | String                                                                                                    | -  Specifies whether the bandwidth is shared or dedicated.                                                                                                                                                     |
      |                       |                                                                                                           | -  The value can be **PER** or **WHOLE**.                                                                                                                                                                      |
      |                       |                                                                                                           |                                                                                                                                                                                                                |
      |                       |                                                                                                           |    -  **WHOLE**: Shared bandwidth                                                                                                                                                                              |
      |                       |                                                                                                           |    -  **PER**: Dedicated bandwidth                                                                                                                                                                             |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | publicip_info         | Array of :ref:`publicip_info <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table30936422>` objects | -  Specifies information about the EIP that uses the bandwidth. For details, see :ref:`Table 6 <eip_apisharedbandwidth_0001__en-us_topic_0201534115_table30936422>`.                                           |
      |                       |                                                                                                           | -  The bandwidth, whose type is **WHOLE**, can be used by multiple EIPs. The bandwidth, whose type is **PER**, can be used by only one EIP.                                                                    |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tenant_id             | String                                                                                                    | Specifies the project ID.                                                                                                                                                                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_type        | String                                                                                                    | -  Specifies the bandwidth type. The default value for the shared bandwidth is **share**.                                                                                                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | charge_mode           | String                                                                                                    | -  Specifies that the bandwidth is billed by bandwidth.                                                                                                                                                        |
      |                       |                                                                                                           | -  The value can be **traffic**.                                                                                                                                                                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | billing_info          | String                                                                                                    | Specifies the bill information.                                                                                                                                                                                |
      |                       |                                                                                                           |                                                                                                                                                                                                                |
      |                       |                                                                                                           | If **billing_info** is specified, the bandwidth is in yearly/monthly billing mode.                                                                                                                             |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                                                                                                    | -  Specifies the enterprise project ID. The value is **0** or a UUID that can contain a maximum of 36 characters, including hyphens (-). Value **0** indicates the default enterprise project.                 |
      |                       |                                                                                                           | -  When creating a shared bandwidth, associate the enterprise project ID with the shared bandwidth.                                                                                                            |
      |                       |                                                                                                           |                                                                                                                                                                                                                |
      |                       |                                                                                                           | .. note::                                                                                                                                                                                                      |
      |                       |                                                                                                           |                                                                                                                                                                                                                |
      |                       |                                                                                                           |    This parameter is unsupported. Do not use it.                                                                                                                                                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                                                                                                    | -  Specifies the bandwidth status.                                                                                                                                                                             |
      |                       |                                                                                                           | -  Possible values are as follows:                                                                                                                                                                             |
      |                       |                                                                                                           |                                                                                                                                                                                                                |
      |                       |                                                                                                           |    -  **FREEZED** (Frozen)                                                                                                                                                                                     |
      |                       |                                                                                                           |    -  **NORMAL** (Normal)                                                                                                                                                                                      |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | created_at            | String                                                                                                    | -  Specifies the time (UTC) when the bandwidth is created.                                                                                                                                                     |
      |                       |                                                                                                           | -  Format: *yyyy-MM-ddTHH:mm:ss*                                                                                                                                                                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | updated_at            | String                                                                                                    | -  Specifies the time (UTC) when the bandwidth is updated.                                                                                                                                                     |
      |                       |                                                                                                           | -  Format: *yyyy-MM-ddTHH:mm:ss*                                                                                                                                                                               |
      +-----------------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apisharedbandwidth_0001__en-us_topic_0201534115_table30936422:

   .. table:: **Table 6** **publicip_info** object

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                   |
      +=======================+=======================+===============================================================================================================+
      | publicip_id           | String                | Specifies the ID of the EIP that uses the bandwidth.                                                          |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------+
      | publicip_address      | String                | Specifies the obtained EIP if only IPv4 EIPs are available.                                                   |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------+
      | publicip_type         | String                | -  Specifies the EIP type.                                                                                    |
      |                       |                       | -  The value can be **5_bgp** (Dynamic BGP) or **5_mailbgp** (Mail BGP).                                      |
      |                       |                       | -  Constraints:                                                                                               |
      |                       |                       |                                                                                                               |
      |                       |                       |    -  The configured value must be supported by the system.                                                   |
      |                       |                       |    -  **publicip_id** is an IPv4 port. If **publicip_type** is not specified, the default value is **5_bgp**. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
        "bandwidth": {
          "id": "1bffc5f2-ff19-45a6-96d2-dfdca49cc387",
          "name": "bandwidth123",
          "size": 10,
          "share_type": "WHOLE",
          "publicip_info": [],
          "tenant_id": "26ae5181a416420998eb2093aaed84d9",
          "bandwidth_type": "share",
          "charge_mode": "traffic",
          "billing_info": "",
          "enterprise_project_id": "0",
          "status": "NORMAL",
          "created_at": "2020-04-21T07:58:02Z",
          "updated_at": "2020-04-21T07:58:02Z"
        }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
