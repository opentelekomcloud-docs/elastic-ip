:original_name: qsg_0004.html

.. _qsg_0004:

Step 2: Create a Subnet for the VPC
===================================

Scenarios
---------

A VPC comes with a default subnet. If the default subnet cannot meet your requirements, you can create one.

The subnet is configured with DHCP by default. When an ECS in this subnet starts, the ECS automatically obtains an IP address using DHCP.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. On the console homepage, under **Network**, click **Virtual Private Cloud**.

4. In the navigation pane on the left, click **Subnets**.

5. Click **Create Subnet**.

   The **Create Subnet** page is displayed.

6. Set the parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000001197228903.png
      :alt: **Figure 1** Create Subnet

      **Figure 1** Create Subnet

   .. table:: **Table 1** Parameter descriptions

      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter              | Description                                                                                                                                                                                                                                 | Example Value         |
      +========================+=============================================================================================================================================================================================================================================+=======================+
      | VPC                    | The VPC for which you want to create a subnet.                                                                                                                                                                                              | -                     |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Name                   | The subnet name.                                                                                                                                                                                                                            | Subnet                |
      |                        |                                                                                                                                                                                                                                             |                       |
      |                        | The name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                       |                       |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | CIDR Block             | The CIDR block for the subnet. This value must be within the VPC CIDR block.                                                                                                                                                                | 192.168.0.0/24        |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Associated Route Table | The default route table to which the subnet will be associated. You can change the route table to a custom route table on the **Subnets** page.                                                                                             | Default               |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Advanced Settings      | Two options are available, **Default** and **Custom**. You can set **Advanced Settings** to **Custom** to configure advanced subnet parameters.                                                                                             | -                     |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Gateway                | The gateway address of the subnet.                                                                                                                                                                                                          | 192.168.0.1           |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | DNS Server Address     | By default, two DNS server addresses are configured. You can change them if necessary. A maximum of five DNS server addresses can be configured. Multiple IP addresses must be separated using commas (,).                                  | 100.125.x.x           |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | NTP Server Address     | The IP address of the NTP server. This parameter is optional.                                                                                                                                                                               | 192.168.2.1           |
      |                        |                                                                                                                                                                                                                                             |                       |
      |                        | You can configure the NTP server IP addresses to be added to the subnet as required. The IP addresses are added in addition to the default NTP server addresses. If this parameter is left empty, no IP address of the NTP server is added. |                       |
      |                        |                                                                                                                                                                                                                                             |                       |
      |                        | A maximum of four IP addresses can be configured. Multiple IP addresses must be separated using commas (,).                                                                                                                                 |                       |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                    | The subnet tag, which consists of a key and value pair. You can add a maximum of 20 tags to each subnet.                                                                                                                                    | -  Key: subnet_key1   |
      |                        |                                                                                                                                                                                                                                             | -  Value: subnet-01   |
      |                        | The tag key and value must meet the requirements listed in :ref:`Table 2 <qsg_0004__en-us_topic_0118498982_en-us_topic_0118498823_table42131827173915>`.                                                                                    |                       |
      +------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _qsg_0004__en-us_topic_0118498982_en-us_topic_0118498823_table42131827173915:

   .. table:: **Table 2** Subnet tag key and value requirements

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

.. |image1| image:: /_static/images/en-us_image_0141273034.png
