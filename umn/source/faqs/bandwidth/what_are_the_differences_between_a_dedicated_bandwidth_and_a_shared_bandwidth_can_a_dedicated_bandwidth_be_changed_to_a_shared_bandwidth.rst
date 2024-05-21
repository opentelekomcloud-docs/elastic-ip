:original_name: faq_bandwidth_0006.html

.. _faq_bandwidth_0006:

What Are the Differences Between a Dedicated Bandwidth and a Shared Bandwidth? Can a Dedicated Bandwidth Be Changed to a Shared Bandwidth?
==========================================================================================================================================

A dedicated bandwidth can only be used by one EIP that is bound to one cloud resource, such as an ECS, a NAT gateway, or a load balancer.

A shared bandwidth can be shared by multiple EIPs. Adding an EIP to or removing an EIP from a shared bandwidth does not affect your services.

A dedicated bandwidth cannot be changed to a shared bandwidth or the other way around. You can purchase a shared bandwidth for your EIPs.

-  After you add an EIP to a shared bandwidth, the EIP will use the shared bandwidth.
-  After you remove an EIP from a shared bandwidth, the EIP will use the dedicated bandwidth.
