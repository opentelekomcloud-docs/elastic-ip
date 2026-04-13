:original_name: eip_apitag_0003.html

.. _eip_apitag_0003:

Deleting a Tag from an EIP
==========================

Function
--------

This API is used to delete a tag from an EIP.

URI
---

DELETE /v2.0/{project_id}/publicips/{publicip_id}/tags/{key}

:ref:`Table 1 <eip_apitag_0003__en-us_topic_0201534220_table5716115334>` describes the parameters.

.. _eip_apitag_0003__en-us_topic_0201534220_table5716115334:

.. table:: **Table 1** Parameter description

   =========== ========= ==========================================
   Parameter   Mandatory Description
   =========== ========= ==========================================
   project_id  Yes       Specifies the project ID.
   publicip_id Yes       Specifies the unique identifier of an EIP.
   key         Yes       Specifies the tag key.
   =========== ========= ==========================================

Request Parameters
------------------

-  Request parameter

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2.0/{project_id}/publicips/{publicip_id}/tags/{key}

Response Parameters
-------------------

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
