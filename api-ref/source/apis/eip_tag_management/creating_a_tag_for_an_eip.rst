:original_name: eip_apitag_0001.html

.. _eip_apitag_0001:

Creating a Tag for an EIP
=========================

Function
--------

This API is used to create a tag for an EIP.

URI
---

POST /v2.0/{project_id}/publicips/{publicip_id}/tags

:ref:`Table 1 <eip_apitag_0001__en-us_topic_0201534118_table27380479>` describes the parameters.

.. _eip_apitag_0001__en-us_topic_0201534118_table27380479:

.. table:: **Table 1** Parameter description

   =========== ========= ==========================================
   Name        Mandatory Description
   =========== ========= ==========================================
   project_id  Yes       Specifies the project ID.
   publicip_id Yes       Specifies the unique identifier of an EIP.
   =========== ========= ==========================================

Request Message
---------------

-  Request parameter

   .. table:: **Table 2** Request parameter

      +-----------+---------------------------------------------------------------------------------+-----------+-------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type                                                                            | Mandatory | Description                                                                                                                   |
      +===========+=================================================================================+===========+===============================================================================================================================+
      | tag       | :ref:`tag <eip_apitag_0001__en-us_topic_0201534118_table13242848193719>` object | Yes       | Specifies the **tag** objects. For details, see :ref:`Table 3 <eip_apitag_0001__en-us_topic_0201534118_table13242848193719>`. |
      +-----------+---------------------------------------------------------------------------------+-----------+-------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apitag_0001__en-us_topic_0201534118_table13242848193719:

   .. table:: **Table 3** **tag** objects

      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
      | Attribute       | Type            | Mandatory       | Description                                                         |
      +=================+=================+=================+=====================================================================+
      | key             | String          | Yes             | -  Specifies the tag key.                                           |
      |                 |                 |                 | -  Cannot be left blank.                                            |
      |                 |                 |                 | -  Can contain a maximum of 36 characters.                          |
      |                 |                 |                 | -  Can contain only the following character types:                  |
      |                 |                 |                 |                                                                     |
      |                 |                 |                 |    -  Uppercase letters                                             |
      |                 |                 |                 |    -  Lowercase letters                                             |
      |                 |                 |                 |    -  Digits                                                        |
      |                 |                 |                 |    -  Special characters, including hyphens (-) and underscores (_) |
      |                 |                 |                 |                                                                     |
      |                 |                 |                 | -  The tag key of a VPC must be unique.                             |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+
      | value           | String          | Yes             | -  Specifies the tag value.                                         |
      |                 |                 |                 | -  Can contain a maximum of 43 characters.                          |
      |                 |                 |                 | -  Can contain only the following character types:                  |
      |                 |                 |                 |                                                                     |
      |                 |                 |                 |    -  Uppercase letters                                             |
      |                 |                 |                 |    -  Lowercase letters                                             |
      |                 |                 |                 |    -  Digits                                                        |
      |                 |                 |                 |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------+-----------------+-----------------+---------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v2.0/{project_id}/publicips/{publicip_id}/tags

      {
          "tag": {
              "key": "key1",
              "value": "value1"
          }
      }

Response Message
----------------

-  Response parameter

   None

-  Example response

   None

   Or

   .. code-block::

      {
             "code":"xxx",
             "message":"xxxxx"
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <eip_api05_0002>`.
