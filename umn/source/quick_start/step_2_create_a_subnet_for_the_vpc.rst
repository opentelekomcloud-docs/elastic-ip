:original_name: qsg_0004.html

.. _qsg_0004:

Step 2: Create a Subnet for the VPC
===================================

Scenarios
---------

A VPC comes with a default subnet. If the default subnet cannot meet your requirements, you can create one.

A subnet is configured with DHCP by default. When an ECS in this subnet starts, the ECS automatically obtains an IP address using DHCP.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. Click |image2| in the upper left corner and choose **Network** > **Virtual Private Cloud**.

   The **Virtual Private Cloud** page is displayed.

4. In the navigation pane on the left, choose **Virtual Private Cloud** > **Subnets**.

5. Click **Create Subnet**.

   The **Create Subnet** page is displayed.

6. Set the parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000002029182980.png
      :alt: **Figure 1** Creating a subnet

      **Figure 1** Creating a subnet

   .. table:: **Table 1** Parameter descriptions

      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter                            | Description                                                                                                                                                                                                                                                 | Example Value         |
      +======================================+=============================================================================================================================================================================================================================================================+=======================+
      | Region                               | The region where the VPC is located.                                                                                                                                                                                                                        | ``-``                 |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | VPC                                  | The VPC for which you want to create a subnet.                                                                                                                                                                                                              | ``-``                 |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Subnet Name                          | The subnet name.                                                                                                                                                                                                                                            | Subnet                |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | The name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                                       |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv4 CIDR Block                      | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                                                                | 192.168.0.0/24        |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | If the VPC has a secondary CIDR block, you can select the primary or the secondary CIDR block that the subnet will belong to based on service requirements.                                                                                                 |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | IPv6 CIDR Block                      | Specifies whether to set **IPv6 CIDR Block** to **Enable**.                                                                                                                                                                                                 | ``-``                 |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | If you select this option, the system automatically assigns an IPv6 CIDR block to the created subnet. Currently, the IPv6 CIDR block cannot be customized. IPv6 cannot be disabled after the subnet is created.                                             |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Associated Route Table               | The default route table to which the subnet will be associated. You can change the route table to a custom route table on the **Subnets** page.                                                                                                             | Default               |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings/Gateway            | The gateway address of the subnet.                                                                                                                                                                                                                          | 192.168.0.1           |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings/DNS Server Address | By default, two DNS server addresses are configured. You can change them if necessary. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                  | 100.125.x.x           |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings/NTP Server Address | The IP address of the NTP server. This parameter is optional.                                                                                                                                                                                               | 192.168.2.1           |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | You can configure the NTP server IP addresses to be added to the subnet as required. The IP addresses are added in addition to the default NTP server addresses. If you do not specify this parameter, no additional NTP server IP addresses will be added. |                       |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                                                 |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings/Tag                | The subnet tag, which consists of a key and value pair. You can add a maximum of 20 tags to each subnet.                                                                                                                                                    | -  Key: subnet_key1   |
      |                                      |                                                                                                                                                                                                                                                             | -  Value: subnet-01   |
      |                                      | The tag key and value must meet the requirements listed in :ref:`Table 2 <qsg_0004__en-us_topic_0000001818822770_en-us_topic_0000001818822946_table6536185812515>`.                                                                                         |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings/Description        | Supplementary information about the subnet. This parameter is optional.                                                                                                                                                                                     | ``-``                 |
      |                                      |                                                                                                                                                                                                                                                             |                       |
      |                                      | The subnet description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                  |                       |
      +--------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _qsg_0004__en-us_topic_0000001818822770_en-us_topic_0000001818822946_table6536185812515:

   .. table:: **Table 2** Subnet tag key and value requirements

      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                           | Example Value         |
      +=======================+========================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                               | subnet_key1           |
      |                       | -  Must be unique for each subnet.                                     |                       |
      |                       | -  Can contain a maximum of 36 characters.                             |                       |
      |                       | -  Can contain only the following character types:                     |                       |
      |                       |                                                                        |                       |
      |                       |    -  Uppercase letters                                                |                       |
      |                       |    -  Lowercase letters                                                |                       |
      |                       |    -  Digits                                                           |                       |
      |                       |    -  Only hyphens (-), underscores (_), and at signs (@) are allowed. |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                             | subnet-01             |
      |                       | -  Can contain only the following character types:                     |                       |
      |                       |                                                                        |                       |
      |                       |    -  Uppercase letters                                                |                       |
      |                       |    -  Lowercase letters                                                |                       |
      |                       |    -  Digits                                                           |                       |
      |                       |    -  Only underscores (_), hyphens (-), and at signs (@) are allowed. |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+

7. Click **OK**.

Precautions
-----------

When a subnet is created, there are five reserved IP addresses, which cannot be used. For example, in a subnet with CIDR block 192.168.0.0/24, the following IP addresses are reserved:

-  192.168.0.0: Network ID. This address is the beginning of the private IP address range and will not be assigned to any instance.
-  192.168.0.1: Gateway address.
-  192.168.0.253: Reserved for the system interface. This IP address is used by the VPC for external communication.
-  192.168.0.254: DHCP service address.
-  192.168.0.255: Network broadcast address.

If you configured the default settings under **Advanced Settings** during subnet creation, the reserved IP addresses may be different from the default ones, but there will still be five of them. The specific addresses depend on your subnet settings.

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001818983298.png
