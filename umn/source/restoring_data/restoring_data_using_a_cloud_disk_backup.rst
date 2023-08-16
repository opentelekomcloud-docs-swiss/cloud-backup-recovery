:original_name: cbr_03_0033.html

.. _cbr_03_0033:

Restoring Data Using a Cloud Disk Backup
========================================

You can use a disk backup to restore a disk to the time when the backup was created.

Backups can only be restored to original disks. If you want to restore a backup to a disk other than the original one, directly use the backup to create a new disk.

Prerequisites
-------------

-  The status of the disk to be restored must be **Available**.
-  Before restoring the disk data, stop the server to which the disk is attached and detach the disk from the server. After the disk data is restored, attach the disk to the server and start the server.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Querying a Backup <cbr_03_0013>`.

#. In the row of the backup, click **Restore Disk**. The **Restore Disk** page is displayed. See :ref:`Figure 1 <cbr_03_0033__fig122481021113018>`.

   .. important::

      -  The backup data will overwrite the current disk data, and the restoration cannot be undone.
      -  If the restore button is grayed out, stop the server, detach the disk to be restored, and then restore data. After the disk data is restored, attach the disk to the server and start the server.

   .. _cbr_03_0033__fig122481021113018:

   **Figure 1** Restore Disk

   |image2|

#. Click **Yes**. You can check whether the data is successfully restored on the **Backups** tab page of disk backup.

   When the status of the backup changes to **Available**, the restoration is successful. The resource is restored to the state at the time you took that backup.

#. After the restoration is complete, re-attach the disk to the server. For details, see section "Attaching an Existing Non-Shared Disk" in the *Elastic Volume Service User Guide*.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001232279489.png
