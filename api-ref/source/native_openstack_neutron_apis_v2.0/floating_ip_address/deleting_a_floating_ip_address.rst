:original_name: eip_openstackapi_0010.html

.. _eip_openstackapi_0010:

Deleting a Floating IP Address
==============================

Function
--------

This API is used to delete a floating IP address.

URI
---

DELETE /v2.0/floatingips/{floatingip_id}

:ref:`Table 1 <eip_openstackapi_0010__en-us_topic_0201534157_table49321613135118>` describes the parameters.

.. _eip_openstackapi_0010__en-us_topic_0201534157_table49321613135118:

.. table:: **Table 1** Parameter description

   ============= ========= ====== =====================================
   Parameter     Mandatory Type   Description
   ============= ========= ====== =====================================
   floatingip_id Yes       String Specifies the floating IP address ID.
   ============= ========= ====== =====================================

Request Message
---------------

None

Response Message
----------------

None

Example:
--------

Example request

.. code-block:: text

   DELETE https://{Endpoint}/v2.0/floatingips/a95ec431-8473-463b-aede-34fb048ee3a7

Example response

None

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <eip_api05_0002>`.
