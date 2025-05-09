:original_name: AssociateVaultPolicy.html

.. _AssociateVaultPolicy:

Applying a Policy to a Vault
============================

Function
--------

This API is used to apply a policy to a vault.

URI
---

POST /v3/{project_id}/vaults/{vault_id}/associatepolicy

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

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================================+
   | X-Auth-Token    | Yes             | String          | User token                                                                                                                                               |
   |                 |                 |                 |                                                                                                                                                          |
   |                 |                 |                 | The token can be obtained by calling the IAM API used to obtain a user token. The value of **X-Subject-Token** in the response header is the user token. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   ========= ========= ====== ===========
   Parameter Mandatory Type   Description
   ========= ========= ====== ===========
   policy_id No        String Policy ID.
   ========= ========= ====== ===========

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +------------------+--------------------------------------------------------------------------------+-----------------------------------------+
   | Parameter        | Type                                                                           | Description                             |
   +==================+================================================================================+=========================================+
   | associate_policy | :ref:`VaultPolicyResp <associatevaultpolicy__response_vaultpolicyresp>` object | Details of applying a policy to a vault |
   +------------------+--------------------------------------------------------------------------------+-----------------------------------------+

.. _associatevaultpolicy__response_vaultpolicyresp:

.. table:: **Table 5** VaultPolicyResp

   ========= ====== ======================================
   Parameter Type   Description
   ========= ====== ======================================
   policy_id String Configured policy ID
   vault_id  String Vault ID for configuring the policy ID
   ========= ====== ======================================

Example Requests
----------------

Applying a policy to a vault

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/vaults/79bd9daa-884f-4f84-b8fe-235d58cd927d/associatepolicy

   {
     "policy_id" : "7075c397-25a0-43e2-a83a-bb16eaca3ee5"
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "associate_policy" : {
       "vault_id" : "2402058d-8373-4b0a-b848-d3c0dfdc71a8",
       "policy_id" : "7075c397-25a0-43e2-a83a-bb16eaca3ee5"
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
