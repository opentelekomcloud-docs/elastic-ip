:original_name: eip_apisharedbandwidth_0003.html

.. _eip_apisharedbandwidth_0003:

Deleting a Shared Bandwidth
===========================

Function
--------

This API is used to delete a shared bandwidth.

URI
---

DELETE /v2.0/{project_id}/bandwidths/{bandwidth_id}

:ref:`Table 1 <eip_apisharedbandwidth_0003__en-us_topic_0201534305_table45251091>` describes the parameters.

.. _eip_apisharedbandwidth_0003__en-us_topic_0201534305_table45251091:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | Name                  | Mandatory             | Description                                                          |
   +=======================+=======================+======================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                            |
   +-----------------------+-----------------------+----------------------------------------------------------------------+
   | bandwidth_id          | Yes                   | Specifies the bandwidth ID, which uniquely identifies the bandwidth. |
   |                       |                       |                                                                      |
   |                       |                       | Currently, only the shared bandwidth can be deleted.                 |
   +-----------------------+-----------------------+----------------------------------------------------------------------+

Request Message
---------------

-  Request parameter

   None

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v2.0/{project_id}/bandwidths/{bandwidth_id}

Response Message
----------------

-  Response parameter

   None

-  Example response

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
