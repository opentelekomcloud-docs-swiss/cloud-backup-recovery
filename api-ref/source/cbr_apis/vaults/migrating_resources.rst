:original_name: MigrateVaultResource.html

.. _MigrateVaultResource:

Migrating Resources
===================

Function
--------

This API is used to associate resources with another vault and migrate the resource backups to that destination vault.

URI
---

POST /v3/{project_id}/vaults/{vault_id}/migrateresources

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   project_id Yes       String Project ID
   vault_id   Yes       String Vault ID
   ========== ========= ====== ===========

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                                                                                                                                         |
   +==============+===========+========+=====================================================================================================================================================================+
   | X-Auth-Token | No        | String | User token The token can be obtained by calling the IAM API used to obtain a user token. The value of **X-Subject-Token** in the response header is the user token. |
   +--------------+-----------+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +----------------------+-----------+------------------+-----------------------------------+
   | Parameter            | Mandatory | Type             | Description                       |
   +======================+===========+==================+===================================+
   | destination_vault_id | Yes       | String           | Destination vault                 |
   +----------------------+-----------+------------------+-----------------------------------+
   | resource_ids         | Yes       | Array of strings | ID of the resource to be migrated |
   +----------------------+-----------+------------------+-----------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   ================== ================ ==========================
   Parameter          Type             Description
   ================== ================ ==========================
   migrated_resources Array of strings List of migrated resources
   ================== ================ ==========================

Example Requests
----------------

Migrating resources as well as their backups to a different vault

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/vaults/79bd9daa-884f-4f84-b8fe-235d58cd927d/migrateresources

   {
     "resource_ids" : [ "abcdde3f-e0e3-403a-b690-fc259dd70008" ],
     "destination_vault_id" : "fe578a6c-d1a8-4790-bd52-5954af4d446c"
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "migrated_resources" : [ "fe578a6c-d1a8-4790-bd52-5954af4d446c" ]
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
