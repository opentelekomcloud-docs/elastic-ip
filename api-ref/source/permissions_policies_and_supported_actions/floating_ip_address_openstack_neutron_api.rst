:original_name: eip_apipermission_0006.html

.. _eip_apipermission_0006:

Floating IP Address (OpenStack Neutron API)
===========================================

+--------------------------------+------------------------------------------+------------------------+
| Permission                     | API                                      | Action                 |
+================================+==========================================+========================+
| Querying floating IP addresses | GET /v2.0/floatingips                    | vpc:floatingIps:get    |
+--------------------------------+------------------------------------------+------------------------+
| Querying a floating IP address | GET /v2.0/floatingips/{floatingip_id}    | vpc:floatingIps:get    |
+--------------------------------+------------------------------------------+------------------------+
| Creating a floating IP address | POST /v2.0/floatingips                   | vpc:floatingIps:create |
+--------------------------------+------------------------------------------+------------------------+
| Updating a floating IP address | PUT /v2.0/floatingips/{floatingip_id}    | vpc:floatingIps:update |
+--------------------------------+------------------------------------------+------------------------+
| Deleting a floating IP address | DELETE /v2.0/floatingips/{floatingip_id} | vpc:floatingIps:delete |
+--------------------------------+------------------------------------------+------------------------+
