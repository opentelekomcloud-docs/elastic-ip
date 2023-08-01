:original_name: eip_apieg_0002.html

.. _eip_apieg_0002:

Binding an EIP to an ECS
========================

Scenarios
---------

This section describes how to bind an EIP to an ECS by calling APIs.

Prerequisites
-------------

-  You have created an ECS. For details, see section "Purchasing an ECS with Customized Configurations" in the *Elastic Cloud Server User Guide*.
-  If you use a token for authentication, you must obtain the token and add **X-Auth-Token** to the request header when making an API call.

   .. note::

      The token obtained from IAM is valid for only 24 hours. If you want to use a token for authentication, you can cache it to avoid frequent calling.

Procedure
---------

#. Obtain the NIC information based on the ECS ID. For details, see section "Querying a Port" in the *Virtual Private Cloud API Reference*.

   a. Send **GET https://**\ *VPC endpoint*\ **/v1/**\ *project_id*\ **/ports?device_id=**\ *ecs_id*. Parameter **project_id** indicates the project ID.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response message.

      -  The request is successful if the following response is displayed.

         .. code-block::

            {
                 "ports": [{
                     "id": "02c72193-efec-42fb-853b-c33f2b802467",
                     "name": "",
                     "status": "ACTIVE",
                     "admin_state_up": true,
                     "fixed_ips": [{
                         "subnet_id": "213cb9d-3122-2ac1-1a29-91ffc1231a12",
                         "ip_address": "192.168.0.75"
                     }],
                     "mac_address": "fa:16:3e:47:5f:c1",
                     "network_id": "4779ab1c-7c1a-44b1-a02e-93dfc361b32d",
                     "tenant_id": "db82c9e1415a464ea68048baa8acc6b8",
                     "project_id": "db82c9e1415a464ea68048baa8acc6b8",
                     "device_id": "ea61f836-b52f-41bf-9d06-685644001d6f",
                     "device_owner": "compute:br-iaas-odin1a",
                     "security_groups": [
                         "e0598d96-9451-4f8a-8de0-b8b4d451d9e7"
                     ],
                     "extra_dhcp_opts": [],
                     "allowed_address_pairs": [],
                     "binding:vnic_type": "normal",
                     "binding:vif_details": {
                         "primary_interface": true
                     },
                     "binding:profile": {},
                     "port_security_enabled": true,
                     "created_at": "2020-06-20T08:07:29",
                     "updated_at": "2020-06-20T08:07:29"
                 }]
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.

#. Assign an EIP.

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
                  "size": 5,
                  "share_type": "WHOLE",
                  "id":"ebfa375c-3f93-465e-81a3-bd66e578ee9d"
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

#. Bind the EIP to the ECS NIC.

   a. Send **PUT /v1/**\ *project_id*\ **/publicips/**\ *publicip_id*. Parameter **project_id** indicates the project ID.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
              "publicip": {
                  "port_id": "02c72193-efec-42fb-853b-c33f2b802467"
              }
          }

   d. Check the response message.

      -  The request is successful if the following response is displayed.

         .. code-block::

            {
               "publicip": {
                 "id": "f588ccfa-8750-4d7c-bf5d-2ede24414706",
                 "status": "ACTIVE",
                 "type": "5_bgp",
                 "port_id": "02c72193-efec-42fb-853b-c33f2b802467",
                 "public_ip_address": "10.xx.xx.162",
                 "private_ip_address": "192.168.1.131",
                 "tenant_id": "26ae5181a416420998eb2093aaed84d9",
                 "create_time": "2019-03-27 01:33:18",
                 "bandwidth_id": "02da78da-4fb0-4880-b512-f516cdeb8ef3",
                 "bandwidth_name": "test",
                 "bandwidth_share_type": "PER",
                 "bandwidth_size": 1,
                 "profile": {},
                 "enterprise_project_id": "0",
                 "ip_version": 4
               }
             }

      -  For details about the error codes when the request is abnormal, see :ref:`Error Codes <errorcode>`.
