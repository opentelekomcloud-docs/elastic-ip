:original_name: faq_eip_0020.html

.. _faq_eip_0020:

How Do I Unbind an EIP from an Instance and Bind a New EIP to the Instance?
===========================================================================

Scenario 1: Unbinding an EIP from an ECS and Binding a New EIP to the ECS
-------------------------------------------------------------------------

For details, see :ref:`Assigning an EIP and Binding It to an ECS <eip_0002>` and :ref:`Unbinding an EIP from an ECS and Releasing the EIP <eip_0003>`.

Scenario 2: Unbinding an EIP from a Load Balancer and Binding a New EIP to the Load Balancer
--------------------------------------------------------------------------------------------

#. Unbind an EIP.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select the desired region and project.
   c. Click **Service List**. Under **Network**, click **Elastic Load Balancing**.
   d. In the load balancer list, locate the target load balancer and choose **More** > **Unbind IPv4 EIP** in the **Operation** column.
   e. Click **Yes**.

#. Assign an EIP.

   .. note::

      If you already have an EIP that you require, skip this step.

   a. Log in to the management console.
   b. Click |image2| in the upper left corner and select the desired region and project.
   c. Click |image3| in the upper left corner and choose **Network** > **Elastic IP**.
   d. On the displayed page, click **Assign EIP**.
   e. Set the parameters as prompted.
   f. Click **Create Now**.

#. Bind the new EIP to the load balancer.

   a. Log in to the management console.
   b. Click |image4| in the upper left corner and select the desired region and project.
   c. Click **Service List**. Under **Network**, click **Elastic Load Balancing**.
   d. In the load balancer list, locate the target load balancer and choose **More** > **Bind IPv4 EIP** in the **Operation** column.
   e. In the **Bind IPv4 EIP** dialog box, select the EIP to be bound and click **OK**.

#. Release the EIP that is unbound.

   .. note::

      If an unbound EIP is no longer required, you can release it.

   a. Log in to the management console.
   b. Click |image5| in the upper left corner and select the desired region and project.
   c. Click |image6| in the upper left corner and choose **Network** > **Elastic IP**.
   d. In the EIP list, locate the target EIP and click **Release**.
   e. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0000001890564517.png
.. |image2| image:: /_static/images/en-us_image_0000001890444945.png
.. |image3| image:: /_static/images/en-us_image_0000001890564529.png
.. |image4| image:: /_static/images/en-us_image_0000001890564513.png
.. |image5| image:: /_static/images/en-us_image_0000001844205350.png
.. |image6| image:: /_static/images/en-us_image_0000001844364098.png
