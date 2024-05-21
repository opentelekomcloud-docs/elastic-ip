:original_name: permission_0004.html

.. _permission_0004:

EIP Custom Policies
===================

Custom policies can be created as a supplement to the system policies of EIP. For the actions supported for custom policies, see `Permissions Policies and Supported Actions <https://docs.otc.t-systems.com/virtual-private-cloud/api-ref/permissions_policies_and_supported_actions/index.html>`__\ *.*

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.

-  JSON: Edit JSON policies from scratch or based on an existing policy.

   For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/identity-access-management/umn/user_guide/permissions/creating_a_custom_policy.html>`__. The following section contains examples of common EIP custom policies.

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
                           vpc:publicIps:create,
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
