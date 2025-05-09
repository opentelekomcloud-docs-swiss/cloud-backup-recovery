:original_name: ShowOpLog.html

.. _ShowOpLog:

Querying a Single Task
======================

Function
--------

This API is used to query a task by task ID.

URI
---

GET /v3/{project_id}/operation-logs/{operation_log_id}

.. table:: **Table 1** Path Parameters

   ================ ========= ====== ===========
   Parameter        Mandatory Type   Description
   ================ ========= ====== ===========
   operation_log_id Yes       String Task ID
   project_id       Yes       String Project ID
   ================ ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                          |
   |                 |                 |                 | The token can be obtained by calling the IAM API used to obtain a user token. The value of **X-Subject-Token** in the response header is the user token. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +---------------+---------------------------------------------------------------+------------------+
   | Parameter     | Type                                                          | Description      |
   +===============+===============================================================+==================+
   | operation_log | :ref:`OperationLog <showoplog__response_operationlog>` object | Task information |
   +---------------+---------------------------------------------------------------+------------------+

.. _showoplog__response_operationlog:

.. table:: **Table 4** OperationLog

   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | Parameter             | Type                                                        | Description                                                                       |
   +=======================+=============================================================+===================================================================================+
   | checkpoint_id         | String                                                      | Backup record ID                                                                  |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | created_at            | String                                                      | Creation time, for example, **2020-02-23T01:00:32Z**                              |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | ended_at              | String                                                      | Task end time, for example, **2020-02-23T01:00:32Z**                              |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | error_info            | :ref:`OpErrorInfo <showoplog__response_operrorinfo>` object | Task error message                                                                |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | extra_info            | :ref:`OpExtraInfo <showoplog__response_opextrainfo>` object | Task extension information                                                        |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | id                    | String                                                      | Task ID                                                                           |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | operation_type        | String                                                      | Task type                                                                         |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | Enumeration values:                                                               |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **backup**                                                                     |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **copy**                                                                       |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **restore**                                                                    |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **delete**                                                                     |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **sync**                                                                       |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **vault_delete**                                                               |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **remove_resource**                                                            |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | policy_id             | String                                                      | Policy ID                                                                         |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | project_id            | String                                                      | Project ID                                                                        |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | provider_id           | String                                                      | Backup provider ID, which specifies whether the backup object is a server or disk |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | started_at            | String                                                      | Task start time, for example, **2020-02-23T01:00:32Z**                            |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | status                | String                                                      | Task status                                                                       |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | Enumeration values:                                                               |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **success**                                                                    |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **skipped**                                                                    |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **failed**                                                                     |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **running**                                                                    |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **timeout**                                                                    |
   |                       |                                                             |                                                                                   |
   |                       |                                                             | -  **waiting**                                                                    |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | updated_at            | String                                                      | Modification time, for example, **2020-02-23T01:00:32Z**                          |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | vault_id              | String                                                      | ID of the vault with which the target resource is associated                      |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+
   | vault_name            | String                                                      | Name of the vault with which the target resource is associated                    |
   +-----------------------+-------------------------------------------------------------+-----------------------------------------------------------------------------------+

.. _showoplog__response_operrorinfo:

.. table:: **Table 5** OpErrorInfo

   ========= ====== ================================================
   Parameter Type   Description
   ========= ====== ================================================
   code      String For details, see :ref:`Error Codes <errorcode>`.
   message   String Error message
   ========= ====== ================================================

.. _showoplog__response_opextrainfo:

