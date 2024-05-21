:original_name: eip_0018.html

.. _eip_0018:

Adding EIPs to a Shared Bandwidth
=================================

Scenarios
---------

You can add multiple EIPs to a shared bandwidth to save costs.

Notes and Constraints
---------------------

-  The type of EIPs must be the same as that of the shared bandwidth the EIPs to be added to.
-  **5_gray** EIPs cannot be added to the same bandwidth as EIPs of other types. If they are in the same shared bandwidth, the bandwidth limit settings will not take effect.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.

3. Click |image2| in the upper left corner, and choose **Network** > **Elastic IP**.

4. In the navigation pane on the left, choose **Elastic IP and Bandwidth** > **EIPs**.

5. In the EIP list, locate the target EIP. In the **Operation** column, choose **More** > **Add to Shared Bandwidth**.


   .. figure:: /_static/images/en-us_image_0000001925251293.png
      :alt: **Figure 1** Adding an EIP to a shared bandwidth

      **Figure 1** Adding an EIP to a shared bandwidth

   .. note::

      -  After an EIP is added to a shared bandwidth, the dedicated bandwidth used by the EIP will become invalid and the EIP will start to use the shared bandwidth. The EIP will be removed from the original dedicated bandwidth.

6. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001925410917.png
.. |image2| image:: /_static/images/en-us_image_0000001879491934.png
