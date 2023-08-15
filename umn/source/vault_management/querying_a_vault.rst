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

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. View the basic information about vaults. Related parameters are described in the following table. See :ref:`Figure 1 <cbr_03_0002__fig10889142793018>`.

   .. _cbr_03_0002__fig10889142793018:

   **Figure 1** Vault list

   |image2|

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
      |                                   | -  A server backup vault stores backups of common servers.                                                                                                                                                                                                       |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Vault Capacity (GB)               | Capacity used by backups in the vault. It shows the space used by backups and the vault capacity.                                                                                                                                                                |
      |                                   |                                                                                                                                                                                                                                                                  |
      |                                   | For example: If **20/100** is displayed, 20 GB has been used out of the 100 GB vault capacity.                                                                                                                                                                   |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Associated Servers/Disks          | Number of servers and disks associated with the vault. You can click the number to view details of associated resources. The associated capacity shown on the details page is the total capacity of all the resources that have been associated with this vault. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. On any backup page, click the **Vaults** tab and set filter criteria to view the vaults. See :ref:`Figure 2 <cbr_03_0002__fig16320163410256>`.

   .. _cbr_03_0002__fig16320163410256:

   **Figure 2** Querying a vault

   |image3|

   -  Select a value from the status drop-down list to query vaults by status. :ref:`Table 2 <cbr_03_0002__table18768121721316>` describes the vault statuses.

      .. _cbr_03_0002__table18768121721316:

      .. table:: **Table 2** Vault statuses

         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Status                | Status Attribute      | Description                                                                                                                                                                                                                                                  |
         +=======================+=======================+==============================================================================================================================================================================================================================================================+
         | All statuses          | --                    | All vaults are displayed if this value is selected.                                                                                                                                                                                                          |
         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Available             | A stable state        | A stable state after a vault task is complete.                                                                                                                                                                                                               |
         |                       |                       |                                                                                                                                                                                                                                                              |
         |                       |                       | This state allows most of the operations.                                                                                                                                                                                                                    |
         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Locked                | An intermediate state | An intermediate state when a capacity expansion is in progress.                                                                                                                                                                                              |
         |                       |                       |                                                                                                                                                                                                                                                              |
         |                       |                       | In this state, you cannot expand the vault capacity. However, you can perform other operations, such as applying a policy and associating servers, file systems, or disks. After the capacity expansion is complete, the vault status becomes **Available**. |
         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Deleting              | An intermediate state | An intermediate state when a vault is being deleted.                                                                                                                                                                                                         |
         |                       |                       |                                                                                                                                                                                                                                                              |
         |                       |                       | In this state, a progress bar is displayed indicating the deletion progress. If the progress bar remains unchanged for an extended time, an exception has occurred. Contact the administrator.                                                               |
         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Error                 | A stable state        | A vault enters the **Error** state when an exception occurs during task execution.                                                                                                                                                                           |
         |                       |                       |                                                                                                                                                                                                                                                              |
         |                       |                       | You can click **Tasks** in the navigation pane on the left to view the error cause. If the error persists, contact the administrator.                                                                                                                        |
         +-----------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   -  Search the vault by its name or ID.

   -  Click **Search by Tag** in the upper right corner to search for vaults by tag.

      -  On the **Search by Tag** tab page that is displayed, enter an existing tag key and value and click |image4|. The added tag search criteria are displayed under the text boxes. Click **Search** in the lower right corner.
      -  You can use more than one tag for a combination search. Each time after a key and a value are entered, click |image5|. The added tag search criteria are displayed under the text boxes. When more than one tag is added, the tags will be applied together for a combination search. A maximum of 10 tags can be added at a time.
      -  You can click **Reset** in the lower right corner to reset the search criteria.

#. Click the vault name to view details about the vault.

   .. note::

      For the values of used capacity and backup space, only the integer part is maintained, and the decimal part is rounded off. For example, the used backup space is displayed as 0 GB, but the backup space that has actually been used might be 0.2 GB.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001231789847.png
.. |image3| image:: /_static/images/en-us_image_0000001232028391.png
.. |image4| image:: /_static/images/en-us_image_0160751578.png
.. |image5| image:: /_static/images/en-us_image_0160751578.png
