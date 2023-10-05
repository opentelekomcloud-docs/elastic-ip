:original_name: qsg_0006.html

.. _qsg_0006:

Step 4: Create a Security Group
===============================

Scenarios
---------

A security group is a collection of access control rules to control the traffic that is allowed to reach and leave the cloud resources that it is associated with. The cloud resources can be cloud servers, containers, databases, and more. A security group consists of inbound and outbound rules.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner and choose **Network** > **Virtual Private Cloud**.

#. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

   The security group list is displayed.

#. In the upper right corner, click **Create Security Group**.

   The **Create Security Group** page is displayed.

#. Configure the parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000001197426329.png
      :alt: **Figure 1** Create Security Group

      **Figure 1** Create Security Group

   .. table:: **Table 1** Parameter description

      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                           | Example Value              |
      +=======================+=======================================================================================================================================================================================================================================================+============================+
      | Name                  | Mandatory                                                                                                                                                                                                                                             | sg-AB                      |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | Enter the security group name.                                                                                                                                                                                                                        |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | The security group name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces.                                                                  |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | .. note::                                                                                                                                                                                                                                             |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       |    You can change the security group name after a security group is created. It is recommended that you give each security group a different name.                                                                                                    |                            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Enterprise Project    | Mandatory                                                                                                                                                                                                                                             | default                    |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | When creating a security group, you can add the security group to an enabled enterprise project.                                                                                                                                                      |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | An enterprise project facilitates project-level management and grouping of cloud resources and users. The name of the default project is **default**.                                                                                                 |                            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Template              | Mandatory                                                                                                                                                                                                                                             | General-purpose web server |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | A template comes with default security group rules, helping you quickly create security groups. The following templates are provided:                                                                                                                 |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | -  **Custom**: This template allows you to create security groups with custom security group rules.                                                                                                                                                   |                            |
      |                       | -  **General-purpose web server**: The security group that you create using this template is for general-purpose web servers and includes default rules that allow all inbound ICMP traffic and allow inbound traffic on ports 22, 80, 443, and 3389. |                            |
      |                       | -  **All ports open**: The security group that you create using this template includes default rules that allow inbound traffic on any port. Note that allowing inbound traffic on any port poses security risks.                                     |                            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
      | Description           | Optional                                                                                                                                                                                                                                              | N/A                        |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | Supplementary information about the security group. This parameter is optional.                                                                                                                                                                       |                            |
      |                       |                                                                                                                                                                                                                                                       |                            |
      |                       | The security group description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                                                                                    |                            |
      +-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+

#. Confirm the inbound and outbound rules of the template and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000001500905066.png
