:original_name: qsg_0006.html

.. _qsg_0006:

Step 4: Create a Security Group
===============================

Scenarios
---------

To improve ECS access security, you can create security groups, define security group rules, and add ECSs in a VPC to different security groups. We recommend that you allocate ECSs that have different Internet access policies to different security groups.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. On the console homepage, under **Network**, click **Virtual Private Cloud**.

4. In the navigation pane on the left, choose **Access Control** > **Security Groups**.

5. On the **Security Groups** page, click **Create Security Group**.

6. In the **Create Security Group** area, set the parameters as prompted. :ref:`Table 1 <qsg_0006__en-us_topic_0118646265_en-us_topic_0118534004_table65377617111335>` lists the parameters to be configured.


   .. figure:: /_static/images/en-us_image_0000001197426329.png
      :alt: **Figure 1** Create Security Group

      **Figure 1** Create Security Group

   .. _qsg_0006__en-us_topic_0118646265_en-us_topic_0118534004_table65377617111335:

   .. table:: **Table 1** Parameter description

      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                          | Example Value         |
      +=======================+======================================================================================================================================================================================+=======================+
      | Name                  | The security group name. This parameter is mandatory.                                                                                                                                | sg-318b               |
      |                       |                                                                                                                                                                                      |                       |
      |                       | The security group name can contain a maximum of 64 characters, which may consist of letters, digits, underscores (_), hyphens (-), and periods (.). The name cannot contain spaces. |                       |
      |                       |                                                                                                                                                                                      |                       |
      |                       | .. note::                                                                                                                                                                            |                       |
      |                       |                                                                                                                                                                                      |                       |
      |                       |    You can change the security group name after a security group is created. It is recommended that you give each security group a different name.                                   |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Supplementary information about the security group. This parameter is optional.                                                                                                      | N/A                   |
      |                       |                                                                                                                                                                                      |                       |
      |                       | The security group description can contain a maximum of 255 characters and cannot contain angle brackets (< or >).                                                                   |                       |
      +-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

7. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
