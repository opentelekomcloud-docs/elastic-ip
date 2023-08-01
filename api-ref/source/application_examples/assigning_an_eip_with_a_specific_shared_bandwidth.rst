:original_name: eip_apieg_0001.html

.. _eip_apieg_0001:

Assigning an EIP with a Specific Shared Bandwidth
=================================================

Scenarios
---------

This section describes how to assign an EIP with a specific shared bandwidth by calling APIs.

Prerequisites
-------------

If you use a token for authentication, you must obtain the token and add **X-Auth-Token** to the request header when making an API call.

.. note::

   The token obtained from IAM is valid for only 24 hours. If you want to use a token for authentication, you can cache it to avoid frequent calling.

Procedure
---------

#. Assign a shared bandwidth.

   a. Send **POST https://**\ *Endpoint*\ **/v2.0/**\ *project_id*\ **/bandwidths**. Parameter **project_id** indicates the project ID.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
              "bandwidth": {
                  "name": "bandwidth123",
                  "size": 10
              }
          }

   d. Check the response message.

      -  The request is successful if the following response is displayed. In the response, **id** indicates the bandwidth ID.

         .. code-block::

            {
               "bandwidth": {
                 "id": "1bffc5f2-ff19-45a6-96d2-dfdca49cc387",
                 "name": "bandwidth123",
                 "size": 10,
                 "share_type": "WHOLE",
                 "publicip_info": [],
                 "tenant_id": "26ae5181a416420998eb2093aaed84d9",
                 "bandwidth_type": "share",
                 "charge_mode": "bandwidth",
                 "enterprise_project_id": "0",
                 "status": "NORMAL",
                 "created_at": "2020-04-21T07:58:02Z",
                 "updated_at": "2020-04-21T07:58:02Z"
               }
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.

#. Query the shared bandwidth details.

   a. Send **Get https://**\ *Endpoint*\ **//v1/**\ *project_id*\ **/bandwidths/**\ *bandwidth_id*. Parameter **project_id** indicates the project ID.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response message.

      -  The request is successful if the following response is displayed. In the response, **id** indicates the bandwidth ID.

         .. code-block::

            {
                 "bandwidth": {
                     "id": "1bffc5f2-ff19-45a6-96d2-dfdca49cc387",
                     "name": "bandwidth123",
                     "size": 10,
                     "share_type": "WHOLE",
                     "publicip_info": [
                         {
                             "publicip_id": "ff156c26-bcc9-4541-a75c-42baf8b9748f",
                             "publicip_address": "114.xx.xx.244",
                             "ip_version": 4,
                             "publicip_type": "5_sbgp"
                         }
                     ],
                     "tenant_id": "b3292dde618e40408e30cd87455a0652",
                     "bandwidth_type": "sbgp",
                     "charge_mode": "bandwidth",
                     "enterprise_project_id": "0",
                     "status": "NORMAL",
                     "created_at": "2020-04-21T07:58:02Z",
                     "updated_at": "2020-04-21T07:58:02Z"
                 }
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.

#. Assign an EIP using the shared bandwidth.

   a. Send **POST https://**\ *Endpoint*\ **/v1/**\ *project_id*\ **/publicips**. Parameter **project_id** indicates the project ID.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
              "publicip": {
                  "type": "5_bgp",
                  "ip_version": 6
           },
              "bandwidth": {
                  "name": "bandwidth123",
                  "size": 10,
                  "share_type": "WHOLE",
                  "id":"1bffc5f2-ff19-45a6-96d2-dfdca49cc387"
              },
              "enterprise_project_id":"0"
          }

   d. Check the response message.

      -  The request is successful if the following response is displayed.

         .. code-block::

            {
                 "publicip": {
                     "id": "f588ccfa-8750-4d7c-bf5d-2ede24414706",
                     "status": "PENDING_CREATE",
                     "type": "5_bgp",
                     "public_ip_address": "161.xx.xx.7",
                     "tenant_id": "8b7e35ad379141fc9df3e178bd64f55c",
                     "ip_version": 4,
                     "create_time": "2015-07-16 04:10:52",
                     "bandwidth_size": 0,
                     "enterprise_project_id":"b261ac1f-2489-4bc7-b31b-c33c3346a439"
                 }
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.

#. Query EIP details.

   a. Send **GET /v1/**\ *project_id*\ **/publicips/**\ *publicip_id*. Parameter **project_id** indicates the project ID.

   b. Add **X-Auth-Token** to the request header.

   c. Check the response message.

      .. code-block::

         {
              "publicip": {
                     "id": "3ec9fea0-2d4c-49e2-8aca-ce883eae547d",
                     "type": "5_bgp",
                     "public_ip_address": "10.246.164.87",
                     "status": "DOWN",
                     "tenant_id": "060576782980d5762f9ec014dd2f1148",
                     "create_time": "2020-08-13 12:55:27",
                     "bandwidth_id": "1bffc5f2-ff19-45a6-96d2-dfdca49cc387",
                     "bandwidth_name": "bandwidth123",
                     "bandwidth_share_type": "WHOLE",
                     "bandwidth_size": 10,
                     "profile": {},
                     "enterprise_project_id": "a380829c-db6f-4db3-b5b6-cc377f7a3ff8",
                     "ip_version": 4
                 }
          }
