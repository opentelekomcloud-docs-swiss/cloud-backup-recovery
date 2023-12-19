:original_name: cbr_04_0026.html

.. _cbr_04_0026:

Example 1: Creating an ECS Backup
=================================

Scenarios
---------

You can back up resources including cloud servers and disks. This section uses an ECS as an example to describe how to create a cloud server backup by calling APIs. For details on how to call APIs, see :ref:`Calling APIs <cbr_04_0008>`.

Involved APIs
-------------

To create a cloud server backup, you need to create a vault for storing backups, associate the target server with the vault, and then back up the server. The following APIs are required:

-  Creating a Vault: Create a container for storing backups.
-  Associating Resources: Determine the cloud server or disk to be backed up.
-  Creating a Restore Point: Create a backup.
-  Querying a Restore Point: Confirm that a backup has been created.

Procedure
---------

#. Create a vault.

   a. Create a vault with simple configurations.

      -  API

         URI format: POST /v3/{project_id}/vaults

         For details, see "Creating a Vault".

      -  Sample request

         POST: https://*{endpoint*}/v3/{project_id}/vaults

         Obtain the value of **{endpoint}** from the administrator.

         Body:

         .. code-block::

            {
                "vault": {
                       "billing": {
                              "cloud_type": "public",
                              "consistent_level": "crash_consistent",
                              "object_type": "server",
                              "protect_type": "backup",
                              "size": 200
                       },
                       "name": "my_vault",
                       "resources": []
                }
            }

      -  Sample response

         .. code-block::

            {
                "vault": {
                    "id": "ea7b8717-2543-478a-a92d-3ca7ee448f67",
                    "name": "my_vault",
                    "description": null,
                    "resources": [],
                    "provider_id": "0daac4c5-6707-4851-97ba-169e36266b66",
                    "created_at": "2020-08-17T03:51:24.678916",
                    "project_id": "0605767b5780d5762fc5c0118072a564",
                    "enterprise_project_id": "0",
                    "auto_bind": false,
                    "bind_rules": {},
                    "user_id": "aa2999fa5ae640f28926f8fd79188934",
                    "billing": {
                        "allocated": 0,
                        "cloud_type": "public",
                        "consistent_level": "crash_consistent",
                        "frozen_scene": null,
                        "charging_mode": "post_paid",
                        "order_id": null,
                        "product_id": null,
                        "protect_type": "backup",
                        "object_type": "server",
                        "spec_code": "vault.backup.server.normal",
                        "used": 0,
                        "storage_unit": null,
                        "status": "available",
                        "size": 200
                    },
                    "tags": []
                }
            }

#. Associate a server or disk with the vault.

   a. Associate resources.

      -  API

         URI format: POST /v3/{project_id}/vaults/{vault_id}/addresources

         For details, see "Associating Resources".

      -  Sample request

         POST: https://{endpoint}/v3/0605767b5780d5762fc5c0118072a56\ *4* /vaults/ea7b8717-2543-478a-a92d-3ca7ee448f67/addresources

         Obtain the value of **{endpoint}** from the administrator.

         Body:

         .. code-block::

            {
                "resources": [{
                       "id": "e8cc6bfd-d324-4b88-9109-9fb0ba70676f",
                       "type": "OS::Nova::Server",
                       "name": "server-4690-0002"
                }]
            }

      -  Sample response

         .. code-block::

            {
                "add_resource_ids": [
                    "e8cc6bfd-d324-4b88-9109-9fb0ba70676f"
                ]
            }

   b. In the request body, select the ID of an ECS that is in the **Running** state and has not been associated with a vault.

#. Create a restore point.

   a. Create a restore point.

      -  API

         URI format: POST /v3/{project_id}/checkpoints

         For details, see "Creating a Restore Point".

      -  Sample request

         POST: https://*{endpoint*}/v3/0605767b5780d5762fc5c0118072a564/checkpoints

         Obtain the value of **{endpoint}** from the administrator.

         Body:

         .. code-block::

            {
                "checkpoint": {
                    "parameters": {
                        "auto_trigger": false,
                        "description": "backupauto",
                        "incremental": true,
                        "name": "backup_auto",
                        "resources": ["e8cc6bfd-d324-4b88-9109-9fb0ba70676f"]
                      },
                    "vault_id": "ea7b8717-2543-478a-a92d-3ca7ee448f67"
                }
            }

      -  Sample response

         .. code-block::

            {
                "checkpoint": {
                    "id": "d9ce6924-d753-4132-bd16-a9f8838ea7d2",
                    "project_id": "0605767b5780d5762fc5c0118072a564",
                    "status": "protecting",
                    "vault": {
                        "id": "ea7b8717-2543-478a-a92d-3ca7ee448f67",
                        "name": "my_vault",
                        "resources": [
                            {
                                "id": "e8cc6bfd-d324-4b88-9109-9fb0ba70676f",
                                "type": "OS::Nova::Server",
                                "name": "ecs-9f93-0002",
                                "extra_info": "{}",
                                "resource_size": "40",
                                "backup_size": "0",
                                "backup_count": "0",
                                "protect_status": "available"
                            }
                        ],
                        "skipped_resources": []
                    },
                    "created_at": "2020-08-17T06:49:06.307378",
                    "extra_info": {
                        "name": "backup_auto",
                        "description": "backupauto",
                        "retention_duration": -1
                    }
                }
            }

   b. Record the ID of the restore point in the response message body.

#. Verify that the server is backed up successfully.

   -  API

      URI format: GET /v3/{project_id}/checkpoints/{checkpoint_id}

      For details, see "Querying a Restore Point".

      Obtain the value of **{endpoint}** from the administrator.

   -  Sample request

      GET: https://{endpoint}/v3/0605767b5780d5762fc5c0118072a564/checkpoints/d9ce6924-d753-4132-bd16-a9f8838ea7d2

   -  Sample response

      .. code-block::

         {
             "checkpoint": {
                 "id": "d9ce6924-d753-4132-bd16-a9f8838ea7d2",
                 "project_id": "0605767b5780d5762fc5c0118072a564",
                 "status": "available",
                 "vault": null,
                 "created_at": "2020-08-17T06:49:06.260790",
                 "extra_info": null
             }
         }
