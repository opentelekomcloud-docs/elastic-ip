:original_name: monitor_0005.html

.. _monitor_0005:

Exporting Monitoring Data
=========================

Scenarios
---------

If you want to analyze the bandwidth or traffic usage of EIPs to locate faults, you can export EIP monitoring data.

Procedure
---------

#. Log in to the management console.

2. Click |image1| in the upper left corner and select the desired region and project.
3. Hover on the upper left corner to display **Service List** and choose **Management & Deployment** > **Cloud Eye**.
4. In the navigation pane on the left, choose **Cloud Service Monitoring** > **Elastic IP and Bandwidth**.
5. On the **Cloud Service Monitoring** page, click **Export Data**.
6. Configure the time range, resource type, dimension, monitored object, and metric.
7. Click **Export**.

-  The first row in the exported monitoring report displays the username, region, service, instance name, instance ID, metric name, metric data, time, and timestamp. You can view historical monitoring data.
-  To convert the time using a Unix timestamp to the time of the target time zone, perform the following steps:

   #. Use Excel to open a .csv file.

   #. Use the following formula to convert the time:

      Target time = [Unix timestamp/1000 + (Target time zone) x 3600]/86400 + 70 x 365 + 19

   #. Set cell format to **Date**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
