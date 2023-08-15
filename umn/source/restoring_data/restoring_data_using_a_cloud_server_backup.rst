:original_name: cbr_03_0032.html

.. _cbr_03_0032:

Restoring Data Using a Cloud Server Backup
==========================================

When disks on a server are faulty or server data is lost due to misoperations, you can use a backup to restore the server.

Context
-------

-  Data on data disks cannot be restored to system disks.
-  Data cannot be restored to servers in the **Faulty** state.

Prerequisites
-------------

-  Disks on the server whose data needs to be restored are running properly.
-  The server whose data needs to be restored has at least one **Available** backup.

Procedure
---------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Querying a Backup <cbr_03_0013>`.

#. In the row of the backup, click **Restore Server**. See :ref:`Figure 1 <cbr_03_0032__fig533382242914>`.

   .. important::

      The historical data at the backup point in time will overwrite the current server data. The restoration cannot be undone.

   .. _cbr_03_0032__fig533382242914:

   **Figure 1** Restoring a server

   |image2|

#. (Optional) Deselect **Start the server immediately after restoration**.

   If you deselect **Start the server immediately after restoration**, manually start the server after the restoration is complete.

   .. important::

      Servers are shut down during restoration. It is therefore recommended that you perform restoration operations during off-peak hours.

#. In the **Specified Disk** drop-down list, select the target disk to which the backup will be restored.

   .. note::

      -  If the server has only one disk, the backup is restored to the disk by default.
      -  If the server has multiple disks, the backup is respectively restored to the original disks by default. You can also restore the backup to another disk on the backup server by selecting the disk from the drop-down list. However, the capacity of the specified disk must not be smaller than that of the backup source disk.
      -  Data on data disks cannot be restored to system disks.

   .. important::

      If the number of disks to be restored is greater than the number of disks that are backed up, restoration may cause data inconsistency.

      For example, if the data of Oracle is scattered across multiple disks and only some of them are restored, data inconsistency occurs after the restoration and the application may unable to start.

#. Click **Yes** and confirm the restoration is successful.

   In the backup list, view the restoration status. When the backup enters the **Available** state and no new failed restoration tasks exist in **Tasks**, the restoration is successful. The resource is restored to the state at the time you took that backup.

   For details about how to view failed restoration tasks, see :ref:`Managing Tasks <cbr_03_0035>`.

   .. important::

      If a Windows server is restored, data disks may fail to be displayed due to Windows limitations.

      After you use a cloud server backup to restore a logical volume group, the logical volume group needs to be attached again.

      You need to manually online these data disks. For details, see :ref:`Data Disks Are Not Displayed After a Windows Server Is Restored <cbr_05_0002>`.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001232077795.png