.. table:: **Table 6** OpExtraInfo

   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | Parameter        | Type                                                                                        | Description                                            |
   +==================+=============================================================================================+========================================================+
   | backup           | :ref:`OpExtendInfoBckup <showoplog__response_opextendinfobckup>` object                     | Extended parameters of backup                          |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | common           | :ref:`OpExtendInfoCommon <showoplog__response_opextendinfocommon>` object                   | Common parameters                                      |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | delete           | :ref:`OpExtendInfoDelete <showoplog__response_opextendinfodelete>` object                   | Extended parameters of deletion                        |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | sync             | :ref:`OpExtendInfoSync <showoplog__response_opextendinfosync>` object                       | Extended parameters of synchronization                 |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | remove_resources | :ref:`OpExtendInfoRemoveResources <showoplog__response_opextendinforemoveresources>` object | Extended parameters of removing resources from a vault |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | resource         | :ref:`Resource <showoplog__response_resource>` object                                       | Resource information                                   |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | restore          | :ref:`OpExtendInfoRestore <showoplog__response_opextendinforestore>` object                 | Extended parameters of restoration                     |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+
   | vault_delete     | :ref:`OpExtendInfoVaultDelete <showoplog__response_opextendinfovaultdelete>` object         | Extended parameters of deleting a vault                |
   +------------------+---------------------------------------------------------------------------------------------+--------------------------------------------------------+

.. _showoplog__response_opextendinfobckup:

.. table:: **Table 7** OpExtendInfoBckup

   =========== ====== ===========
   Parameter   Type   Description
   =========== ====== ===========
   backup_id   String Backup ID
   backup_name String Backup name
   =========== ====== ===========

.. _showoplog__response_opextendinfocommon:

.. table:: **Table 8** OpExtendInfoCommon

   +-----------------------+-----------------------+---------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                         |
   +=======================+=======================+=====================================================================+
   | progress              | Integer               | Progress of the query task. The value ranges from **0** to **100**. |
   |                       |                       |                                                                     |
   |                       |                       | Minimum: **0**                                                      |
   |                       |                       |                                                                     |
   |                       |                       | Maximum: **100**                                                    |
   +-----------------------+-----------------------+---------------------------------------------------------------------+
   | request_id            | String                | Request ID                                                          |
   +-----------------------+-----------------------+---------------------------------------------------------------------+
   | task_id               | String                | Backup task ID                                                      |
   +-----------------------+-----------------------+---------------------------------------------------------------------+

.. _showoplog__response_opextendinfodelete:

.. table:: **Table 9** OpExtendInfoDelete

   =========== ====== ===========
   Parameter   Type   Description
   =========== ====== ===========
   backup_id   String Backup ID
   backup_name String Backup name
   =========== ====== ===========

.. _showoplog__response_opextendinfosync:

.. table:: **Table 10** OpExtendInfoSync

   +---------------------+---------+--------------------------------------------------+
   | Parameter           | Type    | Description                                      |
   +=====================+=========+==================================================+
   | sync_backup_num     | Integer | Number of synchronized backups                   |
   +---------------------+---------+--------------------------------------------------+
   | delete_backup_num   | Integer | Number of deleted backups                        |
   +---------------------+---------+--------------------------------------------------+
   | err_sync_backup_num | Integer | Number of backups that failed to be synchronized |
   +---------------------+---------+--------------------------------------------------+

.. _showoplog__response_opextendinforemoveresources:

.. table:: **Table 11** OpExtendInfoRemoveResources

   +-------------+-----------------------------------------------------------------+---------------------------------------------+
   | Parameter   | Type                                                            | Description                                 |
   +=============+=================================================================+=============================================+
   | fail_count  | Integer                                                         | Number of resources that fail to be deleted |
   +-------------+-----------------------------------------------------------------+---------------------------------------------+
   | total_count | Integer                                                         | Number of deleted backups                   |
   +-------------+-----------------------------------------------------------------+---------------------------------------------+
   | resources   | Array of :ref:`Resource <showoplog__response_resource>` objects | Resource information                        |
   +-------------+-----------------------------------------------------------------+---------------------------------------------+

.. _showoplog__response_resource:

