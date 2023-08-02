:original_name: eip_api_0002.html

.. _eip_api_0002:

Querying an EIP
===============

Function
--------

This API is used to query a specific EIP.

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

GET /v1/{project_id}/publicips/{publicip_id}

:ref:`Table 1 <eip_api_0002__en-us_topic_0201534285_table57982344>` describes the parameters.

.. _eip_api_0002__en-us_topic_0201534285_table57982344:

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

   .. code-block::

      Get https://{Endpoint}/v1/{project_id}/publicips/{publicip_id}

Response Message
----------------

-  Response parameter

   .. table:: **Table 2** Response parameter

      +----------+----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------+
      | Name     | Type                                                                       | Description                                                                                                    |
      +==========+============================================================================+================================================================================================================+
      | publicip | :ref:`publicip <eip_api_0002__en-us_topic_0201534285_table3035698>` object | Specifies the EIP object. For details, see :ref:`Table 3 <eip_api_0002__en-us_topic_0201534285_table3035698>`. |
      +----------+----------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0002__en-us_topic_0201534285_table3035698:

   .. table:: **Table 3** Description of the **publicip** field

      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                                                                             | Description                                                                                                                                                                           |
      +=======================+==================================================================================+=======================================================================================================================================================================================+
      | id                    | String                                                                           | Specifies the unique identifier of an EIP.                                                                                                                                            |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | status                | String                                                                           | -  Specifies the EIP status.                                                                                                                                                          |
      |                       |                                                                                  | -  Possible values are as follows:                                                                                                                                                    |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    -  **FREEZED** (Frozen)                                                                                                                                                            |
      |                       |                                                                                  |    -  **BIND_ERROR** (Binding failed)                                                                                                                                                 |
      |                       |                                                                                  |    -  **BINDING** (Binding)                                                                                                                                                           |
      |                       |                                                                                  |    -  **PENDING_DELETE** (Releasing)                                                                                                                                                  |
      |                       |                                                                                  |    -  **PENDING_CREATE** (Assigning)                                                                                                                                                  |
      |                       |                                                                                  |    -  **PENDING_UPDATE** (Updating)                                                                                                                                                   |
      |                       |                                                                                  |    -  **NOTIFYING** (Assigning)                                                                                                                                                       |
      |                       |                                                                                  |    -  **NOTIFY_DELETE** (Releasing)                                                                                                                                                   |
      |                       |                                                                                  |    -  **DOWN** (Unbound)                                                                                                                                                              |
      |                       |                                                                                  |    -  **ACTIVE** (Bound)                                                                                                                                                              |
      |                       |                                                                                  |    -  **ELB** (Bound to a load balancer)                                                                                                                                              |
      |                       |                                                                                  |    -  **VPN** (Bound to a VPN)                                                                                                                                                        |
      |                       |                                                                                  |    -  **ERROR** (Exceptions)                                                                                                                                                          |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | profile               | :ref:`profile <eip_api_0002__en-us_topic_0201534285_table66651219193417>` object | Specifies the additional parameters, including the order ID and product ID. For details, see :ref:`Table 4 <eip_api_0002__en-us_topic_0201534285_table66651219193417>`.               |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  | This parameter is not supported currently.                                                                                                                                            |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | type                  | String                                                                           | -  Specifies the EIP type.                                                                                                                                                            |
      |                       |                                                                                  | -  The value can be **5_bgp** (Dynamic BGP) or **5_mailbgp** (Mail BGP).                                                                                                              |
      |                       |                                                                                  | -  Constraints:                                                                                                                                                                       |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    -  The configured value must be supported by the system.                                                                                                                           |
      |                       |                                                                                  |    -  **publicip_id** is an IPv4 port. If **publicip_type** is not specified, the default value is **5_bgp**.                                                                         |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | public_ip_address     | String                                                                           | Specifies the obtained EIP if only IPv4 EIPs are available. Specifies the IPv4 address corresponding to the IPv6 address if IPv6 EIPs are available. IPv6 is not supported currently. |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ip_version            | Integer                                                                          | Specifies the IP address version. The value can be **4** or **6**.                                                                                                                    |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  | -  **4**: IPv4                                                                                                                                                                        |
      |                       |                                                                                  | -  **6**: IPv6 (IPv6 is not supported currently.)                                                                                                                                     |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | private_ip_address    | String                                                                           | -  Specifies the private IP address bound to the EIP.                                                                                                                                 |
      |                       |                                                                                  | -  This parameter is returned only if the private IP address is bound to the EIP.                                                                                                     |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  | .. note::                                                                                                                                                                             |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    The value of **private_ip_address** is **null** if the EIP is bound to a dedicated load balancer.                                                                                  |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | port_id               | String                                                                           | -  Specifies the port ID.                                                                                                                                                             |
      |                       |                                                                                  | -  This parameter is returned only when a port is associated with the EIP.                                                                                                            |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  | .. note::                                                                                                                                                                             |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    The value of **port_id** is null if the EIP is bound to a dedicated load balancer.                                                                                                 |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | tenant_id             | String                                                                           | Specifies the project ID.                                                                                                                                                             |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | create_time           | String                                                                           | Specifies the time (UTC) when the EIP is assigned.                                                                                                                                    |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_id          | String                                                                           | Specifies the ID of the EIP bandwidth.                                                                                                                                                |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_size        | Integer                                                                          | Specifies the bandwidth (Mbit/s).                                                                                                                                                     |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_share_type  | String                                                                           | -  Specifies the EIP bandwidth type.                                                                                                                                                  |
      |                       |                                                                                  | -  The value can be **PER** or **WHOLE**.                                                                                                                                             |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    -  **PER**: Dedicated bandwidth                                                                                                                                                    |
      |                       |                                                                                  |    -  **WHOLE**: Shared bandwidth                                                                                                                                                     |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | bandwidth_name        | String                                                                           | Specifies the bandwidth name.                                                                                                                                                         |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | enterprise_project_id | String                                                                           | -  Specifies the enterprise project ID. The value is **0** or a string that contains a maximum of 36 characters in UUID format with hyphens (-).                                      |
      |                       |                                                                                  | -  When assigning an EIP, you need to associate an enterprise project ID with the EIP.                                                                                                |
      |                       |                                                                                  | -  If this parameter is not specified, the default value is **0**, which indicates that the default enterprise project is used.                                                       |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  | .. note::                                                                                                                                                                             |
      |                       |                                                                                  |                                                                                                                                                                                       |
      |                       |                                                                                  |    This parameter is unsupported. Do not use it.                                                                                                                                      |
      +-----------------------+----------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_api_0002__en-us_topic_0201534285_table66651219193417:

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
          "publicip": {
              "id": "2ec9b78d-9368-46f3-8f29-d1a95622a568",
              "status": "DOWN",
              "profile": {},
              "type": "5_bgp",
              "public_ip_address": "161.xx.xx.12",
              "tenant_id": "8b7e35ad379141fc9df3e178bd64f55c",
              "private_ip_address": "192.168.10.5",
              "create_time": "2015-07-16 04:32:50",
              "bandwidth_id": "49c8825b-bed9-46ff-9416-704b96d876a2",
              "bandwidth_share_type": "PER",
      "bandwidth_size": 10,    //The EIP bandwidth size is 10 Mbit/s.
              "bandwidth_name": "bandwidth-test",
              "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439",
              "ip_version": 4
          }
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
