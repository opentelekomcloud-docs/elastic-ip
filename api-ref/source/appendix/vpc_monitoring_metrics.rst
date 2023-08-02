:original_name: eip_api06_0003.html

.. _eip_api06_0003:

VPC Monitoring Metrics
======================

Description
-----------

This section describes monitoring metrics reported by VPC to Cloud Eye as well as their namespaces and dimensions. You can use APIs provided by Cloud Eye to query the monitoring metrics of the monitored object and alarms generated for VPC.

Namespace
---------

SYS.VPC

Metrics
-------

.. table:: **Table 1** EIP and bandwidth metrics

   +----------------------+--------------------+-------------------------------------------------------------+-------------+------------------+--------------------------------+
   | ID                   | Name               | Description                                                 | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +======================+====================+=============================================================+=============+==================+================================+
   | upstream_bandwidth   | Outbound Bandwidth | Network rate of outbound traffic                            | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                             |             |                  |                                |
   |                      |                    | Unit: bit/s                                                 |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth | Inbound Bandwidth  | Network rate of inbound traffic                             | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                             |             |                  |                                |
   |                      |                    | Unit: bit/s                                                 |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------------------+-------------+------------------+--------------------------------+
   | up_stream            | Outbound Traffic   | Network traffic going out of the cloud platform in a minute | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                             |             |                  |                                |
   |                      |                    | Unit: byte                                                  |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------------------+-------------+------------------+--------------------------------+
   | down_stream          | Inbound Traffic    | Network traffic going into the cloud platform in a minute   | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                             |             |                  |                                |
   |                      |                    | Unit: byte                                                  |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------------------+-------------+------------------+--------------------------------+

Dimension
---------

============ ============
Key          Value
============ ============
publicip_id  EIP ID
bandwidth_id Bandwidth ID
============ ============
