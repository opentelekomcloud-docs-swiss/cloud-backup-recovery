:original_name: cbr_01_0012.html

.. _cbr_01_0012:

CBR Concepts
============

Vault
-----

CBR stores backups of a variety of resources in vaults, which are classified into the following types:

-  **Server backup vaults**: store backups of non-database servers or database servers. You can associate servers with a server backup vault and apply a policy to schedule automatic backups.
-  **Disk backup vaults**: store only disk backups. You can associate disks with a disk backup vault and apply a backup policy to schedule automatic backups.

Backup
------

A backup is a copy of a particular chunk of data and is usually stored elsewhere so that it may be used to restore the original data in the event of data loss. It can be generated either manually by a one-off backup task or automatically by a periodic backup task.

A one-off backup task is manually created and is executed only once. Periodic backup tasks are automatically executed based on a user-defined backup policy.

-  A one-off backup is named **manualbk\_**\ *xxxx* and can be user- or system-defined.
-  A periodic backup is named **autobk\_**\ *xxxx* by CBR.

Backup Policy
-------------

A backup policy is a set of rules that define the schedule and retention of backups. After you apply a backup policy to a vault, CBR automatically backs up data and retains backups based on that backup policy.

Instant Restore
---------------

Instant Restore restores data and creates images from backups, much faster than a normal restore.

Instant Restore is an enhanced function of CBR and requires no additional configuration. After Instant Restore is provided, you take less time to restore server data or create images.

Enhanced Backup
---------------

Enhanced backups are backups generated after Instant Restore is provided. Enhanced backups make it faster to restore server data or create images.

Before providing Instant Restore, CBR generates common backups. After providing Instant Restore, CBR first performs a full backup for each associated resource and then generates enhanced backups. CBR only generates enhanced backups for new resources currently.

For the same resource, an enhanced backup and a common backup have the same backup content and size. They only differ in the restoration speed.
