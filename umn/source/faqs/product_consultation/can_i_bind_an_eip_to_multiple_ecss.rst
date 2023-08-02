:original_name: faq_eip_0006.html

.. _faq_eip_0006:

Can I Bind an EIP to Multiple ECSs?
===================================

Each EIP can be bound to only one ECS at a time.

Multiple ECSs cannot share the same EIP. An ECS and its bound EIP must be in the same region. If you want multiple ECSs in the same VPC to share an EIP, you have to use a NAT gateway. For more information, see `NAT Gateway User Guide <https://docs.otc.t-systems.com/nat-gateway/umn/overview/what_is_nat_gateway.html>`__.
