:original_name: overview_0006.html

.. _overview_0006:

Application Scenarios
=====================

Binding an EIP to an ECS
------------------------

**Scenario**

You can bind an EIP to an ECS to enable the ECS to access the Internet.

**Related Services**

ECS, BMS, or VPC


.. figure:: /_static/images/en-us_image_0204809678.png
   :alt: **Figure 1** Binding an EIP to a server

   **Figure 1** Binding an EIP to a server

**Binding an EIP to a NAT Gateway**
-----------------------------------

**Scenario**

After an EIP is bound to a NAT gateway and SNAT and DNAT rules are added, multiple servers (such as ECSs and BMSs) can use the same EIP to access the Internet and provide services accessible from the Internet.

An SNAT rule allows servers in a specific VPC subnet to use the same EIP to access the Internet.

A DNAT rule enables servers in a VPC to provide services accessible from the Internet.

**Related Services**

NAT Gateway, Cloud server (ECS and BMS), and VPC


.. figure:: /_static/images/en-us_image_0204809728.png
   :alt: **Figure 2** EIP used by a NAT gateway

   **Figure 2** EIP used by a NAT gateway

Binding an EIP to a Load Balancer
---------------------------------

**Scenario**

After you attach an EIP to a load balancer, the load balancer can distribute requests from the Internet to backend servers.

**Related Services**

ELB, ECS, and VPC


.. figure:: /_static/images/en-us_image_0204809524.png
   :alt: **Figure 3** EIP used by a load balancer

   **Figure 3** EIP used by a load balancer
