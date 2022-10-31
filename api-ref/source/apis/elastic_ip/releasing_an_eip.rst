:original_name: eip_api_0005.html

.. _eip_api_0005:

Releasing an EIP
================

Function
--------

This API is used to release an EIP.

URI
---

DELETE /v1/{project_id}/publicips/{publicip_id}

:ref:`Table 1 <eip_api_0005__en-us_topic_0201534180_table45251091>` describes the parameters.

.. _eip_api_0005__en-us_topic_0201534180_table45251091:

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

      DELETE https://{Endpoint}/v1/{project_id}/publicips

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
