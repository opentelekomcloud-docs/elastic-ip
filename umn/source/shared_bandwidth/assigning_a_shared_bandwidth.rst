:original_name: bandwidth_0003.html

.. _bandwidth_0003:

Assigning a Shared Bandwidth
============================

Scenarios
---------

Assign a shared bandwidth for use with EIPs.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Elastic IP**.

#. In the navigation pane on the left, choose **Elastic IP and Bandwidth** > **Shared Bandwidths**.

#. In the upper right corner, click **Assign Shared Bandwidth**. On the displayed page, configure parameters as prompted.


   .. figure:: /_static/images/en-us_image_0000001163949251.png
      :alt: **Figure 1** Assigning Shared Bandwidth

      **Figure 1** Assigning Shared Bandwidth

   .. table:: **Table 1** Parameter descriptions

      +----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Parameter      | Description                                                                                                                                                                                                                                                                                             | Example Value |
      +================+=========================================================================================================================================================================================================================================================================================================+===============+
      | Region         | Regions are geographic areas that are physically isolated from each other. The networks inside different regions are not connected to each other, so resources cannot be shared across different regions. For lower network latency and faster access to your resources, select the region nearest you. | eu-de         |
      +----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Bandwidth      | The bandwidth size in Mbit/s. The value ranges from starting with 5 Mbit/s. The maximum bandwidth can be 1000 Mbit/s.                                                                                                                                                                                   | 10            |
      +----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+
      | Bandwidth Name | The name of the shared bandwidth.                                                                                                                                                                                                                                                                       | Bandwidth-001 |
      +----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------+

#. Click **Create Now**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
