:original_name: RestoreBackup.html

.. _RestoreBackup:

Restoring a Backup
==================

Function
--------

This API is used to restore backup data.

URI
---

POST /v3/{project_id}/backups/{backup_id}/restore

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   backup_id  Yes       String Backup ID
   project_id Yes       String Project ID
   ========== ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                   |
   +=================+=================+=================+===============================================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token.                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                               |
   |                 |                 |                 | Obtained by calling the corresponding IAM API. If the request is successfully processed, the value of **X-Subject-Token** included in the response header is the token value. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+--------------------------------------------------------------------+------------------------------------+
   | Parameter | Mandatory | Type                                                               | Description                        |
   +===========+===========+====================================================================+====================================+
   | restore   | Yes       | :ref:`BackupRestore <restorebackup__request_backuprestore>` object | Request body of restoring a backup |
   +-----------+-----------+--------------------------------------------------------------------+------------------------------------+

.. _restorebackup__request_backuprestore:

.. table:: **Table 4** BackupRestore

   +-----------------+-----------------+--------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                                                   | Description                                                                                                      |
   +=================+=================+========================================================================================================+==================================================================================================================+
   | mappings        | No              | Array of :ref:`BackupRestoreServerMapping <restorebackup__request_backuprestoreservermapping>` objects | Restored mapping relationship. This parameter is mandatory for VM restoration and optional for disk restoration. |
   +-----------------+-----------------+--------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | power_on        | No              | Boolean                                                                                                | Whether the server is powered on after restoration. By default it is powered on after restoration.               |
   |                 |                 |                                                                                                        |                                                                                                                  |
   |                 |                 |                                                                                                        | Default: **true**                                                                                                |
   +-----------------+-----------------+--------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | server_id       | No              | String                                                                                                 | ID of the target VM to be restored. This parameter is mandatory for VM restoration.                              |
   +-----------------+-----------------+--------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+
   | volume_id       | No              | String                                                                                                 | ID of the target disk to be restored. This parameter is mandatory for disk restoration.                          |
   +-----------------+-----------------+--------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------+

.. _restorebackup__request_backuprestoreservermapping:

.. table:: **Table 5** BackupRestoreServerMapping

   ========= ========= ====== ========================================
   Parameter Mandatory Type   Description
   ========= ========= ====== ========================================
   backup_id Yes       String Disk backup ID
   volume_id Yes       String ID of the disk to which data is restored
   ========= ========= ====== ========================================

Response Parameters
-------------------

None

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/{f841e01fd2b14e7fa41b6ae7aa6b0594}/backups/a5200268-74a5-4806-acc6-95793ab0228b/restore

   {
     "restore" : {
       "mappings" : [ {
         "backup_id" : "5d822633-2bbf-4af8-a16e-5ab1c7705235",
         "volume_id" : "eccbcfdd-f843-4bbb-b2c0-a5ce861f9376"
       } ],
       "power_on" : true,
       "server_id" : "94eba8b2-acc9-4d82-badc-127144cc5526"
     }
   }

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
202         Accepted
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
