:original_name: cbr_03_0002.html

.. _cbr_03_0002:

Querying a Vault
================

You can set search criteria for querying desired vaults in the vault list.

Prerequisites
-------------

A vault has been created.

Viewing Vault Details
---------------------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. On the **Vaults** tab, view basic information about all vaults. Related parameters are described in the following table. See :ref:`Figure 1 <cbr_03_0002__fig10889142793018>`.

   .. _cbr_03_0002__fig10889142793018:

   **Figure 1** Vault list

   |image3|

   .. table:: **Table 1** Basic information parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                      |
      +===================================+==================================================================================================================================================================================================================================================================+
      | Name/ID                           | Name and ID of the vault. Click the vault name to view details about the vault.                                                                                                                                                                                  |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Type                              | Vault type                                                                                                                                                                                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status                            | Vault status. :ref:`Table 2 <cbr_03_0002__table18768121721316>` describes the vault statuses.                                                                                                                                                                    |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Specifications                    | Vault specifications                                                                                                                                                                                                                                             |
      |                                   |                                                                                                                                                                                                                                                                  |
      |                                   | -  A server backup vault stores backups of non-database servers.                                                                                                                                                                                                 |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Vault Capacity (GB)               | Capacity used by the backups in the vault. It shows the space used by backups and the total vault capacity.                                                                                                                                                      |
      |                                   |                                                                                                                                                                                                                                                                  |
      |                                   | For example: If **20/100** is displayed, 20 GB has been used out of the 100 GB vault capacity.                                                                                                                                                                   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Associated Servers/Disks          | Number of servers and disks associated with the vault. You can click the number to view details of associated resources. The associated capacity shown on the details page is the total capacity of all the resources that have been associated with this vault. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. On the **Vaults** tab page, set filter criteria to view specific vaults. See :ref:`Figure 2 <cbr_03_0002__fig16320163410256>`.

   .. _cbr_03_0002__fig16320163410256:

   **Figure 2** Querying a vault

   |image4|

   -  Select a value from the status drop-down list to query vaults by status. :ref:`Table 2 <cbr_03_0002__table18768121721316>` describes the vault statuses.

      .. _cbr_03_0002__table18768121721316:

      .. table:: **Table 2** Vault statuses

         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Status                | Attribute             | Description                                                                                                                                                                                                                                                                                                                                                |
         +=======================+=======================+============================================================================================================================================================================================================================================================================================================================================================+
         | All statuses          | --                    | All vaults are displayed if this value is selected.                                                                                                                                                                                                                                                                                                        |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Available             | A stable state        | A stable state after a vault task is complete.                                                                                                                                                                                                                                                                                                             |
         |                       |                       |                                                                                                                                                                                                                                                                                                                                                            |
         |                       |                       | This state allows most of the operations.                                                                                                                                                                                                                                                                                                                  |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Locked                | An intermediate state | An intermediate state displayed when a capacity expansion is in progress.                                                                                                                                                                                                                                                                                  |
         |                       |                       |                                                                                                                                                                                                                                                                                                                                                            |
         |                       |                       | If a vault is in this state, you can perform operations, such as applying a policy and associating servers, file systems, or disks. However, the following operations are not allowed on such a vault: expanding the vault capacity and changing the vault specifications. Once those operations are complete, the vault status will become **Available**. |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Deleting              | An intermediate state | An intermediate state displayed when a vault is being deleted.                                                                                                                                                                                                                                                                                             |
         |                       |                       |                                                                                                                                                                                                                                                                                                                                                            |
         |                       |                       | In this state, a progress bar is displayed indicating the deletion progress. If the progress bar remains unchanged for an extended time, an exception has occurred. Contact technical support.                                                                                                                                                             |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Error                 | A stable state        | A vault enters the **Error** state when an exception occurs during task execution.                                                                                                                                                                                                                                                                         |
         |                       |                       |                                                                                                                                                                                                                                                                                                                                                            |
         |                       |                       | You can click **Tasks** in the navigation pane on the left to view the error cause. If the error persists, contact technical support.                                                                                                                                                                                                                      |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   -  Search a vault by its name or ID.

   -  Click **Search by Tag** in the upper right corner to search for vaults by tag.

      -  On the displayed **Search by Tag** page, enter an existing tag key and value and click |image5|. The added tag search criteria are displayed under the text boxes. Click **Search** in the lower right corner.
      -  You can add a maximum of 20 tags by clicking |image6|. They will be applied together for a combination search.
      -  You can click **Reset** in the lower right corner to reset the search criteria.

#. Click the name of a specific vault to view vault details.

   .. note::

      The values of used capacity and backup space are rounded off to integers. CBR will display 0 GB for any backup space less than 1 GB. For example, there may be 200 MB backup space used, but it will be displayed as 0 GB on the console.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001231789847.png
.. |image4| image:: /_static/images/en-us_image_0000001232028391.png
.. |image5| image:: /_static/images/en-us_image_0160751578.png
.. |image6| image:: /_static/images/en-us_image_0160751578.png
