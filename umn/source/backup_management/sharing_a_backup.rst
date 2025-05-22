:original_name: cbr_03_0014.html

.. _cbr_03_0014:

Sharing a Backup
================

Scenarios
---------

You can share server or disk backups with domains. Shared backups can be used to create servers or disks.

Context
-------

**Sharer**

-  Backups can only be shared among domains in the same region. They cannot be shared across regions.
-  Backups cannot be shared across regions. Account to which a backup is shared must be in the same region as the backup.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.
-  When an encrypted backup is shared, the encryption key must be shared with the recipient so that the recipient can use the shared backup.

   .. important::

      -  For details about how to share a key, see `Creating a Grant <https://docs.sc.otc.t-systems.com/key-management-service/umn/key_management_service/managing_a_grant/creating_a_grant.html>`__. To obtain the recipient **Account ID**, hover over the username and choose **My Credentials** > to check the **Account ID**.
      -  Cloud disk backup encryption depends on an agency created that grants KMS access permissions to EVS. If the disk to be backed up is encrypted, the disk backup generated will be an encrypted backup. The encryption attribute of backups cannot be changed.

**Recipient**

-  A recipient must have at least one backup vault to store the accepted shared backup, and the vault's remaining space must be greater than the size of the backup to be accepted.
-  A recipient can choose to accept or reject a backup. After accepting a backup, the recipient can use the backup to create new servers or disks.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.

Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image1| in the upper left corner and select a region.
   c. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and set filter criteria to view the backups.

#. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.

   The backup name, server or disk name, backup ID, and backup type are displayed.

   -  Sharing a backup


      **Figure 1** Share Backup

      |image3|

   a. Click the **Share Backup** tab.

   b. Enter the account name of the recipient.

   c. Click **Add**.

      The account and project to be added will be displayed in the list. You can add multiple account names. A backup can be shared to a maximum of 10 projects.

   d. Click **OK**.

      Return to the backup list, click the backup name to go to the backup details page, and click the **Share List** tab to view the shared backup.

   -  Canceling sharing

      Click the **Cancel Sharing** tab, select the projects you want to cancel sharing, and click **OK**.

      Return to the backup list, click the backup name to go to the backup details page, and click the **Share List** tab to view the unshared backups.


Procedure
---------

#. Log in to the CBR console.

   a. Log in to the management console.
   b. Click |image4| in the upper left corner and select a region.
   c. Click |image5| and choose **Storage** > **Cloud Backup and Recovery**. Select a backup type from the left navigation pane.

#. Click the **Backups** tab and then click **Backups Shared with Me**.

#. Ensure that the recipient has at least one backup vault before accepting the shared backup. For how to purchase a backup vault, see :ref:`Step 1: Create a Vault <cbr_07_0065>`.

#. Click **Accept**. On the displayed page, select the vault used to store the shared backup. Ensure that the vault's remaining capacity is greater than the backup size.

   **Automatic Association:** Determine whether to enable automatic association for the vault. If you select **Configure**, the vault automatically scans and associates in the next backup period servers that have not been backed up and performs backup.

#. View the shared backup you accepted in the backup list.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002021478318.png
.. |image4| image:: /_static/images/en-us_image_0159365094.png
.. |image5| image:: /_static/images/en-us_image_0000001599534545.jpg
