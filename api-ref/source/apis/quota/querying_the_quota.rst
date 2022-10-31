:original_name: eip_apiquota_0001.html

.. _eip_apiquota_0001:

Querying the Quota
==================

Function
--------

This API is used to query network resource quotas of a tenant. The network resources include VPCs, subnets, security groups, security group rules, EIPs, and VPNs.

.. note::

   This API is used to query both the EIP and VPC quotas.

URI
---

GET /v1/{project_id}/quotas

Example:

.. code-block:: text

   GET https://{Endpoint}/v1/{project_id}/quotas?type={type}

:ref:`Table 1 <eip_apiquota_0001__en-us_topic_0201534147_table38014313>` describes the parameters.

.. _eip_apiquota_0001__en-us_topic_0201534147_table38014313:

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------+
   | Name            | Mandatory       | Type            | Description                     |
   +=================+=================+=================+=================================+
   | project_id      | Yes             | String          | Specifies the project ID.       |
   +-----------------+-----------------+-----------------+---------------------------------+
   | type            | No              | String          | -  Specifies the resource type. |
   |                 |                 |                 | -  Values:                      |
   |                 |                 |                 |                                 |
   |                 |                 |                 |    -  vpc                       |
   |                 |                 |                 |    -  subnet                    |
   |                 |                 |                 |    -  securityGroup             |
   |                 |                 |                 |    -  securityGroupRule         |
   |                 |                 |                 |    -  publicIp                  |
   |                 |                 |                 |    -  vpn                       |
   |                 |                 |                 |    -  vpngw                     |
   |                 |                 |                 |    -  vpcPeer                   |
   |                 |                 |                 |    -  loadbalancer              |
   |                 |                 |                 |    -  listener                  |
   |                 |                 |                 |    -  physicalConnect           |
   |                 |                 |                 |    -  virtualInterface          |
   |                 |                 |                 |    -  firewall                  |
   |                 |                 |                 |    -  shareBandwidthIP          |
   |                 |                 |                 |    -  shareBandwidth            |
   |                 |                 |                 |    -  address_group             |
   |                 |                 |                 |    -  flow_log                  |
   |                 |                 |                 |    -  vpcContainRoutetable      |
   |                 |                 |                 |    -  routetableContainRoutes   |
   +-----------------+-----------------+-----------------+---------------------------------+

Request Message
---------------

-  Request parameter

   .. code-block:: text

      None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v1/{project_id}/quotas

Response Message
----------------

