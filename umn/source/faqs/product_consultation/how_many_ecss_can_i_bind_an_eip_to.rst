:original_name: faq_eip_0006.html

.. _faq_eip_0006:

How Many ECSs Can I Bind an EIP To?
===================================

An EIP can be bound to only one ECS.

An EIP cannot be shared by multiple ECSs, and the EIP and ECS must be in the same region. You can use public NAT gateways to enable the ECSs in the VPC to share an EIP to access or be accessed by the Internet.

For more information, see the `NAT Gateway User Guide <https://docs.otc.t-systems.com/nat-gateway/umn/overview/what_is_nat_gateway.html>`__.
