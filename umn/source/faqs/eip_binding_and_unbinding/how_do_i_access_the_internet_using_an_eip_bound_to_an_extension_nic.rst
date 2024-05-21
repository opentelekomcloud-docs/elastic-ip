:original_name: faq_eip_0009.html

.. _faq_eip_0009:

How Do I Access the Internet Using an EIP Bound to an Extension NIC?
====================================================================

#. After an EIP is bound to an extension NIC, log in to the ECS and use the **route** command to query the routes.

   You can run **route --help** to learn more about the **route** command.


   .. figure:: /_static/images/en-us_image_0000001785700150.png
      :alt: **Figure 1** Viewing route information

      **Figure 1** Viewing route information

#. Run the **ifconfig** command to view NIC information.


   .. figure:: /_static/images/en-us_image_0000001832343237.png
      :alt: **Figure 2** Viewing NIC information

      **Figure 2** Viewing NIC information

#. Enable access to the Internet through the extension NIC by default.

   a. Run the following command to delete the default route of the primary NIC:

      **route del -net 0.0.0.0 gw 192.168.11.1 dev eth0**

      192.168.11.1 is the gateway of the subnet that the NIC works. You can view the gateway on the **Summary** tab page of the subnet on the management console.

      .. note::

         This operation will interrupt ECS communication. It is recommended that you perform the configuration by following step :ref:`4 <faq_eip_0009__en-us_topic_0118498796_li197393270215>`.

   b. Run the following command to configure the default route for the extension NIC:

      **route add default gw 192.168.17.1**

#. .. _faq_eip_0009__en-us_topic_0118498796_li197393270215:

   Configure Internet access from the extension NIC based on your destination address.

   Run the following command to configure access to a specified CIDR block (for example, *xx.xx*.0.0/16) through the extension NIC:

   You can configure the CIDR block as required.

   **route add -net xx.xx.0.0 netmask 255.255.0.0 gw 192.168.17.1**
