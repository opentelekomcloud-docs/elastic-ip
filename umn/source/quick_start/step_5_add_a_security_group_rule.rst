:original_name: qsg_0007.html

.. _qsg_0007:

Step 5: Add a Security Group Rule
=================================

Scenarios
---------

After you create a security group, you can add rules to the security group. A rule applies either to inbound traffic or outbound traffic. After you add cloud resources to the security group, they are protected by the rules of the group.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner and choose **Network** > **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

   The security group list is displayed.

#. Locate the row that contains the target security group, click **Manage Rule** in the **Operation** column.

   The page for configuring security group rules is displayed.

#. On the **Inbound Rules** tab, click **Add Rule**. In the displayed dialog box, set required parameters.

   You can click **+** to add more inbound rules.

   .. table:: **Table 1** Inbound rule parameter description

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Parameter             | Description                                                                                                                                                              | Example Value                |
      +=======================+==========================================================================================================================================================================+==============================+
      | Protocol & Port       | **Protocol**: The network protocol. Currently, the value can be **All**, **TCP**, **UDP**, **ICMP**, **GRE**, or others.                                                 | Protocols/TCP (Custom ports) |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      |                       | **Port**: The port or port range over which the traffic can reach your ECS. The value ranges from 1 to 65535.                                                            | 22, or 22-30                 |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Type                  | The IP address type can be IPv4.                                                                                                                                         | IPv4                         |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Source                | Source of the security group rule. The value can be an IP address or a security group to allow access from IP addresses or instances in the security group. For example: | 0.0.0.0/0                    |
      |                       |                                                                                                                                                                          |                              |
      |                       | -  IP address:                                                                                                                                                           |                              |
      |                       |                                                                                                                                                                          |                              |
      |                       |    -  Single IP address: 192.168.10.10/32                                                                                                                                |                              |
      |                       |    -  All IP addresses: 0.0.0.0/0                                                                                                                                        |                              |
      |                       |    -  IP address range: 192.168.1.0/24                                                                                                                                   |                              |
      |                       |                                                                                                                                                                          |                              |
      |                       | -  Security group: sg-A                                                                                                                                                  |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+
      | Description           | Supplementary information about the security group rule. This parameter is optional.                                                                                     | ``-``                        |
      |                       |                                                                                                                                                                          |                              |
      |                       | The security group rule description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                  |                              |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------+

#. On the **Outbound Rules** tab, click **Add Rule**. In the displayed dialog box, set required parameters.

   You can click **+** to add more outbound rules.

   .. table:: **Table 2** Outbound rule parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                 | Example Value         |
      +=======================+=============================================================================================================================================================================+=======================+
      | Protocol & Port       | **Protocol**: The network protocol. Currently, the value can be **All**, **TCP**, **UDP**, **ICMP**, **GRE**, or others.                                                    | Custom TCP            |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      |                       | **Port**: The port or port range over which the traffic can leave your ECS. The value ranges from 1 to 65535.                                                               | 22, or 22-30          |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Type                  | The IP address type can be IPv4.                                                                                                                                            | IPv4                  |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Destination           | Destination of the security group rule. The value can be an IP address or a security group to allow access to IP addresses or instances in the security group. For example: | 0.0.0.0/0             |
      |                       |                                                                                                                                                                             |                       |
      |                       | For more information, see *Virtual Private Cloud User Guide*.                                                                                                               |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Supplementary information about the security group rule. This parameter is optional.                                                                                        | ``-``                 |
      |                       |                                                                                                                                                                             |                       |
      |                       | The security group rule description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                     |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000001520959725.png
