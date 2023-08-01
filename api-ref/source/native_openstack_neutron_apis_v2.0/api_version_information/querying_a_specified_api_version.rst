:original_name: eip_openstackapi_0003.html

.. _eip_openstackapi_0003:

Querying a Specified API Version
================================

Function
--------

This API is used to query the version of a specified API.

URI
---

GET /{api_version}

:ref:`Table 1 <eip_openstackapi_0003__en-us_topic_0201534145_table8488410142319>` describes the parameters.

.. _eip_openstackapi_0003__en-us_topic_0201534145_table8488410142319:

.. table:: **Table 1** Parameter description

   =========== ====== ===================================================
   Parameter   Type   Description
   =========== ====== ===================================================
   api_version String Specifies the version number, for example **v2.0**.
   =========== ====== ===================================================

Request Parameters
------------------

None

Example Request
---------------

.. code-block:: text

   GET https://{Endpoint}/v2.0

Response Parameters
-------------------

.. table:: **Table 2** Response parameter

   +-----------+-----------------------------------------------------------------------------------------------------+-----------------------------------------+
   | Parameter | Type                                                                                                | Description                             |
   +===========+=====================================================================================================+=========================================+
   | resources | Array of :ref:`resource <eip_openstackapi_0003__en-us_topic_0201534145_table1195920258372>` objects | Specifies the **resource** object list. |
   +-----------+-----------------------------------------------------------------------------------------------------+-----------------------------------------+

.. _eip_openstackapi_0003__en-us_topic_0201534145_table1195920258372:

.. table:: **Table 3** **resource** object

   +------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type                                                                                            | Description                                                                                                                  |
   +============+=================================================================================================+==============================================================================================================================+
   | name       | String                                                                                          | Specifies the resource name.                                                                                                 |
   +------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
   | collection | String                                                                                          | Specifies the resource collection name.                                                                                      |
   +------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+
   | links      | Array of :ref:`link <eip_openstackapi_0003__en-us_topic_0201534145_table4442151110172>` objects | Specifies the link list. For details, see :ref:`Table 4 <eip_openstackapi_0003__en-us_topic_0201534145_table4442151110172>`. |
   +------------+-------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------+

.. _eip_openstackapi_0003__en-us_topic_0201534145_table4442151110172:

.. table:: **Table 4** **link** objects

   +-----------+--------+----------------------------------------------------------------------+
   | Parameter | Type   | Description                                                          |
   +===========+========+======================================================================+
   | href      | String | Specifies the API link.                                              |
   +-----------+--------+----------------------------------------------------------------------+
   | rel       | String | Specifies the relationship between the API link and the API version. |
   +-----------+--------+----------------------------------------------------------------------+

Example Response
----------------

.. code-block::

   {
       "resources": [
           {
               "links": [
                   {
                       "href": "https://vpc.systems.com/v2.0/subnets",
                       "rel": "self"
                   }
               ],
               "name": "subnet",
               "collection": "subnets"
           },
           {
               "links": [
                   {
                       "href": "https://vpc.systems.com/v2.0/networks",
                       "rel": "self"
                   }
               ],
               "name": "network",
               "collection": "networks"
           },
           {
               "links": [
                   {
                       "href": "https://vpc.systems.com/v2.0/ports",
                       "rel": "self"
                   }
               ],
               "name": "port",
               "collection": "ports"
           }
       ]
   }

Status Code
-----------

See :ref:`Status Codes <eip_api05_0001>`.

Error Code
----------

See :ref:`Error Codes <errorcode>`.
