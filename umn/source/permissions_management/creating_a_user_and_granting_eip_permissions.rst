:original_name: permission_0003.html

.. _permission_0003:

Creating a User and Granting EIP Permissions
============================================

Currently, the EIP service permissions are included in the VPC permissions. For details, see :ref:`Permissions Management <overview_permission>`.

This section describes how to use IAM to implement fine-grained permissions control for your VPC resources. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing VPC resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust a cloud account or cloud service to perform efficient O&M on your VPC resources.

If your cloud account meets your permissions requirements, you can skip this section.

:ref:`Figure 1 <permission_0003__en-us_topic_0171307068_fig1447123814172>` shows the process flow for granting permissions.

Prerequisites
-------------

Before granting permissions to user groups, learn about :ref:`EIP Permissions <overview_permission>` for EIP.

To grant permissions for other services, learn about all `permissions <https://docs.otc.t-systems.com/permissions/index.html>`__ supported by IAM.

Process Flow
------------

.. _permission_0003__en-us_topic_0171307068_fig1447123814172:

.. figure:: /_static/images/en-us_image_0204809685.png
   :alt: **Figure 1** Process for granting EIP permissions

   **Figure 1** Process for granting EIP permissions

#. On the IAM console, `create a user group and grant it permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__ (**EIP ReadOnlyAccess** as an example).

#. `Create an IAM user and add it to the created user group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__.

#. `Log in as the IAM user <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   In the authorized region, perform the following operations:

   -  Choose **Service List** > **Elastic IP**. Then click **Buy EIP** on the EIP console. If a message appears indicating that you have insufficient permissions to perform the operation, the **EIPReadOnlyAccess** policy is in effect.
   -  Choose another service from **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **EIPReadOnlyAccess** policy is in effect.

Example Custom Policies
-----------------------

-  Example 1: Grant permissions to assign and view EIPs

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "
                           vpc:publicIps:create
                           vpc:publicIps:list
                       "
                  ]
              }
          ]
      }

-  Example 2: Grant permission to deny EIP deletion.

   A policy with only "Deny" permissions must be used together with other policies. If the permissions granted to an IAM user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   Assume that you want to grant the permissions of the **VPC FullAccess** policy to a user but want to prevent them from releasing EIPs. You can create a custom policy for denying EIP release, and attach both policies to the user. As an explicit deny in any policy overrides any allows, the user can perform all operations on EIPs except releasing them. Example policy denying EIP release:

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                "Effect": "Deny",
                        "Action": [
                              "vpc:publicIps:delete"
                        ]
                  }
            ]
      }

-  Example 3: Create a custom policy containing multiple actions.

   A custom policy can contain the actions of one or multiple services that are of the same type (global or project-level). Example policy containing multiple actions:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "ecs:servers:delete",
                      "vpc:publicIps:update",
                      "vpc:publicIps:create"
                  ]
              },
              {
                  "Effect": "Deny",
                  "Action": [
                      "vpc:publicIps:delete"
                  ]
              }
          ]
      }
