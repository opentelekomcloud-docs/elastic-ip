:original_name: eip_apitag_0004.html

.. _eip_apitag_0004:

Batch Creating or Deleting EIP Tags
===================================

Function
--------

This API is used to add multiple tags to or delete multiple tags from an EIP at a time.

This API is idempotent.

If there are duplicate keys in the request body when you add tags, an error is reported.

During tag creation, duplicate keys are not allowed. If a key already exists in the database, its value will be overwritten by the new duplicate key.

During tag deletion, if some tags do not exist, the operation is considered to be successful by default. The character set of the tags will not be checked. When you delete tags, the tag structure cannot be missing, and the key cannot be left blank or be an empty string.

URI
---

POST /v2.0/{project_id}/publicips/{publicip_id}/tags/action

:ref:`Table 1 <eip_apitag_0004__en-us_topic_0201534168_table27380479>` describes the parameters.

.. _eip_apitag_0004__en-us_topic_0201534168_table27380479:

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

      +-----------------+-------------------------------------------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type                                                                                      | Mandatory       | Description                                                                                                                       |
      +=================+===========================================================================================+=================+===================================================================================================================================+
      | tags            | Array of :ref:`tag <eip_apitag_0004__en-us_topic_0201534168_table13242848193719>` objects | Yes             | Specifies the **tag** object list. For details, see :ref:`Table 3 <eip_apitag_0004__en-us_topic_0201534168_table13242848193719>`. |
      +-----------------+-------------------------------------------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+
      | action          | String                                                                                    | Yes             | Specifies the operation. Possible values are as follows:                                                                          |
      |                 |                                                                                           |                 |                                                                                                                                   |
      |                 |                                                                                           |                 | -  **create**                                                                                                                     |
      |                 |                                                                                           |                 | -  **delete**                                                                                                                     |
      +-----------------+-------------------------------------------------------------------------------------------+-----------------+-----------------------------------------------------------------------------------------------------------------------------------+

   .. _eip_apitag_0004__en-us_topic_0201534168_table13242848193719:

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

-  Request example 1: Creating tags in batches

   .. code-block:: text

      POST https://{Endpoint}/v2.0/{project_id}/publicips/{publicip_id}/tags/action

      {
          "action": "create",
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

-  Request example 2: Deleting tags in batches

   .. code-block:: text

      POST https://{Endpoint}/v2.0/{project_id}/publicips/{publicip_id}/tags/action

      {
          "action": "delete",
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

See :ref:`Error Codes <errorcode>`.
