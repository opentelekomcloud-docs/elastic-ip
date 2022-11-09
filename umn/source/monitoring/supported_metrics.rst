:original_name: monitor_0002.html

.. _monitor_0002:

Supported Metrics
=================

Description
-----------

This section describes the namespace, list, and measurement dimensions of EIP and bandwidth metrics that you can check on Cloud Eye. You can use APIs or the Cloud Eye console to query the metrics of the monitored metrics and alarms generated for EIPs and bandwidths.

Namespace
---------

SYS.VPC

Monitoring Metrics
------------------

.. table:: **Table 1** EIP and bandwidth metrics

   +----------------------+--------------------+-------------------------------------------------+-------------+------------------+--------------------------------+
   | ID                   | Name               | Description                                     | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +======================+====================+=================================================+=============+==================+================================+
   | upstream_bandwidth   | Outbound Bandwidth | Network rate of outbound traffic                | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                 |             |                  |                                |
   |                      |                    | Unit: bit/s                                     |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth | Inbound Bandwidth  | Network rate of inbound traffic                 | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                 |             |                  |                                |
   |                      |                    | Unit: bit/s                                     |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------+-------------+------------------+--------------------------------+
   | up_stream            | Outbound Traffic   | Network traffic going out of the cloud platform | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                 |             |                  |                                |
   |                      |                    | Unit: byte                                      |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------+-------------+------------------+--------------------------------+
   | down_stream          | Inbound Traffic    | Network traffic going into the cloud platform   | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                      |                    |                                                 |             |                  |                                |
   |                      |                    | Unit: byte                                      |             |                  |                                |
   +----------------------+--------------------+-------------------------------------------------+-------------+------------------+--------------------------------+

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
