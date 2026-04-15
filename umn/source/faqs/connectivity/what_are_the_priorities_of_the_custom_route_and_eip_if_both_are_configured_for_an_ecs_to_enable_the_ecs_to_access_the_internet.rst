:original_name: faq_connect_0001.html

.. _faq_connect_0001:

What Are the Priorities of the Custom Route and EIP If Both Are Configured for an ECS to Enable the ECS to Access the Internet?
===============================================================================================================================

In a VPC route table, routes are matched by priority in the following order: Local route > specific route > EIP route > default route.

-  If the destination of a custom route is a specific IP address (not 0.0.0.0/0), it takes priority over the EIP route.
-  If the destination of a custom route is 0.0.0.0/0, it can match any traffic. In this case, the EIP route has a higher priority.

For more information about route priorities, see `Route Tables and Routes <https://docs.otc.t-systems.com/virtual-private-cloud/umn/route_tables/route_tables_and_routes.html>`__.
