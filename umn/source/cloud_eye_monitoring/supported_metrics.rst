:original_name: monitor_0002.html

.. _monitor_0002:

Supported Metrics
=================

Description
-----------

This section describes the namespace, list, and measurement dimensions of metrics of EIPs and bandwidths that you can check on Cloud Eye. You can use APIs or the Cloud Eye console to query the metrics of the monitored metrics and generated alarms.

Namespace
---------

Namespace of EIPs and bandwidths: SYS.VPC

Monitoring Metrics
------------------

.. table:: **Table 1** Metrics of EIPs and bandwidths

   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | ID                         | Name                     | Description                                                       | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +============================+==========================+===================================================================+=============+==================+================================+
   | upstream_bandwidth         | Outbound Bandwidth       | Network rate of outbound traffic                                  | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Unit: bit/s                                                       |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth       | Inbound Bandwidth        | Network rate of inbound traffic                                   | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Unit: bit/s                                                       |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | upstream_bandwidth_usage   | Outbound Bandwidth Usage | Usage of outbound bandwidth in the unit of percent.               | 0% to 100%  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Outbound bandwidth usage = Outbound bandwidth/Purchased bandwidth |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth_usage | Inbound Bandwidth Usage  | Usage of inbound bandwidth in the unit of percent.                | 0-100%      | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Inbound bandwidth usage = Inbound bandwidth/Purchased bandwidth   |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | up_stream                  | Outbound Traffic         | Network traffic going out of the cloud platform                   | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Unit: byte                                                        |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | down_stream                | Inbound Traffic          | Network traffic going into the cloud platform                     | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                   |             |                  |                                |
   |                            |                          | Unit: byte                                                        |             |                  |                                |
   +----------------------------+--------------------------+-------------------------------------------------------------------+-------------+------------------+--------------------------------+

.. note::

   If a bandwidth is increased or decreased, there is a delay of 5 to 10 minutes for the monitoring metrics to update for the new bandwidth.

Dimensions
----------

============ ============
Key          Value
============ ============
publicip_id  EIP ID
bandwidth_id Bandwidth ID
============ ============

If a monitored object has multiple dimensions, all dimensions are mandatory when you use APIs to query the metrics.

-  Query a monitoring metric:

   dim.0=bandwidth_id,530cd6b0-86d7-4818-837f-935f6a27414d&dim.1=publicip_id,3773b058-5b4f-4366-9035-9bbd9964714a

-  Query monitoring metrics in batches:

   "dimensions": [

   {

   "name": "bandwidth_id",

   "value": "530cd6b0-86d7-4818-837f-935f6a27414d"

   }

   {

   "name": "publicip_id",

   "value": "3773b058-5b4f-4366-9035-9bbd9964714a"

   }

   ],
