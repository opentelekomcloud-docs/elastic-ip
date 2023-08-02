:original_name: eip_api02_0001.html

.. _eip_api02_0001:

API Overview
============

APIs provided by the EIP service include native OpenStack APIs and EIP APIs.

A combination of these two types of APIs allows you to use all functions provided by the EIP service.

Enterprise project users can only use EIP APIs. For details about API permissions, see :ref:`Permissions Policies and Supported Actions <eip_apipermission_0000>`.

.. table:: **Table 1** EIP APIs

   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | Type                  | Subtype                    | Description                                                                       |
   +=======================+============================+===================================================================================+
   | EIP API               | EIP                        | APIs for assigning, querying, updating, and releasing EIPs                        |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP API               | Floating IP address (IPv6) | APIs for assigning, querying, updating, and releasing IPv6 floating IP addresses  |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP API               | Bandwidth                  | APIs for querying and updating bandwidth                                          |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP API               | Bandwidth (v2.0)           | -  APIs for assigning and deleting shared bandwidth                               |
   |                       |                            | -  APIs for adding an EIP to or removing an EIP from a shared bandwidth           |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP API               | Quota                      | API for querying quota values                                                     |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP API               | EIP tag management         | APIs for adding tags to EIPs as well as querying and deleting EIP tags            |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | OpenStack Neutron API | Floating IP address        | APIs for assigning, querying, updating, and releasing floating IP addresses       |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | OpenStack Neutron API | API version                | APIs for querying all available API versions and displaying the results in pages. |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
   | EIP v3 API            | EIP (v3)                   | APIs for binding and unbinding EIPs.                                              |
   +-----------------------+----------------------------+-----------------------------------------------------------------------------------+
