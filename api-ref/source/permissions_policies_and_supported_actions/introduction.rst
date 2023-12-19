:original_name: cbr_04_0017.html

.. _cbr_04_0017:

Introduction
============

You can use Identity and Access Management (IAM) for fine-grained permissions management of your CBR resources. If your cloud account does not need individual IAM users, you can skip this section.

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

You can grant users permissions using roles and policies. Roles are provided by IAM to define service-based permissions that match user's job responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   If you want to allow or deny the access to an API, use policy-based authorization.

Each account has all the permissions required to call all APIs, but IAM users must be granted the required permissions. The required permissions are determined by the actions supported by the API. Only users with the policies allowing for those actions can call the API successfully. For example, if an IAM user wants to query ECSs using an API, the user must have been granted permissions that allow the **ecs:servers:list** action.

Supported Actions
-----------------

CBR provides system-defined policies that can be directly used in IAM. You can also create custom policies to supplement system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: statements in a policy that allow or deny certain operations
-  APIs: REST APIs that can be called by a user who has been granted specific permissions
-  Actions: specific operations that are allowed or denied
-  Dependencies: actions which a specific action depends on. When allowing an action for a user, you also need to allow any existing action dependencies for that user.
-  IAM projects: the authorization scope of a custom policy

.. note::

   The check mark (Y) and cross symbol (x) indicate that an action takes effect or does not take effect for the corresponding type of projects.

CBR supports the following actions in custom policies:

-  [Example] Vault actions (:ref:`Vault <cbr_04_0018__section16923143918296>`), including all of the actions supported by CBR vault APIs, such as the APIs for creating, modifying, and deleting a vault, querying the vault list, as well as adding and removing resources.
-  [Example] Backup sharing actions (:ref:`Backup Sharing <cbr_04_0018__section86041763166>`), including actions supported by CBR backup sharing APIs, such as APIs for adding share members, obtaining the share member list, and updating the share member status.
