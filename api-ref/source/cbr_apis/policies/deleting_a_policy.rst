:original_name: DeletePolicy.html

.. _DeletePolicy:

Deleting a Policy
=================

Function
--------

This API is used to delete a policy.

URI
---

DELETE /v3/{project_id}/policies/{policy_id}

.. table:: **Table 1** Path Parameters

   ========== ========= ====== ===========
   Parameter  Mandatory Type   Description
   ========== ========= ====== ===========
   policy_id  Yes       String Policy ID
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

Response Parameters
-------------------

None

Example Requests
----------------

.. code-block:: text

   DELETE  https://{endpoint}/v3/{project_id}/policies/{policy_id}

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
