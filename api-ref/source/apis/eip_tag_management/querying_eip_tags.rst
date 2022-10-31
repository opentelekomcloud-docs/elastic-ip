:original_name: eip_apitag_0002.html

.. _eip_apitag_0002:

Querying EIP Tags
=================

Function
--------

This API is used to query tags of a specified EIP.

URI
---

GET /v2.0/{project_id}/publicips/{publicip_id}/tags

:ref:`Table 1 <eip_apitag_0002__en-us_topic_0201534160_table27380479>` describes the parameters.

.. _eip_apitag_0002__en-us_topic_0201534160_table27380479:

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

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v2.0/{project_id}/publicips/{publicip_id}/tags

Response Message
----------------

-  Response parameter

   .. table:: **Table 2** Response parameter

      +-----------+-------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Type                                                                                      | Description                                                                                                                       |
      +===========+===========================================================================================+===================================================================================================================================+
      | tags      | Array of :ref:`tag <eip_apitag_0002__en-us_topic_0201534160_table13242848193719>` objects | Specifies the **tag** object list. For details, see :ref:`Table 3 <eip_apitag_0002__en-us_topic_0201534160_table13242848193719>`. |
      +-----------+-------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apitag_0002__en-us_topic_0201534160_table13242848193719:

   .. table:: **Table 3** **tag** objects

      +-----------------------+-----------------------+---------------------------------------------------------------------+
      | Attribute             | Type                  | Description                                                         |
      +=======================+=======================+=====================================================================+
      | key                   | String                | -  Specifies the tag key.                                           |
      |                       |                       | -  Cannot be left blank.                                            |
      |                       |                       | -  Can contain a maximum of 36 characters.                          |
      |                       |                       | -  Can contain only the following character types:                  |
      |                       |                       |                                                                     |
      |                       |                       |    -  Uppercase letters                                             |
      |                       |                       |    -  Lowercase letters                                             |
      |                       |                       |    -  Digits                                                        |
      |                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
      |                       |                       |                                                                     |
      |                       |                       | -  The tag key of a VPC must be unique.                             |
      +-----------------------+-----------------------+---------------------------------------------------------------------+
      | value                 | String                | -  Specifies the tag value.                                         |
      |                       |                       | -  Can contain a maximum of 43 characters.                          |
      |                       |                       | -  Can contain only the following character types:                  |
      |                       |                       |                                                                     |
      |                       |                       |    -  Uppercase letters                                             |
      |                       |                       |    -  Lowercase letters                                             |
      |                       |                       |    -  Digits                                                        |
      |                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
      +-----------------------+-----------------------+---------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "tags": [
              {
                  "key": "key1",
                  "value": "value1"
              },
              {
                  "key": "key2",
                  "value": "value3"
              }
          ]
      }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <eip_api05_0002>`.
