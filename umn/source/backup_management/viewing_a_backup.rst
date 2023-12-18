:original_name: cbr_03_0013.html

.. _cbr_03_0013:

Viewing a Backup
================

In the backup list, you can set search criteria to filter backups and view their details. The results contain backup tasks that are running or have completed.

Prerequisites
-------------

At least one backup task has been created.

Viewing Backup Details
----------------------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and set filter criteria to view the backups. See :ref:`Figure 1 <cbr_03_0013__fig5673922177>`.

   .. _cbr_03_0013__fig5673922177:

   **Figure 1** Viewing a backup

   |image3|

   -  You can search for backups by selecting a status from the **All statuses** drop-down list in the upper right corner of the backup list. :ref:`Table 1 <cbr_03_0013__table067414221375>` describes the backup statuses.

      .. _cbr_03_0013__table067414221375:

      .. table:: **Table 1** Backup statuses

         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Status                | Status Attribute      | Description                                                                                                                                                                                                |
         +=======================+=======================+============================================================================================================================================================================================================+
         | All statuses          | --                    | All backups are displayed if this value is selected.                                                                                                                                                       |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Available             | A stable state        | A stable state of a backup after the backup is created, indicating that the backup is currently not being used.                                                                                            |
         |                       |                       |                                                                                                                                                                                                            |
         |                       |                       | This state allows most of the operations.                                                                                                                                                                  |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Creating              | An intermediate state | An intermediate state of a backup from the start of a backup job to the completion of this job.                                                                                                            |
         |                       |                       |                                                                                                                                                                                                            |
         |                       |                       | In the **Tasks** list, a progress bar is displayed for a backup task in this state. If the progress bar remains unchanged for an extended time, an exception has occurred. Contact technical support.      |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Restoring             | An intermediate state | An intermediate state when using the backup to restore data.                                                                                                                                               |
         |                       |                       |                                                                                                                                                                                                            |
         |                       |                       | In the **Tasks** list, a progress bar is displayed for a restoration task in this state. If the progress bar remains unchanged for an extended time, an exception has occurred. Contact technical support. |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Deleting              | An intermediate state | An intermediate state from the start of deleting the backup to the completion of deleting the backup.                                                                                                      |
         |                       |                       |                                                                                                                                                                                                            |
         |                       |                       | In the **Tasks** list, a progress bar is displayed for a deletion task in this state. If the progress bar remains unchanged for an extended time, an exception has occurred. Contact technical support.    |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Error                 | A stable state        | A backup enters the **Error** state when an exception occurs.                                                                                                                                              |
         |                       |                       |                                                                                                                                                                                                            |
         |                       |                       | A backup in this state cannot be used for restoration, and must be deleted manually. If manual deletion fails, contact technical support.                                                                  |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   -  You can search for backups by clicking **Advanced Search** in the upper right corner of the backup list.

      You can search by specifying a backup status, backup name, backup ID, vault ID, server name, server ID, server type, or the creation date. See :ref:`Figure 2 <cbr_03_0013__fig1067432214711>`.

      .. _cbr_03_0013__fig1067432214711:

      .. figure:: /_static/images/en-us_image_0251476754.png
         :alt: **Figure 2** Advanced Search

         **Figure 2** Advanced Search

#. Click the backup name to view details about the backup.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001186626606.png
