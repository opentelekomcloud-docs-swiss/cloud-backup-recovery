:original_name: RemoveVaultResource.html

.. _RemoveVaultResource:

Dissociating Resources
======================

Function
--------

This API is used to dissociate resources from a vault.

URI
---

POST /v3/{project_id}/vaults/{vault_id}/removeresources

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

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                   |
   +=================+=================+=================+===============================================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token.                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                               |
   |                 |                 |                 | Obtained by calling the corresponding IAM API. If the request is successfully processed, the value of **X-Subject-Token** included in the response header is the token value. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   +--------------+-----------+------------------+------------------------------------+
   | Parameter    | Mandatory | Type             | Description                        |
   +==============+===========+==================+====================================+
   | resource_ids | Yes       | Array of strings | List of resource IDs to be removed |
   +--------------+-----------+------------------+------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   =================== ================ ====================
   Parameter           Type             Description
   =================== ================ ====================
   remove_resource_ids Array of strings Removed resource IDs
   =================== ================ ====================

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/vaults/79bd9daa-884f-4f84-b8fe-235d58cd927d/associatepolicy

   {
     "resource_ids" : [ "97595625-198e-4e4d-879b-9d53f68ba551" ]
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "remove_resource_ids" : [ "97595625-198e-4e4d-879b-9d53f68ba551" ]
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
