:original_name: cbr_04_0027.html

.. _cbr_04_0027:

Example 2: Implementing Automatic Backup for a Vault
====================================================

Scenarios
---------

This section describes how to use APIs to set a backup policy and apply the policy to a vault for automatic backup.

Involved APIs
-------------

-  Creating a Policy: Define when a backup task runs and how long the backups are retained.
-  Applying a Policy to a Vault: Apply a policy to a vault.

Procedure
---------

#. Create a backup policy.

   -  API

      URI format: POST /v3/{project_id}/policies

      For details, see "Creating a Policy".

   -  Sample request

      POST: https://*{endpoint*}/v3/0605767b5780d5762fc5c0118072a564/policies

      Obtain the value of **{endpoint}** from the administrator.

      Body:

      .. code-block::

         {
             "policy": {
                 "name": "dh_test_policy",
                 "trigger": {
                     "properties": {
                         "pattern": ["FREQ=WEEKLY;BYDAY=SU,MO,TU,WE,TH,FR,SA;BYHOUR=23;BYMINUTE=00"]
         }
                 },
                 "operation_definition": {
                     "retention_duration_days": 30
         }
             }
         }

   -  Sample response

      .. code-block::

         {
             "policy": {
                 "id": "30d7cf2d-14fc-415b-b7da-858b37f47250",
                 "name": "dh_test_policy",
                 "operation_type": "backup",
                 "operation_definition": {
                     "retention_duration_days": 30
                 },
                 "enabled": true,
                 "trigger": {
                     "id": "7954175b-ef2c-432c-b936-f6c83df7a593",
                     "name": "default",
                     "type": "time",
                     "properties": {
                         "pattern": [
                             "FREQ=WEEKLY;BYDAY=SU,MO,TU,WE,TH,FR,SA;BYHOUR=23;BYMINUTE=00"
                         ],
                         "start_time": "2020-08-17 08:39:44"
                     }
                 },
                 "associated_vaults": null
             }
         }

#. Apply the policy to a vault.

   -  API

      POST /v3/{project_id}/vaults/{vault_id}/associatepolicy

      For details, see "Applying a Policy to a Vault".

   -  Sample request

      POST: https://{endpoint}/v3/0605767b5780d5762fc5c0118072a564 /vaults/ea7b8717-2543-478a-a92d-3ca7ee448f67/associatepolicy

      Obtain the value of **{endpoint}** from the administrator.

      Body:

      .. code-block::

         {
             "policy_id": "30d7cf2d-14fc-415b-b7da-858b37f47250"
         }

   -  Sample response

      .. code-block::

         {
             "associate_policy": {
                 "vault_id": "ea7b8717-2543-478a-a92d-3ca7ee448f67",
                 "policy_id": "30d7cf2d-14fc-415b-b7da-858b37f47250"
             }
         }