-  Response parameter

   .. table:: **Table 2** Response parameter

      +--------+--------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
      | Name   | Type                                                                                 | Description                                                                                                                  |
      +========+======================================================================================+==============================================================================================================================+
      | quotas | :ref:`quotas <eip_apiquota_0001__en-us_topic_0201534147_table11308015155544>` object | Specifies the quota object. For details, see :ref:`Table 3 <eip_apiquota_0001__en-us_topic_0201534147_table11308015155544>`. |
      +--------+--------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apiquota_0001__en-us_topic_0201534147_table11308015155544:

   .. table:: **Table 3** Description of the **quotas** field

      +-----------+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+
      | Name      | Type                                                                                      | Description                                                                                                               |
      +===========+===========================================================================================+===========================================================================================================================+
      | resources | Array of :ref:`resource <eip_apiquota_0001__en-us_topic_0201534147_table8208684>` objects | Specifies the resource objects. For details, see :ref:`Table 4 <eip_apiquota_0001__en-us_topic_0201534147_table8208684>`. |
      +-----------+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apiquota_0001__en-us_topic_0201534147_table8208684:

   .. table:: **Table 4** Description of the **resource** field

      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------+
      | Name                  | Type                  | Description                                                                                                 |
      +=======================+=======================+=============================================================================================================+
      | type                  | String                | -  Specifies the resource type.                                                                             |
      |                       |                       | -  Values:                                                                                                  |
      |                       |                       |                                                                                                             |
      |                       |                       |    -  vpc                                                                                                   |
      |                       |                       |    -  subnet                                                                                                |
      |                       |                       |    -  securityGroup                                                                                         |
      |                       |                       |    -  securityGroupRule                                                                                     |
      |                       |                       |    -  publicIp                                                                                              |
      |                       |                       |    -  vpn                                                                                                   |
      |                       |                       |    -  vpngw                                                                                                 |
      |                       |                       |    -  vpcPeer                                                                                               |
      |                       |                       |    -  loadbalancer                                                                                          |
      |                       |                       |    -  listener                                                                                              |
      |                       |                       |    -  physicalConnect                                                                                       |
      |                       |                       |    -  virtualInterface                                                                                      |
      |                       |                       |    -  firewall                                                                                              |
      |                       |                       |    -  shareBandwidthIP                                                                                      |
      |                       |                       |    -  shareBandwidth                                                                                        |
      |                       |                       |    -  address_group                                                                                         |
      |                       |                       |    -  flow_log                                                                                              |
      |                       |                       |    -  vpcContainRoutetable                                                                                  |
      |                       |                       |    -  routetableContainRoutes                                                                               |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------+
      | used                  | Integer               | -  Specifies the number of created network resources.                                                       |
      |                       |                       | -  The value ranges from **0** to the value of **quota**.                                                   |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------+
      | quota                 | Integer               | -  Specifies the maximum quota values for the resources.                                                    |
      |                       |                       |                                                                                                             |
      |                       |                       | -  The value ranges from the default quota value to the maximum quota value.                                |
      |                       |                       |                                                                                                             |
      |                       |                       | -  The default quota values can be changed. Configure the quota values in the underlying system in advance. |
      |                       |                       |                                                                                                             |
      |                       |                       |    Default quota values:                                                                                    |
      |                       |                       |                                                                                                             |
      |                       |                       |    -  VPC: 150                                                                                              |
      |                       |                       |    -  Subnet: 400                                                                                           |
      |                       |                       |    -  Security group: 100                                                                                   |
      |                       |                       |    -  Security group rule: 5000                                                                             |
      |                       |                       |    -  EIPs: 10                                                                                              |
      |                       |                       |    -  VPNs: 5                                                                                               |
      |                       |                       |    -  VPC peering connections: 50                                                                           |
      |                       |                       |    -  Load balancers: 10                                                                                    |
      |                       |                       |    -  Listeners: 10                                                                                         |
      |                       |                       |    -  Firewalls: 200                                                                                        |
      |                       |                       |    -  EIPs that can be added to a shared bandwidth: 20                                                      |
      |                       |                       |    -  Shared bandwidths: 5                                                                                  |
      |                       |                       |    -  IP address groups: 50                                                                                 |
      |                       |                       |    -  Route table per VPC: 1                                                                                |
      |                       |                       |    -  Routes per route table: 200                                                                           |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------+
      | min                   | Integer               | Specifies the minimum quota value allowed.                                                                  |
      +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "quotas": {
              "resources": [
                  {
                      "type": "vpc",
                      "used": 4,
                      "quota": 150,
                      "min": 0
                  },
                  {
                      "type": "subnet",
                      "used": 5,
                      "quota": 400,
                      "min": 0
                  },
                  {
                      "type": "securityGroup",
                      "used": 1,
                      "quota": 100,
                      "min": 0
                  },
                  {
                      "type": "securityGroupRule",
                      "used": 6,
                      "quota": 5000,
                      "min": 0
                  },
                  {
                      "type": "publicIp",
                      "used": 2,
                      "quota": 10,
                      "min": 0
                  },
                  {
                      "type": "vpn",
                      "used": 0,
                      "quota": 5,
                      "min": 0
                  },
                  {
                      "type": "vpcPeer",
                      "used": 0,
                      "quota": 50,
                      "min": 0
                  },
                  {
                      "type": "firewall",
                      "used": 0,
                      "quota": 200,
                      "min": 0
                  },
                  {
                      "type": "shareBandwidth",
                      "used": 0,
                      "quota": 5,
                      "min": 0
                  },
                  {
                      "type": "shareBandwidthIP",
                      "used": 0,
                      "quota": 20,
                      "min": 0
                  },
                  {
                      "type": "loadbalancer",
                      "used": 0,
                      "quota": 10,
                      "min": 0
                  },
                  {
                      "type": "listener",
                      "used": 0,
                      "quota": 10,
                      "min": 0
                  }
              ]
          }
      }

Status Codes
------------

See :ref:`Status Codes <eip_api05_0001>`.

Error Codes
-----------

See :ref:`Error Codes <eip_api05_0002>`.
