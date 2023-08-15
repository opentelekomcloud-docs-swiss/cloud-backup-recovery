:original_name: ShowMemberDetail.html

.. _ShowMemberDetail:

Querying Share Member Details
=============================

Function
--------

This API is used to obtain the details of a backup share member.

URI
---

GET /v3/{project_id}/backups/{backup_id}/members/{member_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+----------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                      |
   +============+===========+========+==================================================================================+
   | backup_id  | Yes       | String | Backup ID                                                                        |
   +------------+-----------+--------+----------------------------------------------------------------------------------+
   | member_id  | Yes       | String | Member ID, which is the project ID of the tenant who receives the shared backup. |
   +------------+-----------+--------+----------------------------------------------------------------------------------+
   | project_id | Yes       | String | Project ID                                                                       |
   +------------+-----------+--------+----------------------------------------------------------------------------------+

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

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   +-----------+----------------------------------------------------------+----------------------------------------------------------------------+
   | Parameter | Type                                                     | Description                                                          |
   +===========+==========================================================+======================================================================+
   | member    | :ref:`Member <showmemberdetail__response_member>` object | Response parameters of querying the details of a backup share member |
   +-----------+----------------------------------------------------------+----------------------------------------------------------------------+

.. _showmemberdetail__response_member:

.. table:: **Table 4** Member

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

   GET  https://{endpoint}/v3/{project_id}/backups/{backup_id}/members/{member_id}

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "member" : {
       "status" : "accepted",
       "image_id" : null,
       "backup_id" : "17c9acd8-3af3-4401-bab9-ff1cfac15561",
       "vault_id" : "4b27c05b-8ad7-48c6-a886-526666c035f0",
       "dest_project_id" : "0761021b8900d2622f38c0115db0b331",
       "created_at" : "2020-02-24T09:36:00.479033",
       "updated_at" : null,
       "id" : "824a90b3-c562-448b-ab04-60ea4a97cf60"
     }
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
