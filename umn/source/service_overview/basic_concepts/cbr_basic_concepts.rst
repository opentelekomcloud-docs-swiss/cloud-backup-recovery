:original_name: cbr_01_0012.html

.. _cbr_01_0012:

CBR Basic Concepts
==================

Vault
-----

CBR uses vaults to store backups of resources. Backup vaults are classified into the following types:

-  **Server backup vaults**: They include those that only store backups of common servers and those that store backups of database servers. You can associate servers with a server backup vault and apply a backup policy to the vault. You can also replicate backups from a vault in one region to a replication vault in another region. Server backups can be used to restore server data.
-  **Disk backup vaults**: store only disk backups. You can associate disks with a disk backup vault and apply a backup policy to the vault.

Backup
------

A backup is a copy of a particular chunk of data and is usually stored elsewhere so that it may be used to restore the original data in the event of data loss. It can be generated either manually by a one-off backup task or automatically by a periodic task.

CBR supports one-off backup and periodic backup. A one-off backup task is manually created by users and is executed only once. Periodic backup tasks are automatically executed based on a user-defined backup policy.

-  The name of a one-off backup is **manualbk\_**\ *xxxx*. It can be user- or system-defined.
-  The name of a periodic backup is **autobk\_**\ *xxxx*, which is assigned automatically by the system.

Backup Policy
-------------

A backup policy is a set of rules for backing up data, including the policy name, policy status, execution time of backup tasks, backup frequency, and retention rule. A retention rule specifies for how long backups are retained or the number of backups that are retained. Automatic backups can be performed by applying a backup policy to a backup vault.

Instant Restore
---------------

Instant Restore is a function for restoring data and creating images from backups. Instant Restore is much faster than a normal restoration process.

Backups of the **Common** type do not support Instant Restore, whereas, backups of the **Enhanced** type do. By default, all CBR backups are enhanced backups. Compared with common backups, enhanced backups use less time to restore server data or create images.

Enhanced Backup
---------------

Enhanced backups can be used to quickly restore server data or create images. This type of backups depends on Instant Restore.

Before Instant Restore is rolled out, all CBR backups generated are common backups. After Instant Restore is rolled out, all CBR backups generated are enhanced backups. This is an overall performance upgrade of CBR backups, and no additional configuration is required. Currently, all CBR backups generated are enhanced backups.

It takes a longer time to restore server data or create images using common backups. Enhanced backups can do the same thing with significantly shortened time. The only difference between common backups and enhanced backups is the restoration speed.
