:original_name: eip_0003.html

.. _eip_0003:

Unbinding an EIP from an ECS and Releasing the EIP
==================================================

Scenarios
---------

If you no longer need an EIP, unbind it from the ECS and release the EIP to avoid wasting network resources.

Notes and Constraints
---------------------

-  In **eu-de**, EIPs of the Dedicated Load Balancer (**5_gray**) type cannot be assigned anymore. You can assign EIPs of the BGP (**5_bgp**) type.
-  Existing EIPs of the Dedicated Load Balancer (**5_gray**) type can be bound to dedicated or shared load balancers.

   -  The EIP console cannot be used to bind EIPs to or unbind them from dedicated load balancers.
   -  You can use APIs to bind EIPs to or unbind them from dedicated load balancers. For details, see `Binding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/binding_an_eip.html>`__ and `Unbinding an EIP <https://docs.otc.t-systems.com/elastic-ip/api-ref/api_v3/eips/unbinding_an_eip.html>`__.
   -  EIPs of this type can be bound to or unbound from shared load balancers using the EIP console or APIs.
   -  You are advised to bind BGP EIPs to or unbind them from dedicated load balancers.

-  EIP assigned together with your load balancers will also be displayed in the EIP list.
-  You can only release EIPs that are not bound to any resources.

Procedure
---------

**Unbinding a single EIP**

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the desired region and project.
#. Click |image2| in the upper left corner and choose **Network** > **Elastic IP**.
#. On the displayed page, locate the row that contains the target EIP, and click **Unbind**.
#. Click **Yes** in the displayed dialog box.

**Releasing a single EIP**

#. Log in to the management console.
#. Click |image3| in the upper left corner and select the desired region and project.
#. Click |image4| in the upper left corner and choose **Network** > **Elastic IP**.
#. On the displayed page, locate the row that contains the target EIP, click **More** and then **Release** in the **Operation** column.
#. Click **Yes** in the displayed dialog box.

**Unbinding multiple EIPs at once**

#. Log in to the management console.
#. Click |image5| in the upper left corner and select the desired region and project.
#. Click |image6| in the upper left corner and choose **Network** > **Elastic IP**.
#. On the displayed page, select the EIPs to be unbound.
#. Click the **Unbind** button located above the EIP list.
#. Click **Yes** in the displayed dialog box.

**Releasing multiple EIPs at once**

#. Log in to the management console.
#. Click |image7| in the upper left corner and select the desired region and project.
#. Click |image8| in the upper left corner and choose **Network** > **Elastic IP**.
#. On the displayed page, select the EIPs to be released.
#. Click the **Release** button located above the EIP list.
#. Click **Yes** in the displayed dialog box.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0000001454059512.png
.. |image3| image:: /_static/images/en-us_image_0141273034.png
.. |image4| image:: /_static/images/en-us_image_0000001454059512.png
.. |image5| image:: /_static/images/en-us_image_0141273034.png
.. |image6| image:: /_static/images/en-us_image_0000001454059512.png
.. |image7| image:: /_static/images/en-us_image_0141273034.png
.. |image8| image:: /_static/images/en-us_image_0000001454059512.png
