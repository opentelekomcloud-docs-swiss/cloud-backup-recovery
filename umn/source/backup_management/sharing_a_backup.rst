:original_name: cbr_03_0014.html

.. _cbr_03_0014:

Sharing a Backup
================

Scenarios
---------

You can share server or disk backups with domains. Shared backups can be used to create servers or disks.

Context
-------

**For sharers:**

-  Backups can only be shared among domains in the same region. They cannot be shared across regions.
-  The project that receives a shared backup must be in the same region as the backup.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.
-  When an encrypted backup is shared, the encryption key must also be shared with the recipient so that the recipient can use the shared backup.

   -  For details about how to share a key, see `Creating a Grant <https://docs.sc.otc.t-systems.com/key-management-service/umn/key_management_service/managing_a_grant/creating_a_grant.html>`__. To obtain the recipient **Account ID**, hover over the username and choose **My Credentials** > to check the **Account ID**.
   -  Cloud disk backup encryption depends on an agency that grants KMS access permissions to EVS. If the disk to be backed up is encrypted, the disk backup will be encrypted. The encryption attribute of backups cannot be changed.

**For recipients:**

-  A recipient must have at least one backup vault to store the accepted shared backup, and the vault's remaining space must be greater than the size of the backup to be accepted.
-  A recipient can choose to accept or reject a backup sharing request. After accepting the backup, the recipient can use the backup to create servers or disks.
-  When a sharer deletes a shared backup, the backup will also be deleted from the recipient's account, but the disks or servers previously created using the backup will be retained.

Initiating Backup Sharing
-------------------------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab and set filter criteria to view the backups.

#. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.

   The backup name, server or disk name, backup ID, and backup type are displayed.

   |image3|

#. Click the **Share Backup** tab.

#. Enter the account name of the recipient.

#. Click **Add**. The account and project to be added is displayed in the list. You can continue to add accounts. A backup can be shared to a maximum of **10** projects.

#. Click **OK**.

   Go back to the backup list, click the backup name to go to the backup details page, and click the **Share List** tab to view the shared backup.

Accepting the Shared Backup
---------------------------

#. Log in to the CBR console.

   a. In the upper left corner, click |image4| and select a region.
   b. Click |image5| and choose **Storage** > **Cloud Backup and Recovery**.

#. Click the **Backups** tab on the cloud server or disk backup vault page and then click **Backups Shared with Me**.

#. Ensure that the recipient has at least one backup vault before accepting the shared backup. For how to purchase a backup vault, see :ref:`Step 1: Create a Vault <cbr_07_0065>`.

#. Click **Accept**. On the displayed page, select the vault used to store the shared backup. Ensure that the vault's remaining capacity is greater than the backup size.

   **Automatic Association:** Determines whether to enable automatic association for the vault. If you select **Configure**, the vault automatically scans for and associates servers that have not been backed up and performs backup in the next backup period.

#. View the shared backup you accepted in the backup list.

Canceling Backup Sharing
------------------------

#. Log in to the CBR console.

   a. In the upper left corner, click |image6| and select a region.
   b. Click |image7| and choose **Storage** > **Cloud Backup and Recovery**.

#. On the cloud server backup page or cloud disk backup page, click the **Backups** tab and set filter criteria to view the backups.

#. Locate the target backup and choose **More** > **Share Backup** in the **Operation** column.

   The backup name, server or disk name, backup ID, and backup type are displayed.

#. Click the **Cancel Sharing** tab, select the projects you want to cancel sharing, and click **OK**.

   Return to the backup list, click the backup name to go to the backup details page, and click the **Share List** tab to view the unshared backups.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image3| image:: /_static/images/en-us_image_0000002021478318.png
.. |image4| image:: /_static/images/en-us_image_0159365094.png
.. |image5| image:: /_static/images/en-us_image_0000001599534545.jpg
.. |image6| image:: /_static/images/en-us_image_0159365094.png
.. |image7| image:: /_static/images/en-us_image_0000001599534545.jpg
