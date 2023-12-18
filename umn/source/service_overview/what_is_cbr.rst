:original_name: cbr_01_0002.html

.. _cbr_01_0002:

What Is CBR?
============

Overview
--------

Cloud Backup and Recovery (CBR) enables you to easily back up Elastic Cloud Servers (ECSs) and Elastic Volume Service (EVS) disks. In case of a virus attack, accidental deletion, or software or hardware fault, you can use the backup to restore data to any point when the data was backed up.

CBR Architecture
----------------

CBR involves backups, vaults, and policies.

**Backup**

A backup is a copy of a particular chunk of data and is usually stored elsewhere so that it may be used to restore the original data in the event of data loss. There are the following types of backups:

-  Cloud disk backup: provides snapshot-based backups for EVS disks.
-  Cloud server backup: uses the consistency snapshot technology to protect data for ECSs.

**Vault**

CBR stores backups in vaults. Before creating a backup, you need to create at least one vault and associate the resources you want to back up with the vaults. Then the resources can be backed up to the associated vaults.

Different types of resources must be backed up to different types of vaults. For example, cloud servers must be backed up to server backup vaults, not disk backup vaults or any other types of vaults.

**Policy**

-  A backup policy defines when you want to take a backup and for how long you would retain each backup.


.. figure:: /_static/images/en-us_image_0242743738.png
   :alt: **Figure 1** CBR architecture

   **Figure 1** CBR architecture

Differences Among the Backup Types
----------------------------------

.. table:: **Table 1** Differences among the backup types

   +-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------+
   | Item            | Cloud Server Backup                            | Cloud Disk Backup                                                                            |
   +=================+================================================+==============================================================================================+
   | What to back up | All disks (system and data disks) on a server  | One or more specific disks (system or data disks)                                            |
   +-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------+
   | When to use     | You want to back up entire cloud servers.      | You want to back up only data disks.                                                         |
   +-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------+
   | Advantages      | All disks on a server are backed up at a time. | Only data of specific disks is backed up, which costs less than backing up an entire server. |
   +-----------------+------------------------------------------------+----------------------------------------------------------------------------------------------+

Backup Mechanism
----------------

CBR in-cloud backup offers block-level backup. The first backup is a full backup and backs up all used data blocks. For example, if a disk size is 100 GB and 40 GB has been used, only the 40 GB of data is backed up. An incremental backup backs up only the data changed since the last backup to save the storage space and backup time.

When a backup is deleted, data blocks will not be deleted if they are depended on by other backups, ensuring that other backups can still be used for restoration. Both a full backup and an incremental backup can be used to restore data to a given backup point in time.

When creating a backup of a disk, CBR also creates a snapshot for it. CBR keeps only the latest snapshot. Every time it creates a new snapshot during backup, it deletes the old snapshot.

CBR stores backups in OBS to ensure data security.

Backup Options
--------------

CBR supports one-off backup and periodic backup. A one-off backup task is manually created and is executed only once. Periodic backup tasks are automatically executed based on a user-defined backup policy.

:ref:`Table 2 <cbr_01_0002__table31963779194543>` compares the two backup options.

.. _cbr_01_0002__table31963779194543:

.. table:: **Table 2** One-off backup and periodic backup

   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Item                   | One-Off Backup                                                                                                                                             | Periodic Backup                                                                                                               |
   +========================+============================================================================================================================================================+===============================================================================================================================+
   | Backup policy          | Not required                                                                                                                                               | Required                                                                                                                      |
   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Number of backup tasks | One manual backup task                                                                                                                                     | Periodic tasks triggered by a preset backup policy                                                                            |
   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Backup name            | User-defined backup name, which is **manualbk\_**\ *xxxx* by default                                                                                       | System-assigned backup name, which is **autobk\_**\ *xxxx* by default                                                         |
   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Backup mode            | The first backup is a full backup and the consecutive backups are incremental.                                                                             | The first backup is a full backup and the consecutive backups are incremental.                                                |
   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+
   | Application scenario   | Executed before patching or upgrading the OS or upgrading an application. A one-off backup can be used for restoration if the patching or upgrading fails. | Executed for routine maintenance. The latest backup can be used for restoration if an unexpected failure or data loss occurs. |
   +------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------+

You can also use the two backup options together if needed. For example, you can associate resources with a vault and apply a backup policy to the vault to execute periodic backup for all the resources in the vault. Additionally, you can perform a one-off backup for the most important resources to enhance data security. :ref:`Figure 2 <cbr_01_0002__fig190314191275>` shows the use of the two backup options.

.. _cbr_01_0002__fig190314191275:

.. figure:: /_static/images/en-us_image_0285742235.png
   :alt: **Figure 2** Use of the two backup options

   **Figure 2** Use of the two backup options

Access to CBR
-------------

You can access the CBR service through the console or by calling HTTPS-based APIs.

-  Console

   Use the console if you prefer a web-based UI. Log in to the console and choose **Cloud Backup and Recovery**.

-  APIs

   Use APIs if you need to integrate CBR into a third-party system for secondary development. For details, see the *Cloud Backup and Recovery API Reference*.