.. table:: **Table 12** Resource

   +-----------------------+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | Parameter             | Type                                                                    | Description                                                                                       |
   +=======================+=========================================================================+===================================================================================================+
   | extra_info            | :ref:`ResourceExtraInfo <showoplog__response_resourceextrainfo>` object | Extra information of the resource                                                                 |
   +-----------------------+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | id                    | String                                                                  | ID of the resource to be backed up                                                                |
   +-----------------------+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | name                  | String                                                                  | Name of the resource to be backed up. The value consists of 0 to 255 characters.                  |
   |                       |                                                                         |                                                                                                   |
   |                       |                                                                         | Minimum: **0**                                                                                    |
   |                       |                                                                         |                                                                                                   |
   |                       |                                                                         | Maximum: **255**                                                                                  |
   +-----------------------+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+
   | type                  | String                                                                  | Type of the resource to be backed up, which can be **OS::Nova::Server** or **OS::Cinder::Volume** |
   +-----------------------+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------+

.. _showoplog__response_resourceextrainfo:

.. table:: **Table 13** ResourceExtraInfo

   +-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Description                                                                                                                                                                                                                                                                                 |
   +=================+==================+=============================================================================================================================================================================================================================================================================================+
   | exclude_volumes | Array of strings | IDs of the disks that will not be backed up. This parameter is used when servers are added to a vault, which include all server disks. But some disks do not need to be backed up. Or in case that a server was previously added and some disks on this server do not need to be backed up. |
   +-----------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _showoplog__response_opextendinforestore:

.. table:: **Table 14** OpExtendInfoRestore

   ==================== ====== ===================================
   Parameter            Type   Description
   ==================== ====== ===================================
   backup_id            String Backup ID
   backup_name          String Backup name
   target_resource_id   String ID of the resource to be restored
   target_resource_name String Name of the resource to be restored
   ==================== ====== ===================================

.. _showoplog__response_opextendinfovaultdelete:

.. table:: **Table 15** OpExtendInfoVaultDelete

   +-------------+---------+----------------------------------------------------------+
   | Parameter   | Type    | Description                                              |
   +=============+=========+==========================================================+
   | fail_count  | Integer | Number of resources that fail to be deleted in this task |
   +-------------+---------+----------------------------------------------------------+
   | total_count | Integer | Number of backups deleted in this task                   |
   +-------------+---------+----------------------------------------------------------+

**Status code: 404**

.. table:: **Table 16** Response body parameters

   ========== ====== ================================================
   Parameter  Type   Description
   ========== ====== ================================================
   error_code String For details, see :ref:`Error Codes <errorcode>`.
   error_msg  String Error message
   ========== ====== ================================================

Example Requests
----------------

.. code-block:: text

   GET https://{endpoint}/v3/{project_id}/operation-logs/{operation_log_id}

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "operation_log" : {
       "status" : "success",
       "provider_id" : "0daac4c5-6707-4851-97ba-169e36266b66",
       "checkpoint_id" : "b432511f-d889-428f-8b0e-5f47c524c6b6",
       "updated_at" : "2019-05-23T14:35:23.584+00:00",
       "error_info" : {
         "message" : "",
         "code" : ""
       },
       "started_at" : "2019-05-23T14:31:36.007+00:00",
       "id" : "4827f2da-b008-4507-ab7d-42d0df5ed912",
       "extra_info" : {
         "resource" : {
           "type" : "OS::Nova::Server",
           "id" : "1dab32fa-ebf2-415a-ab0b-eabe6353bc86",
           "name" : "ECS-0001"
         },
         "backup" : {
           "backup_name" : "manualbk_1234",
           "backup_id" : "0e5d0ef6-7f0a-4890-b98c-cb12490e31c1"
         },
         "common" : {
           "progress" : 100,
           "request_id" : "req-cdb98cc4-e87b-4f40-9b4a-57ec036620bc"
         }
       },
       "ended_at" : "2019-05-23T14:35:23.511+00:00",
       "created_at" : "2019-05-23T14:31:36.039+00:00",
       "operation_type" : "backup",
       "project_id" : "04f1829c788037ac2fb8c01eb2b04b95"
     }
   }

**Status code: 404**

The task ID does not exist.

.. code-block::

   {
     "error_code" : "BackupService.6500",
     "error_msg" : "Operation log does not exist."
   }

Status Codes
------------

=========== ===========================
Status Code Description
=========== ===========================
200         OK
404         The task ID does not exist.
=========== ===========================

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
