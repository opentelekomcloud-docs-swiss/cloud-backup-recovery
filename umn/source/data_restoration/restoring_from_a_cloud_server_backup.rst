:original_name: cbr_03_0032.html

.. _cbr_03_0032:

Restoring from a Cloud Server Backup
====================================

When disks on a server are faulty or their data is lost, you can use a backup to restore the server to its state when the backup was created.

.. note::

   The server is stopped before a data restoration, and automatically starts up after the restoration is complete. If you deselect **Start the server immediately after restoration**, you need to manually start the server after the restoration is complete.

Constraints
-----------

-  A data disk backup cannot be restored to the system disk.
-  Data cannot be restored to servers in the **Faulty** state.
-  An ongoing restoration task cannot be terminated.
-  Data cannot be restored for a cloud server that is being backed up.

Prerequisites
-------------

-  Disks are running properly on the server whose data needs to be restored.
-  The server has at least one available backup.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Click **Restore Server** in the **Operation** column, as shown in :ref:`Figure 1 <cbr_03_0032__fig533382242914>`.

   .. warning::

      -  The current server data will be overwritten by the data captured at the time of backup. **The restoration cannot be undone.**
      -  Servers will be shut down during restoration. It is recommended that you perform restoration during off-peak hours.

   .. _cbr_03_0032__fig533382242914:

   **Figure 1** Restoring a server

   |image3|

#. (Optional) Deselect **Start the server immediately after restoration**.

   If you do so, manually start the server after the restoration is complete.

#. In the **Destination Disk** drop-down list, select the target disk to which the backup will be restored.

   .. warning::

      If the number of disks to be restored is greater than the number of disks that were backed up, restoration may cause data inconsistency.

      For example, if the Oracle data is scattered across multiple disks and only some of the disks are restored, data may become inconsistent and the application may fail to start.

   .. note::

      -  If the server has only one disk, the backup is restored to that disk by default.
      -  If the server has multiple disks, the backup is restored to the original disks by default. You can also restore the backup to a different disk of at least the same size as the original disk.
      -  A data disk backup cannot be restored to the system disk.

#. After confirming that the information is correct, enter **YES**. Click **Yes** and confirm that the restoration is successful.

   You can view the restoration status in the backup list. When the backup enters the **Available** state and no new restoration tasks failed, the restoration is successful. The data is restored to the state when that backup was created.

   For details about how to view failed restoration tasks, see :ref:`Task Management <cbr_03_0035>`.

   .. note::

      If you use a cloud server backup to restore a logical volume group, you need to attach the logical volume group again.

Helpful Links
-------------

-  Due to Windows limitations, data disks may fail to be displayed after a Windows server is restored. If this happens, manually bring these data disks online. For details, see :ref:`Data Disks Are Not Displayed After a Windows Server Is Restored <cbr_05_0002>`.
-  :ref:`Can I Use a System Disk Backup to Recover an ECS? <cbr_06_0014>`
-  :ref:`Can a Server Be Restored from Its Backups After It Is Changed? <cbr_06_0016>`
-  :ref:`What Can I Do If the Password Becomes a Random One After I Use a Backup to Restore a Server or Use an Image to Create a Server? <cbr_06_0018>`
-  :ref:`What Changes Will Be Made to the Original Backup When I Use the Backup to Restore a Server? <cbr_06_0033>`

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002062648677.png
