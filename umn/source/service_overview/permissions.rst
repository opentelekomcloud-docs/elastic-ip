:original_name: overview_permission.html

.. _overview_permission:

Permissions
===========

If you need to assign different permissions to employees in your enterprise to access your EIP resources, IAM is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, helping you securely manage access to your resources.

With IAM, you can use your to create IAM users, and assign permissions to the users to control their access to specific resources. For example, some software developers in your enterprise need to use EIP resources but should not be allowed to delete them or perform any high-risk operations. In this scenario, you can create IAM users for the software developers and grant them only the permissions required for using EIP resources.

If your does not need individual IAM users for permissions management, you may skip over this section.

IAM can be used free of charge. You pay only for the resources in your account. For more information, see `IAM Service Overview <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__.

EIP Permissions
---------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

Currently, EIP permissions are included in VPC permissions.

VPC is a project-level service deployed for specific regions. When you set **Scope** to **Region-specific projects** and select the specified projects in the specified regions , the users only have permissions for VPCs in the selected projects. If you set **Scope** to **All resources**, users have permissions for VPCs in all region-specific projects. When accessing VPCs, the users need to switch to the authorized region.

You can grant permissions by using roles and policies.

-  Roles: A coarse-grained authorization strategy provided by IAM to assign permissions based on users' job responsibilities. Only a limited number of service-level roles are available for authorization. When you grant permissions using roles, you also need to attach dependent roles. Roles are not ideal for fine-grained authorization and least privilege access.
-  Policies: A fine-grained authorization strategy that defines permissions required to perform operations on specific cloud resources under certain conditions. This type of authorization is more flexible and is ideal for least privilege access. For example, you can grant VPC users only the permissions for managing a certain type of resources. A majority of fine-grained policies contain permissions for specific APIs, and permissions are defined using API actions. For the API actions supported by VPC, see `Permissions Policies and Supported Actions <https://docs.otc.t-systems.com/virtual-private-cloud/api-ref/permissions_policies_and_supported_actions/index.html>`__.

:ref:`Table 1 <overview_permission__en-us_topic_0171267768_table43611845113413>` lists all the system-defined roles and policies supported by VPC.

.. _overview_permission__en-us_topic_0171267768_table43611845113413:

.. table:: **Table 1** System-defined permissions for VPC

   +--------------------+-------------------------------------------------------------------------------------------------------------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | Policy Name        | Description                                                                                                             | Policy Type           | Dependencies                                                                                                                 |
   +====================+=========================================================================================================================+=======================+==============================================================================================================================+
   | VPC FullAccess     | Full permissions for VPC                                                                                                | System-defined policy | To use the VPC flow log function, users must also have the **LTS ReadOnlyAccess** permission.                                |
   +--------------------+-------------------------------------------------------------------------------------------------------------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | VPC ReadOnlyAccess | Read-only permissions on VPC.                                                                                           | System-defined policy | None                                                                                                                         |
   +--------------------+-------------------------------------------------------------------------------------------------------------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+
   | VPC Administrator  | Most permissions on VPC, excluding creating, modifying, deleting, and viewing security groups and security group rules. | System-defined role   | **Tenant Guest** and **Server Administrator** policies, which must be attached in the same project as **VPC Administrator**. |
   |                    |                                                                                                                         |                       |                                                                                                                              |
   |                    | To be granted this permission, users must also have the **Tenant Guest** and **Server Administrator** permission.       |                       |                                                                                                                              |
   +--------------------+-------------------------------------------------------------------------------------------------------------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------+

:ref:`Table 2 <overview_permission__en-us_topic_0171267768_table73311721105916>` lists the common operations supported by each system policy of VPC. Please choose proper system policies according to this table.

.. _overview_permission__en-us_topic_0171267768_table73311721105916:

.. table:: **Table 2** Common operations supported by system-defined permissions

   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Operation                                                   | VPC ReadOnlyAccess | VPC Administrator | VPC FullAccess |
   +=============================================================+====================+===================+================+
   | Assigning an EIP                                            | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Viewing an EIP                                              | Y                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Releasing an EIP                                            | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Binding or unbinding an EIP                                 | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Adding an EIP to or removing an EIP from a shared bandwidth | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Assigning a bandwidth                                       | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Viewing a bandwidth                                         | Y                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Modifying a bandwidth                                       | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+
   | Deleting a bandwidth                                        | x                  | x                 | Y              |
   +-------------------------------------------------------------+--------------------+-------------------+----------------+

Helpful Links
-------------

-  `What Is IAM? <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html#iam-01-0026>`__
-  `Permissions Policies and Supported Actions <https://docs.otc.t-systems.com/virtual-private-cloud/api-ref/permissions_policies_and_supported_actions/index.html>`__
