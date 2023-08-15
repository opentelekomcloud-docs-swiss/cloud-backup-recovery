:original_name: cbr_03_0014.html

.. _cbr_03_0014:

Sharing a Backup
================

You can share a server or disk backup with other domains. Shared backups can be used to create servers or disks.

Context
-------

**Sharer**

-  Backups can only be shared among domains in the same region.
-  Encrypted backups cannot be shared. Backups cannot be shared across regions. Account to which a backup is shared must be in the same region as the backup.
-  Accepted shared backups will be deleted once the sharer deletes the original backup. If a shared backup has been used to create new disks or servers, the created resources will not be deleted.

**Recipient**

-  A recipient must have at least one backup vault to store the accepted shared backup, and the vault remaining space must be greater than the size of the backup to be accepted.
-  A recipient can choose whether to accept a backup. After accepting a backup, the recipient can use the backup to create new servers or disks.
-  Accepted shared backups will be deleted once the sharer deletes the original backup. If a shared backup has been used to create new disks or servers, the created resources will not be deleted.

Procedure for the Sharer
------------------------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. On the cloud server or cloud disk backup page, click the **Backups** tab and set filter criteria to view the backups.

#. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.

   The backup name, server name, backup ID, and backup type are displayed.

   -  Sharing a backup


      **Figure 1** Sharing a backup

      |image2|

   a. Click the **Share Backup** tab.
   b. Enter the account name of the tenant to whom the backup is to be shared.
   c. Click **Add**. The account name and project to be added are displayed in the list. You can continue to add account names. A backup can be shared to a maximum of ten projects.
   d. Click **OK**.

   -  Canceling sharing

   a. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.
   b. On the displayed page, click the **Cancel Sharing** tab and select the backup that no longer needs to be shared. Then, click **OK**.

Procedure for the Recipient
---------------------------

#. Log in to CBR Console.

   a. Log in to the management console.
   b. Click |image3| in the upper left corner and select your region and project.
   c. Choose **Storage** > **Cloud Backup and Recovery**. Select a backup tab from the left navigation pane.

#. On the cloud server or cloud disk backup page, click the **Backups** tab and then click **Backups Shared with Me**.

#. Ensure that the recipient has at least one backup vault before accepting the shared backup. For how to purchase a backup vault, see :ref:`Step 1: Create a Vault <en-us_topic_0170938140>`.

#. Click **Accept**. On the displayed page, select the vault used to store the shared backup. Ensure that the vault remaining capacity is greater than the backup size.

   Automatic Association: Determine whether to enable automatic association for the vault. If you select **Configure**, the vault automatically scans and associates in the next backup period servers that have not been backed up and performs backup.

#. After a shared backup is accepted, it will be displayed in the backup list.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001232281309.png
.. |image3| image:: /_static/images/en-us_image_0159365094.png
