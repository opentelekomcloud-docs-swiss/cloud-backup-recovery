:original_name: cbr_03_0032.html

.. _cbr_03_0032:

Restoring from a Cloud Server Backup
====================================

When disks on a server are faulty or their data is lost, you can use a backup to restore the server to its state when the backup was created.

Constraints
-----------

-  When restoring from a cloud server backup, backup of a data disk cannot be restored to the system disk.
-  Data cannot be restored to servers in the **Faulty** state.

Prerequisites
-------------

-  Disks are running properly on the server whose data needs to be restored.
-  The server has at least one **Available** backup.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. In the row of the backup, click **Restore Server**. See :ref:`Figure 1 <cbr_03_0032__fig533382242914>`.

   .. important::

      The current server data will be overwritten by the data captured at the time of backup. The restoration cannot be undone.

   .. _cbr_03_0032__fig533382242914:

   **Figure 1** Restoring a server

   |image3|

#. (Optional) Deselect **Start the server immediately after restoration**.

   If you do so, manually start the server after the restoration is complete.

   .. important::

      Servers will be shut down during restoration, so you are advised to perform a restoration during off-peak hours.

#. In the **Destination Disk** drop-down list, select the target disk to which the backup will be restored.

   .. note::

      -  If the server has only one disk, the backup is restored to that disk by default.
      -  If the server has multiple disks, the backup is restored to the original disks by default. You can also restore the backup to a different disk of at least the same size as the original disk.
      -  When restoring from a cloud server backup, backup of a data disk cannot be restored to the system disk.

   .. important::

      If the number of disks to be restored is greater than the number of disks that were backed up, restoration may cause data inconsistency.

      For example, if the Oracle data is scattered across multiple disks and only some of them are restored, data inconsistency may occur and the application may fail to start.

#. Click **Yes** and confirm that the restoration is successful.

   You can view the restoration status in the backup list. When the backup enters the **Available** state and no new restoration tasks failed, the restoration is successful. The resource is restored to the state when that backup was created.

   For details about how to view failed restoration tasks, see :ref:`Managing Tasks <cbr_03_0035>`.

   .. important::

      If you use a cloud server backup to restore a logical volume group, you need to attach the logical volume group again.

      Due to Window limitations, data disks may fail to be displayed after a Windows server is restored. If this happens, manually bring these data disks online. For details, see :ref:`Data Disks Are Not Displayed After a Windows Server Is Restored <cbr_05_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000001232077795.png
