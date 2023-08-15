:original_name: AddVaultResource.html

.. _AddVaultResource:

Associating Resources
=====================

Function
--------

This API is used to associate resources with a vault.

URI
---

POST /v3/{project_id}/vaults/{vault_id}/addresources

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

   +-----------+-----------+-----------------------------------------------------------------------------------+---------------+
   | Parameter | Mandatory | Type                                                                              | Description   |
   +===========+===========+===================================================================================+===============+
   | resources | Yes       | Array of :ref:`ResourceCreate <addvaultresource__request_resourcecreate>` objects | Resource list |
   +-----------+-----------+-----------------------------------------------------------------------------------+---------------+

.. _addvaultresource__request_resourcecreate:

.. table:: **Table 4** ResourceCreate

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                       |
   +=================+=================+=================+===================================================================================================+
   | id              | Yes             | String          | ID of the resource to be backed up                                                                |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | type            | Yes             | String          | Type of the resource to be backed up, which can be **OS::Nova::Server** or **OS::Cinder::Volume** |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+
   | name            | No              | String          | Resource name                                                                                     |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | Minimum: **0**                                                                                    |
   |                 |                 |                 |                                                                                                   |
   |                 |                 |                 | Maximum: **255**                                                                                  |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------+

.. table:: **Table 5** ResourceExtraInfo

   +-----------------+-----------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory | Type             | Description                                                                                                                                                                                                                                                                               |
   +=================+===========+==================+===========================================================================================================================================================================================================================================================================================+
   | exclude_volumes | No        | Array of strings | ID of the disk that will not be backed up. This parameter is used when servers are added to a vault, which include all server disks. But some disks do not need to be backed up. Or in case that a server was previously added and some disks on this server do not need to be backed up. |
   +-----------------+-----------+------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 6** Response body parameters

   +------------------+------------------+-------------------------------------------+
   | Parameter        | Type             | Description                               |
   +==================+==================+===========================================+
   | add_resource_ids | Array of strings | List of resource IDs that have been added |
   +------------------+------------------+-------------------------------------------+

Example Requests
----------------

.. code-block:: text

   POST https://{endpoint}/v3/f841e01fd2b14e7fa41b6ae7aa6b0594/vaults/79bd9daa-884f-4f84-b8fe-235d58cd927d/addresources

   {
     "resources" : [ {
       "extra_info" : {
         "exclude_volumes" : [ "bdef09bb-293f-446a-88a4-86e9f14408c4" ]
       },
       "id" : "97595625-198e-4e4d-879b-9d53f68ba551",
       "type" : "OS::Nova::Server"
     } ]
   }

Example Responses
-----------------

**Status code: 200**

OK

.. code-block::

   {
     "add_resource_ids" : [ "97595625-198e-4e4d-879b-9d53f68ba551" ]
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
