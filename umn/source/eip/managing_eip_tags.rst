:original_name: eip_0004.html

.. _eip_0004:

Managing EIP Tags
=================

Scenarios
---------

Tags can be added to EIPs to facilitate EIP identification and administration. You can add a tag to an EIP when assigning the EIP. Alternatively, you can add a tag to an assigned EIP on the EIP details page. A maximum of 20 tags can be added to each EIP.

A tag consists of a key and value pair. :ref:`Table 1 <eip_0004__en-us_topic_0118499005_ted9687ca14074ef785241145365a6175>` lists the tag key and value requirements.

.. _eip_0004__en-us_topic_0118499005_ted9687ca14074ef785241145365a6175:

.. table:: **Table 1** EIP tag requirements

   +-----------------------+---------------------------------------------------------------------+-----------------------+
   | Parameter             | Requirement                                                         | Example Value         |
   +=======================+=====================================================================+=======================+
   | Key                   | -  Cannot be left blank.                                            | Ipv4_key1             |
   |                       | -  Must be unique for each EIP.                                     |                       |
   |                       | -  Can contain a maximum of 36 characters.                          |                       |
   |                       | -  Can contain only the following character types:                  |                       |
   |                       |                                                                     |                       |
   |                       |    -  Uppercase letters                                             |                       |
   |                       |    -  Lowercase letters                                             |                       |
   |                       |    -  Digits                                                        |                       |
   |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
   +-----------------------+---------------------------------------------------------------------+-----------------------+
   | Value                 | -  Can contain a maximum of 43 characters.                          | 192.168.12.10         |
   |                       | -  Can contain only the following character types:                  |                       |
   |                       |                                                                     |                       |
   |                       |    -  Uppercase letters                                             |                       |
   |                       |    -  Lowercase letters                                             |                       |
   |                       |    -  Digits                                                        |                       |
   |                       |    -  Special characters, including hyphens (-) and underscores (_) |                       |
   +-----------------------+---------------------------------------------------------------------+-----------------------+

Procedure
---------

**Searching for EIPs by tag key and value on the page showing the EIP list**

#. Log in to the management console.

#. Click |image1| in the upper left corner and select the desired region and project.

#. On the console homepage, under **Network**, click **Elastic IP**.

#. In the upper right corner of the EIP list, click **Search by Tag**.

#. In the displayed area, enter the tag key and value of the EIP you are looking for.

   You must specify both the tag key and value. The system will display the EIPs that contain the tag you specified.

#. Click **+** to add another tag key and value.

   You can add multiple tag keys and values to refine your search results. If you add more than one tag to search for EIPs, the system will display only the EIPs that contain all of the tags you specified.

#. Click **Search**.

   The system displays the EIPs you are looking for based on the entered tag keys and values.

**Adding, deleting, editing, and viewing tags on the Tags tab of an EIP**

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the desired region and project.
#. On the console homepage, under **Network**, click **Elastic IP**.
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

      Locate the row that contains the tag you want to delete, and click **Delete** in the **Operation** column. In the displayed dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0141273034.png
.. |image2| image:: /_static/images/en-us_image_0141273034.png
