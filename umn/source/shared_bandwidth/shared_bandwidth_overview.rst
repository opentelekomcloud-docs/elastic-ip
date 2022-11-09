:original_name: bandwidth_0002.html

.. _bandwidth_0002:

Shared Bandwidth Overview
=========================

Shared bandwidth allows multiple EIPs to share the same bandwidth. All ECSs, BMSs, and load balancers that have EIPs bound in the same region can share a bandwidth.

When you host a large number of applications on the cloud, if each EIP uses an independent bandwidth, a lot of bandwidths are required, increasing O&M workload. If all EIPs share the same bandwidth, VPCs and the region-level bandwidth can be managed in a unified manner, simplifying O&M statistics and network operations cost settlement.

-  Easy to Manage

   Region-level bandwidth sharing and multiplexing simplify O&M statistics, management, and operations cost settlement.

-  Flexible Operations

   You can add EIPs to a shared bandwidth or remove them from a shared bandwidth regardless of the instances to which they are bound.
