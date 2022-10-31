:original_name: qsg_0005.html

.. _qsg_0005:

Step 3: Assign an EIP and Bind It to an ECS
===========================================

Scenarios
---------

You can assign an EIP and bind it to an ECS so that the ECS can access the Internet.

.. note::

   EIPs for dedicated load balancers:

   -  In the **eu-de** region, if you choose to assign an EIP when you create a dedicated load balancer on the management console or using APIs, EIPs for dedicated load balancers (**5_gray**) will be assigned.
   -  Do not bind EIPs of this type to non-dedicated load balancers.
   -  Do not add EIPs of the dedicated load balancer type and other types to the same shared bandwidth. Otherwise, the bandwidth limit policy will not take effect.

Assigning an EIP
----------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Elastic IP**.

#. On the displayed page, click **Assign EIP**.

#. Set the parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000001117669274.png
      :alt: **Figure 1** Assign EIP

      **Figure 1** Assign EIP

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                             | Example Value           |
      +=======================+=========================================================================================================================================================================================================================================================================================================+=========================+
      | Region                | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For lower network latency and faster access to your resources, select the region nearest you. | eu-de                   |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | EIP Type              | -  **Dynamic BGP**: Dynamic BGP provides automatic failover and chooses the optimal path when a network connection fails.                                                                                                                                                                               | Dynamic BGP             |
      |                       | -  **Mail BGP**: EIPs with port 25, 465, or 587 enabled are used.                                                                                                                                                                                                                                       |                         |
      |                       |                                                                                                                                                                                                                                                                                                         |                         |
      |                       | The selected EIP type cannot be changed after the EIP is assigned.                                                                                                                                                                                                                                      |                         |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | Bandwidth             | The bandwidth size in Mbit/s.                                                                                                                                                                                                                                                                           | 100                     |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | Bandwidth Name        | The name of the bandwidth.                                                                                                                                                                                                                                                                              | bandwidth               |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | Tag                   | The EIP tags. Each tag contains a key and value pair.                                                                                                                                                                                                                                                   | -  Key: Ipv4_key1       |
      |                       |                                                                                                                                                                                                                                                                                                         | -  Value: 192.168.12.10 |
      |                       | The tag key and value must meet the requirements listed in :ref:`Table 2 <qsg_0005__en-us_topic_0118499041_en-us_topic_0118498850_table36606052153313>`.                                                                                                                                                |                         |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+
      | Quantity              | The number of EIPs you want to purchase.                                                                                                                                                                                                                                                                | 1                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------+

   .. _qsg_0005__en-us_topic_0118499041_en-us_topic_0118498850_table36606052153313:

   .. table:: **Table 2** EIP tag requirements

      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirement                                                         | Example Value         |
      +=======================+=====================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                            | Ipv4_key1             |
      |                       | -  Must be unique for each EIP.                                     |                       |
      |                       | -  Can contain a maximum of 36 characters.                          |                       |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain a maximum of 43 characters.                          | 192.168.12.10         |
      |                       | -  Can contain only the following character types:                  |                       |
      |                       |                                                                     |                       |
      |                       |    -  Uppercase letters                                             |                       |
      |                       |    -  Lowercase letters                                             |                       |
      |                       |    -  Digits                                                        |                       |
      |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
      +-----------------------+---------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

#. Click **Submit**.

Binding an EIP
--------------

#. On the **EIPs** page, locate the row that contains the target EIP, and click **Bind**.

#. Select the instance to which you want to bind the EIP.


   .. figure:: /_static/images/en-us_image_0000001166028070.png
      :alt: **Figure 2** Bind EIP

      **Figure 2** Bind EIP

#. Click **OK**.

An IPv6 client on the Internet can access the ECS that has an EIP bound in a VPC. For details about the implementation and constraints, see :ref:`How Does an IPv6 Client on the Internet Access the ECS That Has an EIP Bound in a VPC? <faq_connect_0002>`

Follow-Up Procedure
-------------------

After an ECS with an EIP bound is created, the system generates a domain name in the format of **ecs-**\ *xx-xx-xx-xx*\ **.compute.**\ *xxx*\ **.com** for the EIP by default. *xx-xx-xx-xx* indicates the EIP, and xxx indicates the domain name of the cloud service provider. You can use the domain name to access the ECS.

You can use any of the following commands to obtain the domain name of an EIP:

-  ping -a *EIP*
-  nslookup [-qt=ptr] *EIP*
-  dig -x *EIP*

.. |image1| image:: /_static/images/en-us_image_0141273034.png
