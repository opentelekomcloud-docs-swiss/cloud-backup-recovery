:original_name: cbr_02_0007.html

.. _cbr_02_0007:

Creating a Cloud Disk Backup
============================

This section describes how to quickly create a cloud disk backup.

During the cloud disk backup, the performance of the disk is not affected. To ensure data integrity, back up the disk during off-peak hours when no write operation is performed on the disk.

Prerequisites
-------------

A disk can be backed up only when its status is **Available** or **In-use**. If you have performed operations such as expanding, attaching, detaching, or deleting a disk, refresh the page first to ensure that the operation is complete and then determine whether to back up the disk.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. On the **Cloud Disk Backup** page, click the **Vaults** tab and find the vault to which the disk is associated.

#. Choose **More** > **Perform Backup** in the **Operation** column. In the disk list, select the disk you want to back up. After a disk is selected, it is added to the list of selected disks. See :ref:`Figure 1 <cbr_02_0007__fig2557455115213>`.

   .. _cbr_02_0007__fig2557455115213:

   **Figure 1** Selecting the disk to be backed up

   |image2|

   .. note::

      The system will identify whether the selected disk is encrypted. If it is encrypted, its backup data will be stored in encrypted mode.

#. Set the **Name** and **Description** for the backup. :ref:`Table 1 <cbr_02_0007__table4829135361311>` describes the parameters.

   .. _cbr_02_0007__table4829135361311:

   .. table:: **Table 1** Parameter description

      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Parameter             | Description                                                                                                                                               | Remarks               |
      +=======================+===========================================================================================================================================================+=======================+
      | Name                  | Name of the backup you are creating.                                                                                                                      | manualbk_d819         |
      |                       |                                                                                                                                                           |                       |
      |                       | A name must contain 1 to 64 characters including digits, letters, underscores (_), or hyphens (-).                                                        |                       |
      |                       |                                                                                                                                                           |                       |
      |                       | .. note::                                                                                                                                                 |                       |
      |                       |                                                                                                                                                           |                       |
      |                       |    You can use the default name, which is in the format of **manualbk\_**\ *xxxx*.                                                                        |                       |
      |                       |                                                                                                                                                           |                       |
      |                       |    If multiple disks are to be backed up, the system automatically adds suffixes to their backup names, for example, **backup-0001** and **backup-0002**. |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+
      | Description           | Description of the backup.                                                                                                                                | --                    |
      |                       |                                                                                                                                                           |                       |
      |                       | It cannot exceed 255 characters.                                                                                                                          |                       |
      +-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+

#. Choose whether to enable full backup. If full backup is enabled, the system performs a full backup on every associated disk, which requires a larger capacity compared to an incremental backup. See :ref:`Figure 2 <cbr_02_0007__fig789511544815>`.

   .. _cbr_02_0007__fig789511544815:

   **Figure 2** Selecting full backup

   |image3|

#. (Optional) You can also click the vault name to open the detailed page of the vault. On the **Associated Disks** tab page, locate the target disk. Click **Perform Backup** in the **Operation** column of the disk. See :ref:`Figure 3 <cbr_02_0007__fig7287161212118>`.

   .. _cbr_02_0007__fig7287161212118:

   **Figure 3** Perform Backup

   |image4|

#. Click **Yes**. The system automatically creates a backup for the disk.

   On the **Backups** tab page of the **Cloud Disk Backup** page, if the status of the backup is **Available**, the backup task is successful.

   .. note::

      If you delete files on the disk during the backup, the deleted files may fail to be backed up. Therefore, to ensure data integrity, you are advised to delete the target data after the current backup is complete and then perform a backup again.

   After the backup is complete, you can use the backup to restore disk data on the **Cloud Disk Backup** page. For details, see :ref:`Restoring Data Using a Cloud Disk Backup <cbr_03_0033>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001186588456.png
.. |image3| image:: /_static/images/en-us_image_0184062862.png
.. |image4| image:: /_static/images/en-us_image_0000001232149603.png
