:original_name: cbr_01_0009.html

.. _cbr_01_0009:

Constraints
===========

General
-------

-  A vault can be associated with only one backup policy.
-  A vault can be associated with a maximum of 256 resources.
-  A maximum of 32 backup policies can be created.
-  Only backups in the **Available** or **Locked** vaults can be used to restore data.
-  Backups in a **Deleting** vault cannot be deleted.
-  When Storage Disaster Recovery Service (SDRS) is used to set up disaster recovery for cloud servers, restorations can be performed at the disaster recovery site only after protection is disabled.
-  Backups cannot be downloaded to a local PC or uploaded to OBS.
-  A vault and its associated servers or disks must be in the same region.

Cloud Disk Backup
-----------------

-  Only disks in the **Available** or **In-use** state can be backed up.
-  A new disk must be at least as large as the backup's source disk.

Cloud Server Backup
-------------------

-  A maximum of 10 shared disks can be backed up with a cloud server.
-  Only backups in the **Available** or **Locked** vaults can be used to create images.
-  Images cannot be created from backups if the amount of resources associated with a server backup vault exceeds the quota.
-  Only ECS backups can be used to create images.
-  You are advised not to back up a server whose disk size exceeds 4 TB.
