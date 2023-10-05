:original_name: faq_eip_0007.html

.. _faq_eip_0007:

How Do I Access an ECS with an EIP Bound from the Internet?
===========================================================

Each ECS is automatically added to a security group after being created to ensure its security. The security group denies access traffic from the Internet by default. To allow external access to ECSs in the security group, add an inbound rule to the security group.

You can set **Protocol** to **TCP**, **UDP**, **ICMP**, **GRE**, or **All** as required on the page for creating a security group rule.

-  If your ECS needs to be accessible over the Internet and you know the IP address used to access the ECS, set **Source** to the IP address range containing the IP address.

-  If your ECS needs to be accessible over the Internet but you do not know the IP address used to access the ECS, retain the default setting 0.0.0.0/0 for **Source**, and then set allowed ports to improve network security.

   The default source **0.0.0.0/0** indicates that all IP addresses can access ECSs in the security group.

-  Allocate ECSs that have different Internet access requirements to different security groups.
