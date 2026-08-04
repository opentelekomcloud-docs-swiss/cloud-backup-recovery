:original_name: cbr_03_0015.html

.. _cbr_03_0015:

Deleting a Backup
=================

You can delete unwanted backups to reduce space usage and costs.

CBR supports manual deletion of backups and automatic deletion of expired backups. The latter is executed based on the backup retention rule in the backup policy. For details, see :ref:`Creating a Backup Policy <cbr_03_0025>`.

.. note::

   -  Backups are not stored on a server. Deleting backups has no impact on the server performance.
   -  If a backup already exists while the next incremental backup task is in progress, any attempt to delete the existing backup will be blocked. You must wait until the incremental backup finishes before performing the deletion.
   -  CBR automatically creates snapshots during backup and retains the latest snapshot for each disk. If a disk already has a backup, after another backup, the old snapshot will be deleted and the latest one will be retained.

Prerequisites
-------------

-  There is at least one backup.
-  The backups to be deleted are in the **Available** or **Error** state.

Procedure
---------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab. Locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Choose **More** > **Delete** from the **Operation** column. Alternatively, select the backups you want to delete in a batch and click **Delete** in the upper left corner to delete them.


   **Figure 1** Deleting a backup

   |image3|

#. In the displayed dialog box, confirm the information, enter **DELETE**, and click **OK**.

   Return to the backup list. If the target backup no longer appears, it was deleted successfully.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002021320606.png
