:original_name: cbr_04_0028.html

.. _cbr_04_0028:

Example 3: Querying Backups
===========================

Scenarios
---------

This section describes how to use APIs to query all backups of a tenant by page.

The operations described in this section include information query by page and data filtering and sorting. For details about the parameters, see "Querying All Backups".

Involved APIs
-------------

Querying backups involves the following APIs:

-  :ref:`Querying backups based on a given limit and offset <cbr_04_0028__li1131374010534>`
-  :ref:`Querying backups based on a given resource type <cbr_04_0028__li7464445536>`

Procedure
---------

#. .. _cbr_04_0028__li1131374010534:

   Query backups based on a given **limit** and **offset**.

   -  API

      URI format: GET /v3/{project_id}/backups

      For details, see "Querying All Backups".

   -  Sample request

      GET:https://*{endpoint*}/v3/0605767b5780d5762fc5c0118072a564/ backups?limit=100&offset=0

      Obtain the value of **{endpoint}** from the administrator.

   -  Sample response

      .. code-block::

         {
            "backups": [
                  ......
                 {
                     "children": [],
                     "checkpoint_id": "e6aec7a9-7b03-4c1d-8a07-5983b53c53f3",
                     "created_at": "2020-08-18T06:00:45.375070",
                     "description": null,
                     "expired_at": null,
                     "extend_info": {
                         },
                         "auto_trigger": true,
                         "bootable": null,
                         "os_images_data": null,
                         "progress": null,
                         "snapshot_id": null,
                         "support_lld": false,
                         "supported_restore_mode": "backup",
                         "system_disk": false,
                         "contain_system_disk": true,
                         "architecture": "x86_64"
                     },
                     "id": "62617971-839d-4d23-8dfd-4ca65c039bdf",
                     "image_type": "backup",
                     "name": "autobk_cf91_0003",
                     "parent_id": null,
                     "project_id": "0605767b5780d5762fc5c0118072a564",
                     "protected_at": "2020-08-18T06:01:10.432117",
                     "provider_id": "0daac4c5-6707-4851-97ba-169e36266b66",
                     "resource_az": "br-iaas-odin1a",
                     "resource_id": "d6bf7592-ca52-43a2-9979-e418d64b29bb",
                     "resource_name": "xzl_ecs-0003-0001",
                     "resource_size": 40,
                     "resource_type": "OS::Nova::Server",
                     "status": "available",
                     "updated_at": "2020-08-18T06:06:44.928325",
                     "vault_id": "1572bd27-e221-4f28-94ca-9777d232fcd7",
                     "replication_records": []
                 }
             ],
             "count": 1663
         }

#. .. _cbr_04_0028__li7464445536:

   Query backups based on a given resource type.

   -  API

      URI format: GET /v3/{project_id}/backups

      The used API is the same as that provided in :ref:`1 <cbr_04_0028__li1131374010534>`.

   -  Sample request

      GET: https://{endpoint}/v3/0605767b5780d5762fc5c0118072a564/backups?resource_type=OS::Nova::Server&limit=5&offset=0

      Obtain the value of **{endpoint}** from the administrator.

   -  Sample response

      .. code-block::

         {
             "backups": [
                  ......
                 {
                     "children": [],
                     "checkpoint_id": "e328d05e-4b28-4898-b8c1-2bfe6621ec03",
                     "created_at": "2020-08-18T07:00:46.932061",
                     "description": null,
                     "expired_at": null,
                     "extend_info": {
                         "app_consistency": {
                             "app_consistency": "0",
                             "app_consistency_status": "0",
                             "app_consistency_error_code": "0",
                             "app_consistency_error_message": ""
                         },
                         "auto_trigger": true,
                         "bootable": null,
                         "os_images_data": null,
                         "progress": null,
                         "snapshot_id": null,
                         "support_lld": false,
                         "supported_restore_mode": "backup",
                         "system_disk": false,
                         "contain_system_disk": true,
                         "architecture": "x86_64"
                     },
                     "id": "c892ed58-3a18-47c2-9e31-a1d543dc490a",
                     "image_type": "backup",
                     "name": "autobk_7234_0003",
                     "parent_id": null,
                     "project_id": "0605767b5780d5762fc5c0118072a564",
                     "protected_at": "2020-08-18T07:01:12.675112",
                     "provider_id": "0daac4c5-6707-4851-97ba-169e36266b66",
                     "resource_az": "br-iaas-odin1a",
                     "resource_id": "d6bf7592-ca52-43a2-9979-e418d64b29bb",
                     "resource_name": "xzl_ecs-0003-0001",
                     "resource_size": 40,
                     "resource_type": "OS::Nova::Server",
                     "status": "available",
                     "updated_at": "2020-08-18T07:06:47.518054",
                     "vault_id": "1572bd27-e221-4f28-94ca-9777d232fcd7",
                     "replication_records": []
                 }
             ],
             "count": 150
         }
