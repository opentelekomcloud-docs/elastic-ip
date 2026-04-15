:original_name: eip_apipermission_0003.html

.. _eip_apipermission_0003:

Bandwidth
=========

+----------------------+------------------------------------------------+-----------------------+
| Permission           | API                                            | Action                |
+======================+================================================+=======================+
| Querying a bandwidth | GET /v1/{project_id}/bandwidths/{bandwidth_id} | vpc:bandwidths:get    |
+----------------------+------------------------------------------------+-----------------------+
| Querying bandwidths  | GET /v1/{project_id}/bandwidths                | vpc:bandwidths:list   |
+----------------------+------------------------------------------------+-----------------------+
| Updating a bandwidth | PUT /v1/{project_id}/bandwidths/{bandwidth_id} | vpc:bandwidths:update |
+----------------------+------------------------------------------------+-----------------------+
