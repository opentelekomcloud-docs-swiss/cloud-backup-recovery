:original_name: cbr_01_0035.html

.. _cbr_01_0035:

Enabling Backup Locking
=======================

Backup locking enhances backup data security by preventing accidental or malicious deletion. After backup locking is enabled, all **automatic backups** in vaults will enter the write once, read many (WORM) state. The backups are strictly protected and cannot be deleted by any user during their retention periods. The backups can only be automatically deleted based on the preset retention rules.

.. note::

   The retention period refers to the time from when an automatic backup is generated to when the backup is deleted according to the retention rule defined in the policy. For example, if a policy's retention rule specifies a three-day period, any automatic backup generated under that policy will be automatically deleted three days after its creation. The interval between the backup's creation and its scheduled deletion is referred to as the retention period.

Scenarios
---------

You can enable backup locking for vaults to prevent backups from being deleted by mistake or maliciously.

Once enabled, all automatic backups in the vaults enter the WORM state. No one can delete the backups that are in their retention periods.

This section describes how to enable backup locking for a vault. You can also enable it when creating a vault.

.. note::

   -  Backup locking does not affect normal backup, restoration, and replication operations.
   -  Manual backups are not affected by backup locking and can be manually deleted.

Constraints
-----------

-  Backup locking cannot be disabled after it is enabled. If the vault capacity is full after backup locking is enabled, resource backups may fail because backups cannot be deleted in advance.
-  After backup locking is enabled, associated resources cannot be dissociated.
-  Resources in a vault with backup locking enabled can be migrated to another vault with backup locking enabled. Resources in a vault with backup locking enabled cannot be migrated to another vault without backup locking enabled. If resources have been migrated from a vault without backup locking to a vault with backup locking, the resources cannot be migrated back to the original vault.
-  After backup locking is enabled, policy-based backups can only be deleted after they expire. You cannot manually delete them.

Enabling Backup Locking for an Existing Vault
---------------------------------------------

#. Log in to the CBR console.

   a. In the upper left corner, click |image1| and select a region.
   b. Click |image2| and choose **Storage** > **Cloud Backup and Recovery**.

#. Locate the target vault and choose **More** > **Enable Backup Locking** in the **Operation** column.

#. In the displayed dialog box, click **OK** to enable backup locking.


   .. figure:: /_static/images/en-us_image_0000002648124280.png
      :alt: **Figure 1** Backup locking

      **Figure 1** Backup locking

#. Click **OK**.

   On the vault list, you can see that the value in the **Backup Locking** column is **Enabled**.

.. |image1| image:: /_static/images/en-us_image_0159365094.png
.. |image2| image:: /_static/images/en-us_image_0000001599534545.jpg
