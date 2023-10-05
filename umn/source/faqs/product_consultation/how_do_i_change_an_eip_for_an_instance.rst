:original_name: faq_eip_0020.html

.. _faq_eip_0020:

How Do I Change an EIP for an Instance?
=======================================

Scenario 1: Changing an EIP for an ECS
--------------------------------------

Refer to :ref:`Assigning an EIP and Binding It to an ECS <eip_0002>` and :ref:`Unbinding an EIP from an ECS and Releasing the EIP <eip_0003>`.

Scenario 2: Changing an EIP for a Load Balancer
-----------------------------------------------

#. Unbind an EIP.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select the desired region and project.
   c. Click **Service List**. Under **Networking**, click **Elastic Load Balance**.
   d. In the load balancer list, locate the target load balancer and choose **More** > **Unbind EIP** in the **Operation** column.
   e. Click **Yes**.

#. Assign an EIP.

   a. Log in to the management console.
   b. Click |image2| in the upper left corner and select the desired region and project.
   c. Click |image3| in the upper left corner and choose **Network** > **Elastic IP**.
   d. On the displayed page, click **Assign EIP**.
   e. Set the parameters as prompted.
   f. Click **Create Now**.

#. Bind the new EIP to the load balancer.

   a. Log in to the management console.
   b. Click |image4| in the upper left corner and select the desired region and project.
   c. Click **Service List**. Under **Networking**, click **Elastic Load Balance**.
   d. In the load balancer list, locate the target load balancer and choose **More** > **Bind EIP** in the **Operation** column.
   e. In the **Bind EIP** dialog box, select the EIP to be bound and click **OK**.

#. Release the EIP that has been replaced.

   a. Log in to the management console.
   b. Click |image5| in the upper left corner and select the desired region and project.
   c. Click |image6| in the upper left corner and choose **Network** > **Elastic IP**.
   d. In the EIP list, locate the row that contains the target EIP, and click **Release**.
   e. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0000001388688657.png
.. |image2| image:: /_static/images/en-us_image_0000001618428593.png
.. |image3| image:: /_static/images/en-us_image_0000001595877226.png
.. |image4| image:: /_static/images/en-us_image_0000001338408584.png
.. |image5| image:: /_static/images/en-us_image_0000001567669964.png
.. |image6| image:: /_static/images/en-us_image_0000001596195138.png
