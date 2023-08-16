:original_name: cbr_04_0017.html

.. _cbr_04_0017:

Introduction
============

This section describes fine-grained permissions management for your CBR. If your cloud account does not need individual IAM users, skip this section.

By default, new IAM users do not have permissions assigned. You need to add the users to one or more groups, and attach permissions policies or roles to these groups. Users inherit permissions from the groups to which they are added and can perform specified operations on cloud services based on the permissions.

You can grant users permissions by using roles and policies. Roles are a type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   Policy-based authorization is useful if you want to allow or deny the access to an API.

An account has all the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user wants to query ECSs using an API, the user must have been granted permissions that allow the **ecs:servers:list** action.

Supported Actions
-----------------

CBR provides system-defined policies that can be directly used in IAM. You can also create custom policies and use them to supplement system-defined policies, implementing more refined access control. Actions supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Statements in a policy that allow or deny certain operations.
-  APIs: REST APIs that can be called by a user who has been granted specific permissions.
-  Actions: Specific operations that are allowed or denied.
-  Related actions: Actions on which a specific action depends to take effect. When assigning permissions for the action to a user, you also need to assign permissions for the related actions.
-  IAM projects: Type of projects for which an action will take effect.

   .. note::

      The check mark (Y) and cross symbol (x) indicate that an action takes effect or does not take effect for the corresponding type of projects.

CBR supports the following actions that can be defined in custom policies:

-  [Example] :ref:`Vault <cbr_04_0018__section16923143918296>` includes actions supported by CBR vault APIs, such as APIs for creating, modifying, and deleting a vault, querying the vault list, as well as adding and removing resources.
-  [Example] :ref:`Backup Sharing <cbr_04_0018__section86041763166>` includes actions supported by CBR backup sharing APIs, such as APIs for adding share members, obtaining the share member list, and updating the share member status.
