:original_name: DeletePublicIp.html

.. _DeletePublicIp:

Releasing an EIP
================

Function
--------

Release an EIP.

URI
---

DELETE /v3/{project_id}/eip/publicips/{publicip_id}

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+----------------------------+
   | Parameter       | Mandatory       | Type            | Description                |
   +=================+=================+=================+============================+
   | project_id      | Yes             | String          | -  Definition: Project ID. |
   |                 |                 |                 |                            |
   |                 |                 |                 | -  Range: None             |
   |                 |                 |                 |                            |
   |                 |                 |                 | Maximum: **32**            |
   +-----------------+-----------------+-----------------+----------------------------+
   | publicip_id     | Yes             | String          | EIP ID.                    |
   |                 |                 |                 |                            |
   |                 |                 |                 | Maximum: **36**            |
   +-----------------+-----------------+-----------------+----------------------------+

Request Parameters
------------------

None

Response Parameters
-------------------

**Status code: 204**

Normal response to DELETE operations

None

Example Requests
----------------

None

Example Responses
-----------------

None

Status Codes
------------

=========== ====================================
Status Code Description
=========== ====================================
204         Normal response to DELETE operations
=========== ====================================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
