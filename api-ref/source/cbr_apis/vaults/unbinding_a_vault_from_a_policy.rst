:original_name: DisassociateVaultPolicy.html

.. _DisassociateVaultPolicy:

Unbinding a Vault from a Policy
===============================

Function
--------

This API is used to unbind a vault from a policy.

URI
---

POST /v3/{project_id}/vaults/{vault_id}/dissociatepolicy

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
   | X-Auth-Token    | No              | String          | User token.                                                                                                                                                                   |
   |                 |                 |                 |                                                                                                                                                                               |
   |                 |                 |                 | Obtained by calling the corresponding IAM API. If the request is successfully processed, the value of **X-Subject-Token** included in the response header is the token value. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 3** Request body parameters

   ========= ========= ====== ===========
   Parameter Mandatory Type   Description
   ========= ========= ====== ===========
   policy_id Yes       String Policy ID
   ========= ========= ====== ===========

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +-------------------+-----------------------------------------------------------------------------------+--------------------------------------------+
   | Parameter         | Type                                                                              | Description                                |
   +===================+===================================================================================+============================================+
   | dissociate_policy | :ref:`VaultPolicyResp <disassociatevaultpolicy__response_vaultpolicyresp>` object | Details of unbinding a vault from a policy |
   +-------------------+-----------------------------------------------------------------------------------+--------------------------------------------+

.. _disassociatevaultpolicy__response_vaultpolicyresp:

.. table:: **Table 5** VaultPolicyResp

   ========= ====== ======================================
   Parameter Type   Description
   ========= ====== ======================================
   policy_id String Configured policy ID
   vault_id  String Vault ID for configuring the policy ID
   ========= ====== ======================================

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/vaults/79bd9daa-884f-4f84-b8fe-235d58cd927d/dissociatepolicy

   {
     "policy_id" : "7075c397-25a0-43e2-a83a-bb16eaca3ee5"
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "dissociate_policy" : {
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
