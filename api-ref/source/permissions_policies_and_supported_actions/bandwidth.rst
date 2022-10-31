:original_name: eip_apipermission_0003.html

.. _eip_apipermission_0003:

Bandwidth
=========

+----------------------+------------------------------------------------+-----------------------+
| Permission           | API                                            | Action                |
+======================+================================================+=======================+
| Queries a bandwidth. | GET /v1/{project_id}/bandwidths/{bandwidth_id} | vpc:bandwidths:get    |
+----------------------+------------------------------------------------+-----------------------+
| Queries bandwidths.  | GET /v1/{project_id}/bandwidths                | vpc:bandwidths:list   |
+----------------------+------------------------------------------------+-----------------------+
| Updates a bandwidth. | PUT /v1/{project_id}/bandwidths/{bandwidth_id} | vpc:bandwidths:update |
+----------------------+------------------------------------------------+-----------------------+
