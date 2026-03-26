:original_name: qsg_0003.html

.. _qsg_0003:

Step 1: Create a VPC
====================

Scenarios
---------

A VPC provides an isolated virtual network for ECSs. You can configure and manage the network as required.

You can create a VPC by following the procedure provided in this section. Then, create subnets, security groups, and assign EIPs by following the procedure provided in subsequent sections based on your actual network requirements.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner and choose **Network** > **Virtual Private Cloud**.

   The **Virtual Private Cloud** page is displayed.

#. Click **Create VPC**.

#. On the **Create VPC** page, set parameters as prompted.

   A default subnet will be created together with a VPC and you can also click **Add Subnet** to create more subnets for the VPC.


   .. figure:: /_static/images/en-us_image_0000002555360481.png
      :alt: **Figure 1** Creating a VPC with a subnet (VPC information)

      **Figure 1** Creating a VPC with a subnet (VPC information)


   .. figure:: /_static/images/en-us_image_0000002555242197.png
      :alt: **Figure 2** Creating a VPC with a subnet (subnet information)

      **Figure 2** Creating a VPC with a subnet (subnet information)

   .. table:: **Table 1** VPC parameter descriptions

      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Category                     | Parameter                  | Description                                                                                                                                                                                                                                                 | Example Value       |
      +==============================+============================+=============================================================================================================================================================================================================================================================+=====================+
      | Basic Configuration          | Region                     | Select the region nearest to you to ensure the lowest latency possible.                                                                                                                                                                                     | eu-de               |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Virtual Private Cloud        | Name                       | The VPC name.                                                                                                                                                                                                                                               | VPC-001             |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The name can contain a maximum of 64 characters, which can consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                                       |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Virtual Private Cloud        | IPv4 CIDR Block            | The CIDR block of the VPC. The CIDR block of a subnet can be the same as the CIDR block for the VPC (for a single subnet in the VPC) or a subset of the CIDR block for the VPC (for multiple subnets in the VPC).                                           | 192.168.0.0/16      |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The following CIDR blocks are supported:                                                                                                                                                                                                                    |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | 10.0.0.0/8-24                                                                                                                                                                                                                                               |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | 172.16.0.0/12-24                                                                                                                                                                                                                                            |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | 192.168.0.0/16-24                                                                                                                                                                                                                                           |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Virtual Private Cloud        | Enterprise Project         | The enterprise project to which the VPC belongs.                                                                                                                                                                                                            | default             |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | An enterprise project facilitates project-level management and grouping of cloud resources and users. The name of the default project is **default**.                                                                                                       |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | More (Optional)              | Tag                        | Click |image3| to expand the configuration area and configure this parameter.                                                                                                                                                                               | -  Key: vpc_key1    |
      |                              |                            |                                                                                                                                                                                                                                                             | -  Value: vpc-01    |
      |                              |                            | The VPC tag, which consists of a key and value pair. You can add a maximum of 20 tags to each VPC.                                                                                                                                                          |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The tag key and value must meet the requirements listed in :ref:`Table 2 <qsg_0003__en-us_topic_0000001818982662_en-us_topic_0000001865662501_table248245914136>`.                                                                                          |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | More (Optional)              | Description                | Click |image4| to expand the configuration area and configure this parameter.                                                                                                                                                                               | N/A                 |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | Supplementary information about the VPC. This parameter is optional.                                                                                                                                                                                        |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                         |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet 1                     | Subnet Name                | The subnet name.                                                                                                                                                                                                                                            | Subnet              |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The name can contain a maximum of 64 characters, which can consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                                       |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet 1                     | IPv4 CIDR Block            | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                                                                | 192.168.0.0/24      |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet 1                     | IPv6 CIDR Block (Optional) | Specifies whether to set **IPv6 CIDR Block** to **Enable**.                                                                                                                                                                                                 | ``-``               |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | After the IPv6 function is enabled, the system automatically assigns an IPv6 CIDR block to the created subnet. Currently, the IPv6 CIDR block cannot be customized. IPv6 cannot be disabled after the subnet is created.                                    |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Subnet 1                     | Associated Route Table     | The default route table to which the subnet will be associated. You can change the route table to a custom route table on the **Subnets** page.                                                                                                             | Default             |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Advanced Settings (Optional) | Gateway                    | The gateway address of the subnet.                                                                                                                                                                                                                          | 192.168.0.1         |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Advanced Settings (Optional) | DNS Server Address         | By default, two DNS server addresses are configured. You can change them as required. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                   | 100.125.x.x         |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Advanced Settings (Optional) | NTP Server Address         | The IP address of the NTP server. This parameter is optional.                                                                                                                                                                                               | 192.168.2.1         |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | You can configure the NTP server IP addresses to be added to the subnet as required. The IP addresses are added in addition to the default NTP server addresses. If you do not specify this parameter, no additional NTP server IP addresses will be added. |                     |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                                                 |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Advanced Settings (Optional) | Tag                        | The subnet tag, which consists of a key and value pair. You can add a maximum of 20 tags to each subnet.                                                                                                                                                    | -  Key: subnet_key1 |
      |                              |                            |                                                                                                                                                                                                                                                             | -  Value: subnet-01 |
      |                              |                            | The tag key and value must meet the requirements listed in :ref:`Table 3 <qsg_0003__en-us_topic_0000001818982662_en-us_topic_0000001865662501_table6536185812515>`.                                                                                         |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Advanced Settings (Optional) | Description                | Supplementary information about the subnet. This parameter is optional.                                                                                                                                                                                     | N/A                 |
      |                              |                            |                                                                                                                                                                                                                                                             |                     |
      |                              |                            | The description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                         |                     |
      +------------------------------+----------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+

   .. _qsg_0003__en-us_topic_0000001818982662_en-us_topic_0000001865662501_table248245914136:

   .. table:: **Table 2** VPC tag key and value requirements

      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                                                     | Example Value         |
      +=======================+==================================================================================================+=======================+
      | Key                   | -  For each resource, each tag key must be unique, and each tag key can only have one tag value. | vpc_key1              |
      |                       | -  Cannot be left blank.                                                                         |                       |
      |                       | -  Can contain a maximum of 128 characters.                                                      |                       |
      |                       | -  Cannot start or end with a space.                                                             |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can be left blank.                                                                            | vpc-01                |
      |                       | -  Can contain a maximum of 255 characters.                                                      |                       |
      |                       | -  Cannot start or end with a space.                                                             |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+

   .. _qsg_0003__en-us_topic_0000001818982662_en-us_topic_0000001865662501_table6536185812515:

   .. table:: **Table 3** Subnet tag key and value requirements

      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                                                     | Example Value         |
      +=======================+==================================================================================================+=======================+
      | Key                   | -  For each resource, each tag key must be unique, and each tag key can only have one tag value. | subnet_key1           |
      |                       | -  Cannot be left blank.                                                                         |                       |
      |                       | -  Can contain a maximum of 128 characters.                                                      |                       |
      |                       | -  Cannot start or end with a space.                                                             |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can be left blank.                                                                            | subnet-01             |
      |                       | -  Can contain a maximum of 255 characters.                                                      |                       |
      |                       | -  Cannot start or end with a space.                                                             |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001865663089.png
.. |image3| image:: /_static/images/en-us_image_0000002524247358.png
.. |image4| image:: /_static/images/en-us_image_0000002555247269.png
