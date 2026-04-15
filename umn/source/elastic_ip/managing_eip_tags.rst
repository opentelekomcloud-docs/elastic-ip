:original_name: eip_0004.html

.. _eip_0004:

Managing EIP Tags
=================

Scenarios
---------

Tags can be added to EIPs to facilitate EIP identification and administration. You can add a tag to an EIP when assigning the EIP. Alternatively, you can add a tag to an assigned EIP on the EIP details page. A maximum of 20 tags can be added to each EIP.

A tag consists of a key and value pair. :ref:`Table 1 <eip_0004__en-us_topic_0000001818822710_ted9687ca14074ef785241145365a6175>` lists the tag key and value requirements.

.. _eip_0004__en-us_topic_0000001818822710_ted9687ca14074ef785241145365a6175:

.. table:: **Table 1** EIP tag requirements

   +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
   | Parameter             | Requirements                                                                                     | Example Value         |
   +=======================+==================================================================================================+=======================+
   | Key                   | -  For each resource, each tag key must be unique, and each tag key can only have one tag value. | Ipv4_key1             |
   |                       | -  Cannot be left blank.                                                                         |                       |
   |                       | -  Can contain a maximum of 128 characters.                                                      |                       |
   |                       | -  Cannot start or end with a space.                                                             |                       |
   +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+
   | Value                 | -  Can be left blank.                                                                            | 3005eip               |
   |                       | -  Can contain a maximum of 255 characters.                                                      |                       |
   |                       | -  Cannot start or end with a space.                                                             |                       |
   +-----------------------+--------------------------------------------------------------------------------------------------+-----------------------+

Procedure
---------

**Searching for EIPs by tag key and value on the page showing the EIP list**

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. Click |image2| in the upper left corner, and choose **Network** > **Elastic IP**.

#. In the search box above the EIP list, click anywhere in the box to set filters.

#. Click the tag key and then the value as required. The system filters resources based on the tag you select.

#. Click anywhere in the search box to add the next tag key and value.

   You can add multiple tag keys and values to refine your search results. If you add more than one tag to search for EIPs, the system will display only the EIPs that match all of the tags you specified.

**Adding, deleting, editing, and viewing tags on the Tags tab of an EIP**

#. Log in to the management console.

#. Click |image3| in the upper left corner and select the desired region and project.

#. Click |image4| in the upper left corner, and choose **Network** > **Elastic IP**.

#. On the displayed page, locate the EIP whose tags you want to manage, and click the EIP name.

   The EIP details page is displayed.

#. Click the **Tags** tab and then click **Edit Tag** in the upper left corner above the tag list.

   The **Edit Tag** page is displayed.

#. Perform the following operations on the tags as required:

   -  Adding a tag: Click |image5|, enter a tag key and value, and click **OK**.
   -  Modifying a tag: Click |image6| next to the target tag key or value to delete the original value, enter a new value, and click **OK**.
   -  Deleting a tag: Click **Delete** next to the target tag and click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001818982822.png
.. |image3| image:: /_static/images/en-us_image_0000001818982734.png
.. |image4| image:: /_static/images/en-us_image_0000001818982822.png
.. |image5| image:: /_static/images/en-us_image_0000002555651817.png
.. |image6| image:: /_static/images/en-us_image_0000002555531839.png
