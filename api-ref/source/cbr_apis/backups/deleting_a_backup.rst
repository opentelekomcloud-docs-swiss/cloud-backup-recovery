:original_name: DeleteBackup.html

.. _DeleteBackup:

Deleting a Backup
=================

Function
--------

This API is used to delete a single backup.

URI
---

DELETE /v3/{project_id}/backups/{backup_id}

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ==============================
   Parameter  Mandatory Type   Description
   ========== ========= ====== ==============================
   backup_id  Yes       String ID of the backup to be deleted
   project_id Yes       String Project ID
   ========== ========= ====== ==============================

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

None

Example Requests
----------------

This API is used to delete a single backup.

.. code-block:: text

   DELETE https://{endpoint}/v3/{project_id}/backups/{backup_id}

Example Responses
-----------------

None

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
204         No Content
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
