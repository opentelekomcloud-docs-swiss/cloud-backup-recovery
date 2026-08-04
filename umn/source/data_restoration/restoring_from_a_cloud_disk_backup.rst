:original_name: cbr_03_0033.html

.. _cbr_03_0033:

Restoring from a Cloud Disk Backup
==================================

You can use a disk backup to restore the disk to its state when the backup was created.

Before restoring the disk data, stop the server to which the disk is attached and detach the disk from the server. After the disk data is restored, attach the disk to the server and start the server.

Prerequisites
-------------

-  The disk to be restored is **Available**.
-  The server is stopped and the disk is detached from the server. After the disk data is restored, attach the disk to the server and start the server.

Constraints
-----------

-  Backups can only be restored to original disks and cannot be restored to other disks. If you want to restore a backup to a different disk, use the backup to create a new disk.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. In the row of the backup, click **Restore Disk**. The **Restore Disk** dialog box is displayed.

   .. warning::

      -  The EVS disk data will be overwritten by the data captured at the time of backup. **The restoration cannot be undone.**
      -  If the restore button is grayed out, stop the server, detach the disk, and try again. After the disk data is restored, attach the disk to the server and start the server.


   **Figure 1** Restore Disk

   |image3|

#. Confirm the information as prompted and enter **YES**. Click **Yes**. You can check whether data is successfully restored on the **Backups** tab of **Cloud Disk Backups** or on the EVS console.

   When the backup status changes to **Available**, the restoration is successful. The resource is restored to the state when that backup was created.

#. After the restoration is complete, re-attach the disk to the server. For details, see section "Attaching a Non-Shared Disk" in the *Elastic Volume Service User Guide*.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002062648297.png
