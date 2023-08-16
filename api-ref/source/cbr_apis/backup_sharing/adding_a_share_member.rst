:original_name: AddMember.html

.. _AddMember:

Adding a Share Member
=====================

Function
--------

This API is used to add a member with whom the backup can be shared. Only cloud server backups can be shared among tenants in the same region.

URI
---

POST /v3/{project_id}/backups/{backup_id}/members

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

   +-----------+-----------+------------------+-----------------------------------------------------+
   | Parameter | Mandatory | Type             | Description                                         |
   +===========+===========+==================+=====================================================+
   | members   | Yes       | Array of strings | Project IDs of the backup share members to be added |
   +-----------+-----------+------------------+-----------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-----------+-------------------------------------------------------------+------------------------------------------------------+
   | Parameter | Type                                                        | Description                                          |
   +===========+=============================================================+======================================================+
   | members   | Array of :ref:`Member <addmember__response_member>` objects | Response parameters of adding a backup share member  |
   +-----------+-------------------------------------------------------------+------------------------------------------------------+
   | count     | Integer                                                     | Number of share members that the backup is shared to |
   +-----------+-------------------------------------------------------------+------------------------------------------------------+

.. _addmember__response_member:

.. table:: **Table 5** Member

   +-----------------------+-----------------------+------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                      |
   +=======================+=======================+==================================================================+
   | status                | String                | Backup sharing status                                            |
   |                       |                       |                                                                  |
   |                       |                       | Enumeration values:                                              |
   |                       |                       |                                                                  |
   |                       |                       | -  **pending**                                                   |
   |                       |                       |                                                                  |
   |                       |                       | -  **accepted**                                                  |
   |                       |                       |                                                                  |
   |                       |                       | -  **rejected**                                                  |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | created_at            | String                | Backup sharing time, for example, **2020-02-05T10:38:34.209782** |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | updated_at            | String                | Update time, for example, **2020-02-05T10:38:34.209782**         |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | backup_id             | String                | Backup ID                                                        |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | image_id              | String                | ID of the image created by using the accepted shared backup      |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | dest_project_id       | String                | ID of the project with which the backup is shared                |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | vault_id              | String                | ID of the vault where the shared backup is stored                |
   +-----------------------+-----------------------+------------------------------------------------------------------+
   | id                    | String                | ID of the shared record                                          |
   +-----------------------+-----------------------+------------------------------------------------------------------+

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/0605767b5780d5762fc5c0118072a564/backups/0b07081e-3ec7-4e77-8571-54e2947da422/members

   {
     "members" : [ "075e6035d300d48c2fd0c00b78b71ebf" ]
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "members" : [ {
       "status" : "pending",
       "image_id" : null,
       "backup_id" : "0b07081e-3ec7-4e77-8571-54e2947da422",
       "vault_id" : null,
       "dest_project_id" : "075e6035d300d48c2fd0c00b78b71ebf",
       "created_at" : "2020-02-05T10:38:34.209782",
       "updated_at" : null,
       "id" : "3c5a3015-c3a0-4dc6-a1e2-917b90f62319"
     } ]
   }

Status Codes
------------

=========== ===========
Status Code Description
=========== ===========
200         OK
=========== ===========

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
