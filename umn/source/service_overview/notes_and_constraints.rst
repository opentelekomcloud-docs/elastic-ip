:original_name: overview_0003.html

.. _overview_0003:

Notes and Constraints
=====================

EIP
---

Note the following when using EIPs:

-  Each EIP can only be bound to one cloud resource.
-  An EIP that has already been bound to a cloud resource cannot be bound to another resource without first being unbound from the current resource.
-  EIPs cannot be transferred across accounts.
-  You can only release unbound EIPs.
-  The system preferentially assigns EIPs to you from the ones you released, if any. However, if any of these EIPs is already assigned to another user, it cannot be re-assigned to you.

Bandwidth
---------

-  A dedicated bandwidth can control how much data can be transferred using a single EIP.
-  A shared bandwidth cannot control how much data can be transferred using a single EIP. Data transfer rate on EIPs cannot be customized.

-  A shared bandwidth or dedicated bandwidth can only be used by resources owned by the same account.

.. note::

   -  Inbound bandwidth is the bandwidth consumed when data is transferred from the Internet to the cloud. Outbound bandwidth is the bandwidth consumed when data is transferred from the cloud to the Internet.
