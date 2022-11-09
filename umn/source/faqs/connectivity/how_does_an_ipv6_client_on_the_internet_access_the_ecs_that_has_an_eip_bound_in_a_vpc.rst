:original_name: faq_connect_0002.html

.. _faq_connect_0002:

How Does an IPv6 Client on the Internet Access the ECS That Has an EIP Bound in a VPC?
======================================================================================

Users with IPv6 clients can call APIs to assign IPv6 EIPs and bind the EIPs to ECSs. Then, the users can use the EIP to access the ECSs in the VPC over the Internet.

For details, see **Floating IP Address (IPv6)** > **Creating a Floating IP Address** in the `Virtual Private Cloud API Reference <https://docs.otc.t-systems.com/en-us/api/vpc/en-us_topic_0050065465.html>`__. The NAT64 gateway in the data center will convert the IPv6 EIP to the IPv4 address. (The last 32 bits of the obtained IPv6 EIP is the IPv4 EIP.)

After users who use IPv6 clients bind an IPv6 EIP to an ECS, the data flow is shown in :ref:`Figure 1 <faq_connect_0002__en-us_topic_0118499049_fig1038524023539>`.

.. _faq_connect_0002__en-us_topic_0118499049_fig1038524023539:

.. figure:: /_static/images/en-us_image_0118499144.png
   :alt: **Figure 1** IPv6 data flow

   **Figure 1** IPv6 data flow

The IPv6 service has the following restrictions:

-  ECSs use IPv4 addresses and cannot directly access public IPv6 addresses. Therefore, only public IPv6 addresses can access ECSs. That means ECSs cannot use IPv4 EIPs that are converted from IPv6 address to access the Internet. To enable the ECSs to access the Internet, you must bind IPv4 EIPs to them.
-  Data packets from an IPv6 network on the Internet are converted to IPv4 packets on the NAT64 gateway. Both the source IP address and port number will be converted. (The source IP address is invisible.)
-  The IPv6 client can access only the EIP and the ELB service.
-  Only one EIP (IPv6 or IPv4) can be bound to each NIC.
-  You can only make API calls to use an EIP to obtain the IPv6 address. The management console displays only IPv4 addresses.
-  The security group function does not apply to IPv6 clients.
-  Resources in internal networks on the cloud can access IPv4 addresses converted by NAT64 gateway.
-  The public cloud does not provide IP spoofing protection for IPv6 traffic from the Internet.
-  Currently, the Anti-DDoS service does not protect IPv6 addresses.
