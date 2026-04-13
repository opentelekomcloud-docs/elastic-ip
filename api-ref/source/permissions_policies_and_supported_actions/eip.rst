:original_name: eip_apipermission_0002.html

.. _eip_apipermission_0002:

EIP
===

+------------------+-------------------------------------------------+----------------------+
| Permission       | API                                             | Action               |
+==================+=================================================+======================+
| Assigning an EIP | POST /v1/{project_id}/publicips                 | vpc:publicIps:create |
+------------------+-------------------------------------------------+----------------------+
| Querying an EIP  | GET /v1/{project_id}/publicips/{publicip_id}    | vpc:publicIps:get    |
+------------------+-------------------------------------------------+----------------------+
| Querying EIPs    | GET /v1/{project_id}/publicips                  | vpc:publicIps:list   |
+------------------+-------------------------------------------------+----------------------+
| Updating an EIP  | PUT /v1/{project_id}/publicips/{publicip_id}    | vpc:publicIps:update |
+------------------+-------------------------------------------------+----------------------+
| Releasing an EIP | DELETE /v1/{project_id}/publicips/{publicip_id} | vpc:publicIps:delete |
+------------------+-------------------------------------------------+----------------------+
