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

#. On the console homepage, under **Network**, click **Virtual Private Cloud**.

#. Click **Create VPC**.

#. On the **Create VPC** page, set parameters as prompted.

   A default subnet will be created together with a VPC and you can also click **Add Subnet** to create more subnets for the VPC.

   .. table:: **Table 1** VPC parameter descriptions

      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Category                         | Parameter              | Description                                                                                                                                                                                                                                                                                             | Example Value       |
      +==================================+========================+=========================================================================================================================================================================================================================================================================================================+=====================+
      | Basic Information                | Region                 | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For lower network latency and faster access to your resources, select the region nearest you. | eu-de               |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information                | Name                   | The VPC name.                                                                                                                                                                                                                                                                                           | VPC-001             |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | The name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                                                                                   |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Basic Information                | CIDR Block             | The CIDR block of the VPC. The CIDR block of a subnet can be the same as the CIDR block for the VPC (for a single subnet in the VPC) or a subset of the CIDR block for the VPC (for multiple subnets in the VPC).                                                                                       | 192.168.0.0/16      |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | The following CIDR blocks are supported:                                                                                                                                                                                                                                                                |                     |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | 10.0.0.0/8-24                                                                                                                                                                                                                                                                                           |                     |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | 172.16.0.0/12-24                                                                                                                                                                                                                                                                                        |                     |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | 192.168.0.0/16-24                                                                                                                                                                                                                                                                                       |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet                   | Name                   | The subnet name.                                                                                                                                                                                                                                                                                        | Subnet              |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | The name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                                                                                   |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet                   | CIDR Block             | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                                                                                                            | 192.168.0.0/24      |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet                   | Associated Route Table | The default route table to which the subnet will be associated. You can change the route table to a custom route table on the **Subnets** page.                                                                                                                                                         | Default             |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet/Advanced Settings | Gateway                | The gateway address of the subnet.                                                                                                                                                                                                                                                                      | 192.168.0.1         |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet/Advanced Settings | DNS Server Address     | By default, two DNS server addresses are configured. You can change them as required. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                               | 100.125.x.x         |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet/Advanced Settings | NTP Server Address     | The IP address of the NTP server. This parameter is optional.                                                                                                                                                                                                                                           | 192.168.2.1         |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | You can configure the NTP server IP addresses to be added to the subnet as required. The IP addresses are added in addition to the default NTP server addresses. If this parameter is left empty, no IP address of the NTP server is added.                                                             |                     |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                                                                                             |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet/Advanced Settings | Tag                    | The subnet tag, which consists of a key and value pair. You can add a maximum of 20 tags to each subnet.                                                                                                                                                                                                | -  Key: subnet_key1 |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         | -  Value: subnet-01 |
      |                                  |                        | The tag key and value must meet the requirements listed in :ref:`Table 3 <qsg_0003__en-us_topic_0118498853_en-us_topic_0118498861_table6536185812515>`.                                                                                                                                                 |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+
      | Default Subnet/Advanced Settings | Description            | Supplementary information about the subnet. This parameter is optional.                                                                                                                                                                                                                                 | N/A                 |
      |                                  |                        |                                                                                                                                                                                                                                                                                                         |                     |
      |                                  |                        | The subnet description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                                                                              |                     |
      +----------------------------------+------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------+

   .. table:: **Table 2** VPC tag key and value requirements

      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                               | Example Value         |
      +=======================+============================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                                   | vpc_key1              |
      |                       | -  Must be unique for the same VPC and can be the same for different VPCs. |                       |
      |                       | -  Can contain a maximum of 36 characters.                                 |                       |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                                 | vpc-01                |
      |                       | -  Can contain only the following character types:                         |                       |
      |                       |                                                                            |                       |
      |                       |    -  Uppercase letters                                                    |                       |
      |                       |    -  Lowercase letters                                                    |                       |
      |                       |    -  Digits                                                               |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_)        |                       |
      +-----------------------+----------------------------------------------------------------------------+-----------------------+

   .. _qsg_0003__en-us_topic_0118498853_en-us_topic_0118498861_table6536185812515:

   .. table:: **Table 3** Subnet tag key and value requirements

      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirements                                                        | Example Value         |
      +=======================+=====================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                            | subnet_key1           |
      |                       | -  Must be unique for each subnet.                                  |                       |
      |                       | -  Can contain a maximum of 36 characters.                          |                       |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                          | subnet-01             |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
