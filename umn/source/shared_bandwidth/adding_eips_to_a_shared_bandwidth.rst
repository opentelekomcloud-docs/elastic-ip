:original_name: bandwidth_0004.html

.. _bandwidth_0004:

Adding EIPs to a Shared Bandwidth
=================================

Scenarios
---------

Add EIPs to a shared bandwidth and the EIPs can then share that bandwidth. You can add multiple EIPs to a shared bandwidth at the same time.

Notes and Constraints
---------------------

-  The type of EIPs must be the same as that of the shared bandwidth the EIPs to be added to.
-  Do not add EIPs of the dedicated load balancer type (**5_gray**) and other types to the same shared bandwidth. Otherwise, the bandwidth limit policy will not take effect.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. Click |image2| in the upper left corner, and choose **Network** > **Elastic IP**.

4. In the navigation pane on the left, choose **Elastic IP and Bandwidth** > **Shared Bandwidths**.

5. In the shared bandwidth list, locate the target shared bandwidth that you want to add EIPs to. In the **Operation** column, choose **Add Public IP Address**, and select the EIPs or IPv6 addresses to be added.


   .. figure:: /_static/images/en-us_image_0000002065101369.png
      :alt: **Figure 1** Adding an EIP

      **Figure 1** Adding an EIP


   .. figure:: /_static/images/en-us_image_0000002065187445.png
      :alt: **Figure 2** Adding an IPv6 address

      **Figure 2** Adding an IPv6 address

   .. note::

      -  After an EIP is added to a shared bandwidth, the dedicated bandwidth used by the EIP will become invalid and the EIP will start to use the shared bandwidth. The EIP will be removed from the original dedicated bandwidth.

6. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001818982822.png
