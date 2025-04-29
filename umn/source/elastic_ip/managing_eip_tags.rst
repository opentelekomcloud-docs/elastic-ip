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

   +-----------------------+------------------------------------------------------------------------+-----------------------+
   | Parameter             | Requirement                                                            | Example Value         |
   +=======================+========================================================================+=======================+
   | Key                   | -  Cannot be left blank.                                               | Ipv4_key1             |
   |                       | -  Must be unique for each EIP.                                        |                       |
   |                       | -  Can contain a maximum of 36 characters.                             |                       |
   |                       | -  Can contain only the following character types:                     |                       |
   |                       |                                                                        |                       |
   |                       |    -  Uppercase letters                                                |                       |
   |                       |    -  Lowercase letters                                                |                       |
   |                       |    -  Digits                                                           |                       |
   |                       |    -  Only hyphens (-), underscores (_), and at signs (@) are allowed. |                       |
   +-----------------------+------------------------------------------------------------------------+-----------------------+
   | Value                 | -  Can contain a maximum of 43 characters.                             | 3005eip               |
   |                       | -  Can contain only the following character types:                     |                       |
   |                       |                                                                        |                       |
   |                       |    -  Uppercase letters                                                |                       |
   |                       |    -  Lowercase letters                                                |                       |
   |                       |    -  Digits                                                           |                       |
   |                       |    -  Only underscores (_), hyphens (-), and at signs (@) are allowed. |                       |
   +-----------------------+------------------------------------------------------------------------+-----------------------+

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
#. On the page showing EIP details, click the **Tags** tab and perform desired operations on tags.

   -  View tags.

      On the **Tags** tab, you can view details about tags added to the current EIP, including the number of tags and the key and value of each tag.

   -  Add a tag.

      Click **Add Tag** in the upper left corner. In the displayed **Add Tag** dialog box, enter the tag key and value, and click **OK**.

   -  Edit a tag.

      Locate the row that contains the tag you want to edit, and click **Edit** in the **Operation** column. Enter the new tag value, and click **OK**.

      The tag key cannot be modified.

   -  Delete a tag.

      Locate the row that contains the tag you want to delete, and click **Delete** in the **Operation** column. In the displayed dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001818982734.png
.. |image2| image:: /_static/images/en-us_image_0000001818982822.png
.. |image3| image:: /_static/images/en-us_image_0000001818982734.png
.. |image4| image:: /_static/images/en-us_image_0000001818982822.png
