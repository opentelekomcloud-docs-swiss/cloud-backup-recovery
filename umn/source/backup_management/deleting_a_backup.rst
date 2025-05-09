:original_name: cbr_03_0015.html

.. _cbr_03_0015:

Deleting a Backup
=================

You can delete unwanted backups to reduce space usage and costs.

CBR supports manual deletion of backups and automatic deletion of expired backups. The latter is executed based on the backup retention rule in the backup policy. For details, see :ref:`Creating a Backup Policy <cbr_03_0025>`.

.. note::

   -  Backups are not stored on a server. Deleting backups has no impact on the server performance.
   -  If a backup has been created and the next backup task is in progress, CBR will not allow you to delete the most recent backup created. You can delete the backup only after the backup task is complete.
   -  CBR automatically creates snapshots during backup and retains the latest snapshot for each disk. If a disk already has a backup, after another backup, the old snapshot will be deleted and the latest one will be retained.

Prerequisites
-------------

-  There is at least one backup.
-  The backup to be deleted is in the **Available** or **Error** state.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and locate the desired backup. For details, see :ref:`Viewing a Backup <cbr_03_0013>`.

#. Choose **More** > **Delete** from the **Operation** column. See :ref:`Figure 1 <cbr_03_0015__fig1233612574363>`. Alternatively, select the backups you want to delete in a batch and click **Delete** in the upper left corner to delete them.

   .. _cbr_03_0015__fig1233612574363:

   **Figure 1** Deleting a backup

   |image3|

#. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002021320606.png
