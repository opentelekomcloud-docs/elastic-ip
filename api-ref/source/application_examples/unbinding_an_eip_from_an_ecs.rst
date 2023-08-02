:original_name: eip_apieg_0003.html

.. _eip_apieg_0003:

Unbinding an EIP from an ECS
============================

Scenarios
---------

This section describes how to unbind an EIP from an ECS by calling APIs.

Prerequisites
-------------

-  You have created an ECS. For details, see section "Purchasing an ECS with Customized Configurations" in the *Elastic Cloud Server User Guide*.
-  If you use a token for authentication, you must obtain the token and add **X-Auth-Token** to the request header when making an API call.

   .. note::

      The token obtained from IAM is valid for only 24 hours. If you want to use a token for authentication, you can cache it to avoid frequent calling.

Procedure
---------

#. Query EIP details.

   a. Send **GET /v1/**\ *project_id*\ **/publicips/**\ *publicip_id*. Parameter **project_id** indicates the project ID.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response message.

      -  The request is successful if the following response is displayed.

         .. code-block::

            {
               "publicip": {
                 "id": "f6318bef-6508-4ea5-a48f-6152b6b1a8fb",
                 "status": "ACTIVE",
                 "type": "5_bgp",
                 "port_id": "a135e9b8-1630-40d2-a6c5-eb534a61efbe",
                 "public_ip_address": "10.xx.xx.162",
                 "private_ip_address": "192.168.1.131",
                 "port_id": "a135e9b8-1630-40d2-a6c5-eb534a61efbe",
                 "tenant_id": "26ae5181a416420998eb2093aaed84d9",
                 "create_time": "2019-03-27 01:33:18",
                 "bandwidth_id": "02da78da-4fb0-4880-b512-f516cdeb8ef3",
                 "bandwidth_name": "test",
                 "bandwidth_share_type": "PER",
                 "bandwidth_size": 1,
                 "enterprise_project_id": "0",
                 "profile": {},
                 "ip_version": 4
               }
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.

#. Unbind the EIP from the ECS NIC.

   a. Send **PUT /v1/**\ *project_id*\ **/publicips/**\ *publicip_id*. Parameter **project_id** indicates the project ID.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
              "publicip": {
                  "port_id": ""
              }
          }

   a. Check the response message.

      -  The request is successful if the following response is displayed.

         .. code-block::

            {
               "publicip": {
                 "id": "f6318bef-6508-4ea5-a48f-6152b6b1a8fb",
                 "status": "DOWN",
                 "type": "5_bgp",
                 "public_ip_address": "10.xx.xx.162",
                 "bandwidth_id": "02da78da-4fb0-4880-b512-f516cdeb8ef3",
                 "bandwidth_name": "test",
                 "bandwidth_share_type": "PER",
                 "bandwidth_size": 1,
                 "tenant_id": "26ae5181a416420998eb2093aaed84d9",
                 "create_time": "2019-03-27 01:33:18",
                 "enterprise_project_id": "0",
                 "profile": {}
                 "ip_version": 4
               }
             }

   -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.
