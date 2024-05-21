:original_name: eip_0002.html

.. _eip_0002:

Assigning an EIP and Binding It to an ECS
=========================================

Scenarios
---------

You can assign an EIP and bind it to an ECS so that the ECS can access the Internet.

.. note::

   Note the following when you use EIPs of the Dedicated Load Balancer (**5_gray**) type:

   -  In **eu-de**, EIPs of the Dedicated Load Balancer (**5_gray**) type cannot be assigned anymore. You can assign EIPs of the BGP (**5_bgp**) type.
   -  Existing EIPs of the Dedicated Load Balancer (**5_gray**) type can be bound to dedicated or shared load balancers.

      -  The EIP console cannot be used to bind EIPs to or unbind them from dedicated load balancers.
      -  You can use APIs to bind EIPs to or unbind them from dedicated load balancers. For details, see `Binding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/binding_an_eip.html>`__ and `Unbinding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/unbinding_an_eip.html>`__.
      -  EIPs of this type can be bound to or unbound from shared load balancers using the EIP console or APIs.
      -  You are advised to bind BGP EIPs to or unbind them from dedicated load balancers.

   -  Do not add EIPs of the dedicated load balancer type (**5_gray**) and other types to the same shared bandwidth. Otherwise, the bandwidth limit policy will not take effect.

Assigning an EIP
----------------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner and choose **Network** > **Elastic IP**.

#. On the displayed page, click **Assign EIP**.

#. Set the parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000001818823034.png
      :alt: **Figure 1** Assign EIP

      **Figure 1** Assign EIP

   .. table:: **Table 1** Parameter descriptions

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                                                                                                                                                                                                                                           | Example Value         |
      +=======================+=======================================================================================================================================================================================================================================================================================================================================================================+=======================+
      | Region                | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For lower network latency and faster access to your resources, select the region nearest you. The region selected for the EIP is its geographical location. | eu-de                 |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | EIP Type              | -  **Dynamic BGP**: Dynamic BGP provides automatic failover and chooses the optimal path when a network connection fails.                                                                                                                                                                                                                                             | Dynamic BGP           |
      |                       | -  **Mail BGP**: EIPs with port 25, 465, or 587 enabled are used for email services.                                                                                                                                                                                                                                                                                  |                       |
      |                       |                                                                                                                                                                                                                                                                                                                                                                       |                       |
      |                       | The selected EIP type cannot be changed after the EIP is assigned.                                                                                                                                                                                                                                                                                                    |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Billed By             | Two options are available:                                                                                                                                                                                                                                                                                                                                            | Dedicated             |
      |                       |                                                                                                                                                                                                                                                                                                                                                                       |                       |
      |                       | -  **Dedicated**: The bandwidth can be used by only one EIP.                                                                                                                                                                                                                                                                                                          |                       |
      |                       | -  **Shared**: The bandwidth can be shared by multiple EIPs.                                                                                                                                                                                                                                                                                                          |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Bandwidth             | The bandwidth size in Mbit/s.                                                                                                                                                                                                                                                                                                                                         | 100                   |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | EIP Name              | The EIP name.                                                                                                                                                                                                                                                                                                                                                         | eip-test              |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Enterprise Project    | The enterprise project that the EIP belongs to.                                                                                                                                                                                                                                                                                                                       | default               |
      |                       |                                                                                                                                                                                                                                                                                                                                                                       |                       |
      |                       | An enterprise project facilitates project-level management and grouping of cloud resources and users. The name of the default project is **default**.                                                                                                                                                                                                                 |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Bandwidth Name        | The name of the bandwidth.                                                                                                                                                                                                                                                                                                                                            | bandwidth             |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Tag                   | The EIP tags. Each tag contains a key and value pair.                                                                                                                                                                                                                                                                                                                 | -  Key: Ipv4_key1     |
      |                       |                                                                                                                                                                                                                                                                                                                                                                       | -  Value: 3005eip     |
      |                       | The tag key and value must meet the requirements listed in :ref:`Table 2 <eip_0002__en-us_topic_0000001818982674_table36606052153313>`.                                                                                                                                                                                                                               |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Quantity              | The number of EIPs you want to assign.                                                                                                                                                                                                                                                                                                                                | 1                     |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

   .. _eip_0002__en-us_topic_0000001818982674_table36606052153313:

   .. table:: **Table 2** EIP tag requirements

      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Parameter             | Requirement                                                            | Example Value         |
      +=======================+========================================================================+=======================+
      | Key                   | -  Cannot be left blank.                                               | Ipv4_key1             |
      |                       | -  The key value must be unique for the same EIP.                      |                       |
      |                       | -  Can contain up to 36 characters.                                    |                       |
      |                       | -  Can contain only the following character types:                     |                       |
      |                       |                                                                        |                       |
      |                       |    -  Uppercase letters                                                |                       |
      |                       |    -  Lowercase letters                                                |                       |
      |                       |    -  Digits                                                           |                       |
      |                       |    -  Only hyphens (-), underscores (_), and at signs (@) are allowed. |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+
      | Value                 | -  Can contain up to 43 characters.                                    | 3005eip               |
      |                       | -  Can contain only the following character types:                     |                       |
      |                       |                                                                        |                       |
      |                       |    -  Uppercase letters                                                |                       |
      |                       |    -  Lowercase letters                                                |                       |
      |                       |    -  Digits                                                           |                       |
      |                       |    -  Only underscores (_), hyphens (-), and at signs (@) are allowed. |                       |
      +-----------------------+------------------------------------------------------------------------+-----------------------+

#. Click **Create Now**.

#. Click **Submit**.

Binding an EIP
--------------

#. On the **EIPs** page, locate the row that contains the target EIP, and click **Bind**.

#. Select the instance that you want to bind the EIP to.


   .. figure:: /_static/images/en-us_image_0000001865662761.png
      :alt: **Figure 2** Bind EIP

      **Figure 2** Bind EIP

#. Click **OK**.

An IPv6 client on the internet can access the ECS that has an EIP bound in a VPC. For details, see `How Does an IPv6 Client on the Internet Access the ECS That Has an EIP Bound in a VPC? <https://docs.otc.t-systems.com/virtual-private-cloud/umn/faq/connectivity/how_does_an_ipv6_client_on_the_internet_access_the_ecs_that_has_an_eip_bound_in_a_vpc.html#vpc-faq-0076>`__

Follow-Up Procedure
-------------------

After an ECS with an EIP bound is created, the system generates a domain name in the format of **ecs-**\ *xx-xx-xx-xx*\ **.compute.**\ *xxx*\ **.com** for the EIP by default. *xx-xx-xx-xx* indicates the EIP, and xxx indicates the domain name of the cloud service provider. You can use the domain name to access the ECS.

You can use any of the following commands to obtain the domain name of an EIP:

-  ping -an *EIP*
-  nslookup [-qt=ptr] *EIP*
-  dig -x *EIP*

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001818982822.png
